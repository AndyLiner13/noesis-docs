Source: https://www.noesisengine.com/docs/Gui.Core.FirstSteps.html

# First steps with XamlPlayer

*XamlPlayer* is a lightweight XAML viewer that can be used to quickly try out UI experiments. It is located inside the root folder of the SDK and it is also available as a project with source code. As the rest of examples it is implemented using the [Application Framework](/Gui.Core/ApplicationTutorial.md).

![FirstStepsTutorialImg1.png](/FirstStepsTutorialImg1/png.md)

# Xaml Visualization

*XamlPlayer* offers two ways to visualize XAMLs:

- Using Drag and Drop.
- Connecting remotely with the [Inspector](/Gui.Core/InspectorTutorial.md).

NOTE

XamlPlayer can be used to visualize images, fonts and rive files too.

## Drag and Drop

To visualize a XAML file just simply drag and drop it to the *XamlPlayer* window. We have included several samples inside the folder '*NoesisSDK/Data*' of the SDK. It is recommended that you test all of the provided samples to get an overview of the different features offered by NoesisGUI. For example, if you drag the file *CarHud.xaml* and drop it to the *XamlPlayer* window you should get the following:

![FirstStepsTutorialImg2.png](/FirstStepsTutorialImg2/png.md)

## Remote loading

An alternative to drag and drop is remotely connecting with [Inspector](/Gui.Core/InspectorTutorial.md) to load content into *XamlPlayer*. This is useful when using *XamlPlayer* in mobile devices or consoles where dragging files is not possible.

![FirstStepsTutorialImg3.png](/FirstStepsTutorialImg3/png.md)

'*Content.xaml*' is the XAML that is used internally by *XamlPlayer* to host the visualization. So, just go to *Resources* panel of *Inspector* and point '*Project Path*' to a location where a file with the name *Content.xaml* can be found. Each time '*Content.xaml*' is edited and saved it will automatically reload in *XamlPlayer*.

# Hot Reload

Content visualized by *XamlPlayer* will automatically [Hot Reload](/Gui.Core/HotReloadTutorial.md) whenever file sources changes. Content reloading can also be forced by pressing the F5 key. We recommend using our [Visual Studio Code extension](https://noesisengine.com/vscode) to edit XAML files.

# View Controls

- To rotate the view in 3D press and hold ALT + Right Mouse Button while moving the mouse.
- To pan the view press and hold CTRL + Right Mouse button while moving the mouse.
- To zoom where your mouse is pointing press CTRL + Mouse wheel.
- To reset the view press CTRL + R.
- To open the settings toolbar press CTRL + T.
- To open the performance stats panel press CTRL + F.
- To reload content press F5.
- To take a [RenderDoc](https://renderdoc.org/) capture press F10.

NOTE

Depending on the platform, the toolbar is activated by doing 'CTRL+T' on desktop, 'Options' button on consoles or 'left-swiping' for mobiles.

# Debugging Helpers

The toolbar located to the left side provides the following debugging functionality:

- **Wireframe**: toggles wireframe mode when rendering triangles.
- **Batches**: each batch submitted to the GPU is given a unique solid color.
- **Overdraw**: display pixel overdraw using blending layers. Different colors are used for each type of triangle: *Red* for opacities, *Blue* for clipping masks and *Green* for the rest.
- **PPAA**: per-primitive [Antialiasing](/Gui.Core/AntialiasingTutorial.md) extrudes the contours of the geometry and smooths them. Useful when GPU multisampling is not enabled.
- **Stats**: display a [performance](/Gui.Core/Optimizing.md) stats panel.

![FirstStepsTutorialImg4.png](/FirstStepsTutorialImg4/png.md)

# Command Line

XamlPlayer also understands the following command line switches:

- **filename.xaml**: to load a XAML at startup.
- **--render [D3D11|GL|Metal|...]**: overrides the default renderer.
- **--vsync [0|1]**: disables vertical synchronization.
- **--samples N**: enables multisample anti-aliasing (MSAA), by default it is off.
- **--linear**: for switching to linear rendering, by default rendering happens in gamma space.
- **--log\_binding**: to increase the verbosity of logging when using data binding.
- **--emulate\_touch**: enables emulation of touch input from mouse events.