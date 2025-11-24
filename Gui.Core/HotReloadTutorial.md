Source: https://www.noesisengine.com/docs/Gui.Core.HotReloadTutorial.html

# Hot Reload

Hot Reload helps you quickly and easily build user interfaces. Without Hot Reload, you have to build and deploy your application every time you want to see a change. With Hot Reload, when you save your XAML or Image the changes are reflected live in your running application. In addition, your navigation state and data will be maintained, enabling you to quickly iterate on your UI without losing your place in the application. Therefore, with Hot Reload, you will spend less time rebuilding and deploying your apps to validate UI changes.

# XAML Hot Reload

Hot Reload parses the XAML to see exactly what changed when you make an edit, and sends just those changes to the running application. It preserves UI state, since it doesn't recreate the UI for the full page, just updating changed properties and controls affected by edits.

Changes in resource dictionaries are also supported, even in multiple XAMLs. Hot Reload creates new styles when modifying sealed ones. Theme modifications are reapplied without having to restart the application.

![HotReloadTutorial0.gif](/HotReloadTutorial0/gif.md)

# Enable Hot Reload

Hot Reload is only supported in 'Profile' configurations of NoesisGUI. It also needs assistance from the installed [Resource Providers](/Gui.Core/ProvidersTutorial.md#hot-reloading). Providers must invoke the corresponding delegate when changes happen, for example in a filesystem.

The following providers included in the App Framework already implement support for Hot Reload using a filesystem watcher:

- LocalXamlProvider
- LocalTextureProvider
- LocalFontProvider

Note

In Unity and Unreal, Hot Reload is always enabled in the editor

# Disable Hot Reload

Hot Reload consumes a bit of extra memory and it can be disabled just in case you don't need this feature while developing your application. You can do so by adding the following code before initializing Noesis. Note that Hot Reload is disabled at compile time in 'Release' configurations.

```
Noesis::GUI::DisableHotReload();
Noesis::GUI::Init();
```

# Hot Reload in SDK Samples

By default, the examples included in the SDK use embedded resources stored in the executable. This can be overridden with the '--root' command line switch to enable Hot Reload. For example:

```
Samples.HelloWorld --root W:/Noesis/NoesisSDK/Native/Src/Packages/Samples/HelloWorld/Data
```

# Hot Reload on Remote App

Hot Reload is also supported remotely, for example when running your application in a mobile device or in a video game console. This is supported by connecting to the remote application with the [Inspector](/Gui.Core/InspectorTutorial.md) and setting up a local 'Project path'.

![InspectorTutorialImg5.png](/InspectorTutorialImg5/png.md)