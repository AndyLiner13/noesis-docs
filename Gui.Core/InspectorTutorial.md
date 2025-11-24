Source: https://www.noesisengine.com/docs/Gui.Core.InspectorTutorial.html

# NoesisGUI Inspector

Inspector is a tool that allows the user to connect to a live instance of a NoesisGUI based application and observe and modify the state of the UI objects. It may help you track down problems in your application and iterate quickly by changing properties on the fly without having to restart your application.

Key features of *Inspector* are:

- Remote connection to Views.
- Global Performance Counters.
- Visual Tree inspection.
- Live Edit Values of objects in the tree.
- Frame performance stats.
- Hot Reloading of assets.
- Access to console.

NOTE

Inspector is only available in PRO licenses. It is a private download you get access to when acquiring a license

# Getting started

To use the *Inspector* within your application a instrumented Noesis library is necessary. By default, the libraries includes in our public SDKs are instrumented and compatible with Inspector. Inspector is enabled by default and it can be disabled before initializing Noesis by calling *Noesis::GUI::DisableInspector()*.

NOTE

In Unity, only builds with 'Development Build' flag enabled can be used with the Inspector.

For Unreal, Inspector is disabled in *Shipping* build configurations.

NOTE

We do not recommend distributing official releases of your application with instrumented Noesis library

When the application to be inspected launches, it should appear on the **Connect to...** dialog on the *Inspector*.

![InspectorTutorialImg7.png](/InspectorTutorialImg7/png.md)

Once you select a target application a connection will be established and you are ready to start inspecting it.

If *Auto connect* was selected, Inspector will automatically reconnect to any application launched on the same IP without going back to the **Connect to...** dialog. This is very useful if you are working on your application and need to restart it several times.

NOTE

Make sure your application keeps rendering even without focus when the Inspector is connected. The function 'Noesis::GUI::IsInspectorConnected()' can be used for this purpose.

![InspectorTutorialImg8.png](/InspectorTutorialImg8/png.md)

# Inspector layout

Once a connection is established, you'll be presented with the UI of the Inspector. The top part of the window is always the same, and consists of a minimal toolbar, and a set of high level performance graphs.

The toolbar allows you to select a new target in the **Connect to...** dialog, and it displays the information of the currently attached target: the name of the application, the IP address of the target and the platform. It also contains a drop down list with all the Views in the current target, as well as buttons that let you toggle some debug visualization settings: *Wireframe*, *Batches*, *Overdraw*, and *Glyph* and *Gradient Texture Overlays*.

The overall [performance](/Gui.Core/Optimizing.md) graphs allow to see at a glance how your application is performing, by displaying the frames per second (the inverse of the frame time), update and render times, as well as the amount of memory that NoesisGUI is using at the moment.

![InspectorTutorialImg1.png](/InspectorTutorialImg1/png.md)

Under these graphs there are a series of tabs: *Elements*, *Performance*, *Resources* and *Console*. Their utility will be described in the following sections.

## Elements tab

The element tab allows to inspect the *Visual* tree and the properties of its nodes, as well as modifying said properties values.

On the left you have the *Visual* tree panel. It displays the hierarchy of *Visual* nodes of the selected *View*. For each node you can see its name (if it's got any), its type between square brackets, and the number of nodes under it on the right. Additionally, if the node was created from a XAML, a link to it is provided. Please, read the *Resources* tab section for more information about how to edit and reload resources on the fly.

![InspectorTutorialImg9.png](/InspectorTutorialImg9/png.md)

## Performance tab

![InspectorTutorialImg3.png](/InspectorTutorialImg3/png.md)

This tab shows more in depth performance information about each buffered frame of your application. At the top you have the performance graph, which displays the update and render times for each frame. You can click on the graph to select a single frame, and then use the arrow buttons to move to the previous and next frames. When a frame is selected, the graph stops updating automatically, but you can stop it first by clicking on the pause button. If you want to resume updating, click the play button. You can select which times are shown using the color coded check boxes on the left.

The bottom panel shows information about the selected frame, or the average of the last second of run time if none is selected. On the left you have rendering statistics: you have the frames per second and its inverse, the frame time, and also the update and render times for that particular frame. To the right you have information related to the drawing of the frame: the number of triangles drawn, the number of primitives drawn, how many batches were submitted to the GPU, the total number of paths tessellated (and the delta from the previous frame), and the total size of the buffers submitted to the GPU (and the number of submissions required). Under that, you can find information related to some of the textures NoesisGUI uses internally: the total number of gradients updated, glyphs rasterized and discarded from the glyph cache, as we as the deltas from the previous frame between parentheses. Finally, on the left, you can see the number of stencil buffer masks, opacity groups and render target switches that were required for the selected frame.

The right hand side panel shows the total amount of memory allocated at the moment, as well as the number of allocations requested. While the render stats apply only to the selected View, the memory stats refer to all the NoesisGUI objects in the application.

![InspectorTutorialImg4.png](/InspectorTutorialImg4/png.md)

## Resources tab

The resources tab displays lists of resources currently loaded by you application through the different types of providers: *XAML*, *Texture* and *Font*.

At the top of there's an address bar where you can type or browse for the project directory on your computer. This will be used, along with the URIs, to open the asset files from your computer. Just set the project path, and either double click or select and click *Edit* and your default program will be used to open the selected file. You can then edit and save the file, and the new contents will be [Hot Reloaded](/Gui.Core/HotReloadTutorial.md) on the target application.

![InspectorTutorialImg5.png](/InspectorTutorialImg5/png.md)

## Console tab

The console tab displays the output of the target application, and also allows you to run commands on the target application using the command prompt at the bottom.

![InspectorTutorialImg6.png](/InspectorTutorialImg6/png.md)