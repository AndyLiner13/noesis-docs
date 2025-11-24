Source: https://www.noesisengine.com/docs/Gui.Core.RenderingTutorial.html

# Rendering Architecture

NoesisGUI rendering architecture is designed to have two threads working in parallel: the *ui* thread and the *render* thread. Although, as explained later, this is not strictly mandatory. You can have more threads or even have no extra threads at all. Under no circumstances our core library will create threads under the hood. This responsibility is delegated to the client who is in charge of invoking *Noesis* from the appropriate thread.

![RenderingTutorialImg1.jpg](/RenderingTutorialImg1/jpg.md)

# UI Thread

This is the thread where all logical interactions between the user and the application happen. Things like *event* dispatching and *layout* processing occurs in this thread. Note that depending on the complexity of the application this can be the *Main* thread or a separate *UI* thread.

The object in charge of providing this interaction is the *View*. It can be created by calling *GUI::CreateView()*.

```
// Loads XAML and creates a view with it
Ptr<FrameworkElement> xaml = Noesis::GUI::LoadXaml<FrameworkElement>("Button.xaml");
Ptr<IView> view = Noesis::GUI::CreateView(xaml);

// Sets logical size
view->SetSize(width, height);
```

View instances are not thread-safe. All invocations must happen in the same thread where view was created.

```
// Send input events to view
view->MouseButtonDown(x, y, button);
view->MouseButtonUp(x, y, button);
view->MouseDoubleClick(x, y, button);
view->MouseMove(x, y);
```

NOTE

Any violation of this thread-safety is reported as an error in 'checked' builds.

Once per frame the view instance must be ticked to update its internal representation. At this step the current state is locked and stored to be consumed by the render thread described in the next section. From a high-level perspective this can be seen as taking a frame **snapshot** of the current UI state.

```
// Updates view
view->Update(time);
```

Note that although you can only interact with the view from the owner thread, you are allowed to create several views in different threads. This way you can update each view in parallel. Although the overhead of each view is low, it is recommended to only have one view per surface. In a normal scenario, you create a view for the main camera and a separate view for each render texture that is needed, reusing them as much as possible.

NOTE

Please note that 'Update' never blocks and allocates memory when not synchronized with 'UpdateRenderTree'. It's crucial to maintain a balance between invocations of 'Update' that return true and calls to 'UpdateRenderTree'.

# Render Thread

This is the thread that directly interacts with the GPU through the *RenderDevice* abstract class. Being *Noesis* rendering agnostic, it is client code responsibility to provide one *RenderDevice* implementation. The [Application Framework](/Gui.Core/ApplicationTutorial.md) provides many reference implementations that can be used as a starting point to create a custom one. *RenderDevice* exposes a few functions to control the internal *Vector Graphics* context created. Default values should work well for most scenarios.

```
Ptr<GLRenderDevice> device = *new GLRenderDevice();
device->SetGlyphCacheWidth(2048);
device->SetGlyphCacheHeight(2048);
device->SetOffscreenSampleCount(1);
```

Each view contains a renderer that must be initialize with a *RenderDevice* implementation. All interactions with the view in the render thread are isolated through the interface *IRenderer*. This interface is obtained by calling *GetRenderer()*.

```
view->GetRenderer()->Init(device);
```

Each time you need to render a new frame you must call *UpdateRenderTree()* to collect pending update commands from the UI thread. This is like grabbing a frame from the UI thread. The rendering is decomposed into two stages:

- **Offscreen** (*RenderOffscreen()*). Sometimes, for example when using effects like shadows or when using opacity groups, the view needs to render content to intermediate textures. Those drawing commands happen at this stage. It is very important that this stage takes place before binding the main surface. This is especially important in tiled architectures.
- **Onscreen** (*Render()*). At this point the view renders primitives to the currently active framebuffer. For example, when rendering HUD interfaces this stage happens after rendering 3D content and before swapping or resolving the back buffer.

NOTE

[IntegrationGLUT](https://github.com/Noesis/Tutorials/tree/master/Samples/IntegrationGLUT) is a minimalist integration sample showcasing these concepts.

```
// Applies last changes happened in view
view->GetRenderer()->UpdateRenderTree();

// Generates offscreen textures
view->GetRenderer()->RenderOffscreen();

// ------->
// HERE: Insert code to render your 3D scene
// <-------

// Render UI in the active render target and viewport dimensions
view->GetRenderer()->Render();
```

Note that several views can be managed in the same render thread just by initializing all of them with the same render device. That way internal resources like ramps and glyphs are shared across all views. *RenderDevice* is a heavyweight class. Extra instances should be avoided whenever possible.

NOTE

Extra parallelization may happen at RenderDevice implementation level. For example, using deferred contexts in *D3D11* or similar concepts in other APIs. Doing this, generating GPU commands for the UI can be done in parallel with the rest of frame commands. This is useful for architectures already using *Jobs* or *Tasks*.

The common scenario is having just one render thread. But sometimes interacting with different render devices in different threads is necessary. In this case, each thread must have its own instance of *RenderDevice*. Instances of *RenderDevice* are not thread-safe and must not be shared. Following this pattern, each render thread is in in charge of collecting updates from all the views that it initialized.