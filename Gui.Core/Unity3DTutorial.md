Source: https://www.noesisengine.com/docs/Gui.Core.Unity3DTutorial.html

# First steps with NoesisGUI and Unity

![unity.jpg](/unity/jpg.md)

This tutorial covers the basics of using NoesisGUI within Unity. NoesisGUI entirely replaces Unity UI offering a much more convenient and efficient approach. You will learn how to start editing the samples included in NoesisGUI package and how to create new games from scratch. NoesisGUI is deeply integrated with Unity; XAMLs appear as native resources that directly use assets imported by Unity like *Textures*, *Fonts*, *VideoClips* and *AudioClips*. It is strongly recommended that you read the rest of [tutorials](/Gui.Core/Index.md) to familiarize yourself with the basic concepts of XAML and the *Noesis* architecture.

![spacer.png](/spacer/png.md)

NoesisGUI is fully compatible with all major Unity rendering pipelines across recent Unity versions. The table below summarizes the supported Unity versions and their compatibility with the Built-in, URP, and HDRP pipelines:

| Unity Version | Built-in | URP | HDRP |
| --- | --- | --- | --- |
| 2020.2 - 2023.x | ✅Compatible | ✅Compatible | ✅Compatible |
| Unity 6.0 | ✅Compatible | ✅Compatible | ✅Compatible |
| Unity 6.1 | ✅Compatible | ✅Compatible | ✅Compatible |

# What's new in 3.2

- Added support for [Rive](#rive-assets) assets.
- Support for disabling [Hot-reloading](/Gui.Core/HotReloadTutorial.md) from [Settings](#configuring-noesisgui) panel.
- Legacy Input System is no longer necessary.
- Added tracking device actions for XR to [Input Actions Asset](#input-actions).
- Added [World Space UI](#world-space-ui) property to View.
- Support for editing XAML files in [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=NoesisTechnologies.noesisgui-tools).
- Vulkan renderer is now supported in Windows and Android platforms.
- Unity 2023.2+ is [required](https://docs.unity3d.com/Manual/webgl-native-plugins-with-emscripten.html) for WebGL.
- All new features included in [3.2 Core](/Gui.Core/Changelog.md#version-3-2-0b1) are also available.

# What's new in 3.1

- NoesisGUI is now a package that must be installed using the [Package Manager](https://docs.unity3d.com/Manual/upm-ui.html). The previous package, located at *'Assets/NoesisGUI'* must be deleted before installing the new version.
- XAMLs assets are now implemented using a [Scripted Importer](https://docs.unity3d.com/Manual/ScriptedImporters.html). This means that we no longer need the corresponding *.asset* file for each *.xaml*. You must delete all *.asset* files belonging to *.xaml* resources if you are upgrading your project. References to XAMLs from current views must also be recreated. Since 3.1.1 this step is performed automatically.
- Fonts are also implemented using a [Scripted Importer](https://docs.unity3d.com/Manual/ScriptedImporters.html). In this case we are overriding the default font importer used by Unity. Same as with XAMLs, you must delete all *.asset* files belonging to *.ttf* resources. Since 3.1.1 this step is performed automatically.
- *NoesisSettings.asset* has been deprecated and must be removed. When first installing NoesisGUI 3.1, a new *Noesis.settings.asset* will be created. This new asset is very similar to the legacy one but no longer needs to be stored inside a *Resources* folder.
- [Sprites](https://docs.unity3d.com/Manual/Sprites.html) are now supported in *DataContexts* and accessible to [ImageSource](/Gui.Core/_ImageSource.md) properties in XAML using data-binding. See our *Inventory* sample.
- Implemented gamepad events using the new [Input System Package](https://docs.unity3d.com/Manual/com.unity.inputsystem.html). Note that for keyboard, mouse and touch we still need the legacy Input System.
- All new features like *Videos*, *Blending Modes* and *Shaders* included in [3.1 Core](/Gui.Core/Changelog_v31.md) are also available for Unity. See our examples *VideoEffect* and *BrushShaders*.
- Hot-reloading while in *Play* mode is now always enabled.

# Installation

The first step is downloading the latest version of the Unity package from our [website](https://www.noesisengine.com/developers/downloads.php). After that, extract the corresponding *NoesisGUI-Unity-X.X.X.zip* file into a folder and locate the file *package.json* at the root.

Next, open Unity's [Package Manager](https://docs.unity3d.com/Manual/upm-ui.html) and install the NoesisGUI package from the extracted local folder using the *"Install package from disk..."* option.

![Unity3DTutorialImg1.png](/Unity3DTutorialImg1/png.md)

Note

*NoesisGUI-Unity-X.X.X.zip* must **not** be decompressed inside the '/*Assets*' folder of your project.

The recommended location for embedded packages is the '/*Packages*' folder.

The minimum Unity version that NoesisGUI is compatible with is indicated in '*package.json*'. For NoesisGUI 3.2.8, it is 2020.2.

If this is your first contact with *Noesis*, we recommend importing all the examples included in the package and reading the provided documentation. Our samples are also available on [GitHub](https://github.com/Noesis/Tutorials) and the documentation can be read online at our [website](https://www.noesisengine.com/docs/). Please note that the samples included in the package are always more up to date than those available on *GitHub*.

![Unity3DTutorialImg101.png](/Unity3DTutorialImg101/png.md)

# Examples

Within the installed package, we provide several working samples, each with its corresponding scene file (.unity) and a [Microsoft Blend](https://en.wikipedia.org/wiki/Microsoft_Blend) project. For example, the *HelloWorld* sample includes the scene located at *HelloWorld/HelloWorld.unity* and the Blend project located at *HelloWorld/HelloWorld-blend.csproj*.

Many more examples can be found in our [GitHub](https://github.com/Noesis/Tutorials/tree/master/Samples) repository; however, please note that the samples included in the package are always more up to date than those available on GitHub.

![Unity3DTutorialImg2_.png](/Unity3DTutorialImg2_/png.md)

# Configuring NoesisGUI

Clicking on the Unity menu option '*Tools* -> *NoesisGUI* -> *Settings*' will open an inspector window that displays global options for NoesisGUI. This same window is also available in *Project Settings* under the NoesisGUI category. For more details about a specific option, hover the mouse over it to see a helpful tooltip description.

Note

Settings, by default, are stored at '*Assets/Noesis.settings.asset*'. Please move this file to a different folder that better suits your project layout.

The *Application Resources* field in this settings window is especially important: it replaces the traditional *App.xaml* used in WPF applications. Since Unity does not use the Application class, any global resource dictionaries that would normally go into *App.xaml* must be referenced here instead. This includes the default *Theme*, or any custom resources your project needs globally. If you're migrating from Blend and using its default structure, make sure to move the merged dictionaries from *App.xaml* into the *Application Resources* section manually.

More information about available Noesis licenses can be found in the [Licensing documentation](/Gui.Core/Licensing.md).

![Unity3DTutorialImg2.png](/Unity3DTutorialImg2/png.md)

# Blend

![Unity3DTutorialImg3_.png](/Unity3DTutorialImg3_/png.md)

*Microsoft Blend* for *Visual Studio* (formerly Microsoft Expression Blend) is an interactive WYSIWYG front-end for designing XAML-based interfaces. In this section, we will explain how you can use it so changes performed in Blend appear immediately in the Unity Editor, even in *Play* mode. This workflow allows quick iterations while designing user interfaces.

Note

For getting started with Blend, we recommend reading our [Blend Native Tutorial](/Gui.Core/BlendTutorial.md).

Note

If you move assets, make sure to keep your Blend project in sync, as this is not done automatically.

Beta Feature

We are actively working on [Noesis Studio](https://www.noesisengine.com/forums/viewforum.php?f=15), our modern, integrated replacement for Blend. It's currently in *beta* and aims to provide a more streamlined and native experience for designing UIs with Noesis. Stay tuned for updates and consider trying it out if you'd like to get early access to the future of Noesis GUI design.

## New project

If you want to quickly create a new Unity project set up for NoesisGUI, we offer a Visual Studio project template available in the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=NoesisTechnologies.noesistemplates).

To install this template:

- Launch Visual Studio and click '*Extensions* -> *Manage Extensions*' from the Menu Bar.
- In the Extension Manager, expand the *Online* node and search for *Noesis*. Download the *NoesisGUI Project Templates* extension and restart Visual Studio.

![Unity3DTutorialImg13.png](/Unity3DTutorialImg13/png.md)

To create an application from the project template, simply create a new C# solution using the *Unity App (NoesisGUI)* template from Visual Studio's Start Page.

![Unity3DTutorialImg15.png](/Unity3DTutorialImg15/png.md)

## Existing project

If you are already working on a Unity project and decide to add NoesisGUI to implement your game's or application's user interface, our plugin adds a new entry to the *Assets* top menu: *Open Blend project*.

The first time you select this option, it will create a new Blend project at the root of your Unity project. This project is preconfigured to easily reference resources from your *Assets/* folder, and the solution file will be named *{UnityProjectName}-blend.sln*.

![Unity3DTutorialImg222.png](/Unity3DTutorialImg222/png.md)

The project also creates a sample XAML file at the root of *Assets/* to help you get started. Simply drag that XAML asset onto the *Main Camera* in an empty Unity scene and click *Play* to see your first XAML UI in action.

![Unity3DTutorialImg223.png](/Unity3DTutorialImg223/png.md)
![Unity3DTutorialImg224.png](/Unity3DTutorialImg224/png.md)

## Code-behind

User controls with [code-behind](/Gui.Core/CodeBehindTutorial.md) need to be adapted to compile correctly in both Blend and Unity. Preprocessor macro directives such as **#define** and **#if** must be used to separate NoesisGUI-specific code that is not [100% compatible with WPF](/Gui.Core/WPFComparison.md#code-behind-differences).

All our [samples](https://github.com/Noesis/Tutorials/tree/master/Samples/Buttons/Unity) use preprocessor directives in this way.

```
#if UNITY_5_3_OR_NEWER
   #define NOESIS
   using Noesis;
#else
   using System;
   using System.Windows.Controls;
#endif

namespace DummyGame
{
   /// <summary>
   /// Interaction logic for DummyGameMainView.xaml
   /// </summary>
   public partial class DummyGameMainView : UserControl
   {
      public DummyGameMainView()
      {
         InitializeComponent();
      }

    #if NOESIS
      private void InitializeComponent()
      {
         NoesisUnity.LoadComponent(this);
      }
    #endif
   }
}
```

# Assets

## XAML assets

When you drag and drop XAML files into your project '*Assets/*' folder, Unity will automatically generate a *NoesisXaml* asset for each file. These assets come with a thumbnail preview and a dedicated preview window, making it easier to identify and work with your UI files directly within the Unity Editor.

Note

'Window' root elements are not supported by NoesisGUI in Unity, as the windowing system is provided by the Unity engine itself. Instead, we recommend using 'Page', 'UserControl', or any 'Panel' class as the XAML root.

Additionally, the 'Application' class is not supported. This means that the 'App.xaml' file typically created by Blend cannot be used as-is. If you have a merged dictionary defined in 'App.xaml', you should manually add it to the *Application Resources* property found in the Noesis *Settings* panel.

You can also create a few XAML snippets directly from the '*Tools* -> *NoesisGUI* -> *Create*' menu.

![Unity3DTutorialImg20.png](/Unity3DTutorialImg20/png.md)

The import process will automatically inject dependencies to referenced resources like *Resource Dictionaries*, *Textures*, *AudioClips*, *VideoClips*, *Shaders*, *Fonts*, *Rives*, and *UserControls*.

To properly detect dependencies for *UserControls* and *Shaders*, you must adhere to the following naming conventions:

> | XAML usage | Dependency Asset |
> | --- | --- |
> | <local:MyUserControl Input="200" /> | MyUserControl.xaml |
> | <local:MonochromeBrush Color="White" /> | Monochrome.noesisbrush |
> | <local:TintEffect Color="Orange" /> | Tint.noesiseffect |

Note

To properly detect dependencies, a namespace, such as *local:*, must always be used. Direct references without a namespace will not be resolved during the import process.

It is extremely important that every XAML file declares its dependencies correctly. When building a standalone player in Unity, only the assets explicitly referenced will be included in the final build. If dependencies are not properly linked through your XAML, required resources (such as fonts, textures, or controls) may be excluded, resulting in missing or broken UI elements at runtime.

To inspect the list of dependencies for a given XAML file, simply click on the asset in the Unity Editor to open its inspector panel.

![Unity3DTutorialImg21_.png](/Unity3DTutorialImg21_/png.md)

Just in case you need to add extra dependencies to your XAML, such as resources used only from code in *ViewModels*, we provide the [extension](/Gui.Core/ExtensionsTutorial.md#unity-extensions) property *Xaml.Dependencies*.

The specified [URI](/Gui.Providers/_Uri.md) can be either relative to the XAML file where the dependency is defined or an absolute URI.

Note

We generally do **not** recommend setting dependencies manually. This feature is mostly legacy and should not be necessary in almost all scenarios, if the naming conventions are followed, as the import process automatically detects dependencies.

```
<UserControl
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions"
  x:Class="Localization.MainWindow"
  FontFamily="./#Oxygen, ./#FontopoNIHONGO"
  Foreground="#FF488EB5">

  <noesis:Xaml.Dependencies>
    <noesis:Dependency Source="Language-en.xaml"/>
    <noesis:Dependency Source="Language-fr.xaml"/>
    <noesis:Dependency Source="Language-jp.xaml"/>
  </noesis:Xaml.Dependencies>

</UserControl>
```

### Theme

A *Theme* provides [default styles](/Gui.Core/StylingTutorial.md) for all UI controls, serving as a solid starting point to create your own game styles.

It is configured in the [NoesisGUI Settings](/Gui.Core/Unity3DTutorial.md#configuring-noesisgui) menu, under the *Application Resources* entry. By default, our [Noesis Theme](/Gui.Core/ApplicationTutorial.md#noesis-theme), located at *Packages/com.noesis.noesisgui/Theme*, is used.

Note

*App.xaml* is not used by Unity. Instead, Application Resources are set in the NoesisGUI Settings.

![NoesisTheme.png](/NoesisTheme/png.md)

### Language Server

A [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=NoesisTechnologies.noesisgui-tools) extension is available to provide a rich editing experience when working with XAML.

This extension enables language server features such as autocompletion, type information, and error highlighting, while the Unity Editor is open.

![Unity3DTutorialImg22_.png](/Unity3DTutorialImg22_/png.md)

## Texture assets

[Images](/Gui.Core/ImagesTutorial.md) used inside XAMLs generate a dependency to the corresponding Unity texture asset. The texture imported by Unity is directly consumed by NoesisGUI. This means that all settings available under Import Settings are respected.

If your images include alpha, make sure to:

- Set *Alpha Source* to *Input Texture Alpha*
- Uncheck *Alpha is Transparency*
- Add the label Noesis to the texture to enable automatic conversion to the [premultiplied-alpha](https://developer.nvidia.com/content/alpha-blending-pre-or-not-pre) format required by Noesis

Note

If the Noesis label is not added to a texture, Noesis will emit a runtime warning each time that texture is used

![Unity3DTutorialImg22.png](/Unity3DTutorialImg22/png.md)

### Sprites

[Sprites](https://docs.unity3d.com/Manual/Sprites.html) in Unity can be used with NoesisGUI just like regular images. If a sprite is part of a sprite atlas, it can still be referenced normally in XAML, as NoesisGUI reads the underlying texture asset.

Additionally, you can expose objects in your view models and bind them directly to Image.Source.

This makes it easy to integrate your existing Unity workflows with Noesis-based UIs.

```
public class Item
{
    public UnityEngine.Sprite _icon;
    public UnityEngine.Sprite Icon { get => _icon; }
}
```

This Sprite property can be consumed by any *ImageSource* property in XAML using [data-binding](/Gui.Core/DataBindingTutorial.md):

```
 <DataTemplate x:Key="InventorySlot">
   <Grid Margin="5" Background="Transparent" ToolTip="{Binding Item.Description}">
     <Border BorderThickness="2" BorderBrush="{StaticResource OrangeBorder}"
       Background="{StaticResource RadialBackground}" CornerRadius="4"/>
     <Image Source="{Binding Item.Icon}"/>
   </Grid>
</DataTemplate>
```

The *Inventory* sample included in the package demonstrates how to use sprites and atlases effectively to reduce the number of draw calls, helping you build more performance-efficient interfaces.

![Unity3DTutorialImg221.png](/Unity3DTutorialImg221/png.md)

## AudioClip assets

*AudioClips* are natively supported by NoesisGUI through the [Behaviors](/App.Interactivity/Behaviors.md) system.

Any clip used in a [PlaySoundAction](/App.Interactivity/_PlaySoundAction.md) is automatically added as a dependency of the XAML, ensuring it is properly included in the Unity build.

```
<Button Content="START" Command="{Binding StartCommand}">
  <b:Interaction.Triggers>
    <b:EventTrigger EventName="GotFocus">
      <b:PlaySoundAction Source="AudioSlide.mp3" Volume="0.5"/>
    </b:EventTrigger>
    <b:EventTrigger EventName="Click">
      <b:PlaySoundAction Source="AudioClick.mp3" Volume="0.8"/>
    </b:EventTrigger>
  </b:Interaction.Triggers>
</Button>
```

![Unity3DTutorialImg225.png](/Unity3DTutorialImg225/png.md)

## VideoClip assets

*VideoClips* can be played using the [MediaElement](/App.MediaElement/_MediaElement.md) control.

Just like *AudioClips*, they are automatically detected and added as XAML dependencies, ensuring they are correctly included in the Unity build.

```
<Grid x:Name="LayoutRoot">
  <Border>
    <Border.Effect>
      <noesis:TintEffect/>
    </Border.Effect>
    <MediaElement Source="Particles.mp4" Stretch="UniformToFill" LoadedBehavior="Manual">
      <b:Interaction.Triggers>
        <b:EventTrigger EventName="Loaded">
          <noesis:PlayMediaAction/>
        </b:EventTrigger>
        <b:EventTrigger EventName="MediaEnded">
          <noesis:StopMediaAction/>
          <noesis:PlayMediaAction/>
        </b:EventTrigger>
      </b:Interaction.Triggers>
    </MediaElement>
  </Border>
</Grid>
```

![Unity3DTutorialImg226.png](/Unity3DTutorialImg226/png.md)

## Fonts assets

Similar to XAMLs, each time you drop a *.ttf*, *.otf*, or *.ttc* file into your Unity project, it is automatically imported by NoesisGUI.

An editor window is provided to display key attributes such as *Family*, *Weight*, *Style*, and *Stretch*, along with a real-time render preview of the font.

![Unity3DTutorialImg220.png](/Unity3DTutorialImg220/png.md)

## Shader assets

As described in the [Shaders Tutorial](/Gui.Core/ShadersTutorial.md), NoesisGUI can be extended with shaders using [Effects](/Gui.Core/_Effect.md) and [Brushes](/Gui.Core/_BrushShader.md).

In Unity, shaders for effects are defined in *.noesiseffect* files, while shaders for brushes are defined in *.noesisbrush* files. Both formats describe the shader in HLSL.

These assets are automatically added as dependencies to XAMLs based on naming conventions. Specifically, the suffixes *Effect* and *Brush* in your class names are replaced by *.noesiseffect* and *.noesisbrush* respectively. For example:

- The node <local:TintEffect Color="Orange"/> generates a dependency to the asset Tint.noesiseffect
- The node <local:NoiseBrush Scale="2"/> generates a dependency to the asset Noise.noesisbrush

Shaders are loaded in C# using the *CreateShader* function. This function should be called once to initialize the shader. Then, use *SetShader* on each instance to apply it.

```
public class NoiseBrush : BrushShader
{
    private static NoesisShader Shader;

    public NoiseBrush()
    {
        if (Shader == null) Shader = CreateShader();

        SetShader(Shader);
        SetConstantBuffer(_constants);
    }
}
```

The examples *VideoEffect* and *BrushShaders* can be used as guides to implement your own shaders.

![Unity3DTutorialImg30.png](/Unity3DTutorialImg30/png.md)

## Rive assets

[Rive](https://rive.app/) assets (*.riv*) are supported by NoesisGUI starting from version 3.2. These assets are used through the [RiveControl](/App.RiveBase/_RiveControl.md), which provides access to state machine input values and triggers directly from XAML or code-behind.

An [example](https://github.com/Noesis/Tutorials/tree/master/Samples/Rive) is included in the package, fully created with *Rive*, demonstrating integration and animation control.

![Unity3DTutorialImg31.png](/Unity3DTutorialImg31/png.md)

# Data binding

The recommended way to interact with the UI is through [DataBinding](/Gui.Core/DataBindingTutorial.md) between XAMLs and *DataContexts* in code. Unity provides additional flexibility by allowing *MonoBehaviours* to be used as *DataContexts*. This means you can assign and edit the *DataContext* directly in the Unity *Inspector*, making the workflow more intuitive and integrated.

The *DataBinding* example included in the package is a great use-case demonstrating this approach.

![Unity3DTutorialImg41.png](/Unity3DTutorialImg41/png.md)

Another useful extension included in our examples is *NoesisEventCommand*, which connects a *UnityEvent* with a NoesisGUI [ICommand](/Gui.Core/CommandsTutorial.md). This allows you to bind XAML events directly to *MonoBehaviour* methods via the Unity *Inspector*, streamlining the interaction between UI and code.

The *Button* example demonstrates this integration in action.

![Unity3DTutorialImg42.png](/Unity3DTutorialImg42/png.md)

# Input Actions

All *Views* provide a default asset with actions for navigation events. You can create a new asset and assign it to the *View* using the Actions Asset property to customize how input interactions are handled.

![Unity3DTutorialImg21.png](/Unity3DTutorialImg21/png.md)

The following properties are also available on each *View*:

- *Action Map*: Set of actions used by the view and enabled by default.
- *Action Repeat Delay*: The initial delay (in seconds) before a repeated action begins.
- *Action Repeat Rate*: The interval (in seconds) at which a repeated action continues.
- *XR Tracking Origin*: Transform representing the real-world origin for tracking XR devices.
- *Matched Actions*: Displays a list of input actions currently bound to this view. Actions highlighted in red are not mapped to any input action and will not respond during runtime.

# Rendering

The *MonoBehaviour* responsible for rendering XAMLs is *NoesisView*. You must attach this component to a *GameObject*. When attached to a *Camera*, the user interface will render as an overlay layer on top of the camera's output.

To set up UI rendering to a camera, simply drag and drop a XAML asset into the *Scene View*. You can also drag and drop XAMLs directly into the *Hierarchy Window* to create a new UI object in the scene.

![Unity3DTutorialImg4.png](/Unity3DTutorialImg4/png.md)

To display and interact with the user interface, you must enter *Play* mode. While in *Play* mode, the *NoesisView* preview window will display [performance stats](/Gui.Core/Optimizing.md) such as frame rate and memory usage, providing valuable insights to help you optimize your interfaces efficiently. This real-time feedback makes it easier to identify performance bottlenecks and ensure a smooth user experience.

![Unity3DTutorialImg3.png](/Unity3DTutorialImg3/png.md)

## Post-processing

### Legacy Pipeline

By default, camera post processing effects are applied to the UI. In case you don't want this to happen, you need to create a new camera to render NoesisGUI. This camera must have a larger '*Depth*' value and must set '*Clear Flags*' to '*Don't Clear*'. You must also make sure the '*Culling Mask*' is set to '*Nothing*' to avoid rendering 3D elements with this camera.

UNITY BUG

When using Camera Stacking (several cameras rendering to the same render target), make sure the camera rendering the UI has the properties 'Culling Mask' and 'HDR' respectively set to 'Nothing' and 'Off'. This will avoid a bug in the latest versions of Unity.

### Universal Pipeline

In the Universal Render Pipeline (URP), camera post-processing effects are applied to the UI. If you want to render the UI after post-processing, you need to use [Camera Stacking](https://docs.unity3d.com/Manual/urp/cameras/camera-stacking-concepts.html). We recommend the following steps:

- Create a new camera only for the UI and attach a *Noesis View* component to it. Set '*Render Type*' to '*Overlay*' and '*Culling Mask*' to '*Nothing*'. Make sure 'Post Processing' is disabled on this camera.
- Create another camera for post-processing. Set '*Render Type*' to '*Overlay*' and '*Culling Mask*' to '*Nothing*'. Enable the 'Post Processing' checkbox.
- Create an empty *GameObject* with a *Volume* component to define your post-processing effects.
- Attach both cameras to the *Stack* section of the Main Camera. The 'UI camera' must be the last in the list to ensure it renders after post-processing.

![Unity3DTutorialImg50.png](/Unity3DTutorialImg50/png.md)

NOTE

In URP, Noesis View also exposes an 'Injection Point' property that controls when the UI pass is rendered. However, changing this property may not work consistently across all platforms, so we recommend using the steps described above for best compatibility.

### High Definition Pipeline

In the High Definition Render Pipeline (HDRP), camera post-processing does not affect the UI by default. This behavior can be changed using the '*Injection Point*' property exposed by the *Noesis View* component.

![Unity3DTutorialImg51.png](/Unity3DTutorialImg51/png.md)

## Render to texture

In some scenarios, you may want to render the user interface to a texture instead of directly displaying it on the screen or through a camera. NoesisGUI supports this workflow by allowing you to attach a *NoesisView* component to any *GameObject* that is not a camera.

When *NoesisView* is attached to a non-camera object, its *Render Mode* automatically switches to *Render Texture*. This is reflected in the *Render Mode* property of the component. In this mode, a new property called *Target Texture* becomes available, allowing you to specify the *Render Texture* where the UI should be rendered.

To use this feature, create a *Render Texture* asset and assign it to the *Target Texture* field in the *NoesisView*.

Note

We recommend creating the texture using '*Tools -> NoesisGUI -> Create -> Render Texture*' to work around a Unity bug when using linear rendering.
Ensure the created render texture has a stencil buffer enabled. NoesisGUI relies on the stencil for masking UI elements.

![Unity3DTutorialImg61.png](/Unity3DTutorialImg61/png.md)

The texture must also be used by a material assigned to the object's *Mesh Renderer* to display the UI on screen. If you want the UI rendered in the texture to be interactive, the *GameObject* must have a *MeshCollider* component. This allows NoesisGUI to perform hit testing by projecting mouse or touch events onto the texture's surface.

![Unity3DTutorialImg62.png](/Unity3DTutorialImg62/png.md)

The *Widget3D* example included in the package demonstrates how to use *Render Texture* to display UI controls within 3D scenes.

![Unity3DTutorialImg63.png](/Unity3DTutorialImg63/png.md)

### Rendering on demand

By default, in *Render Texture* mode, the property *Continuous Rendering* is disabled to render only when changes happen. This can bring significant performance and power savings.

The *Continuous Rendering* property is not available when rendering to a camera. In this case, a different approach must be followed. The *External Update* property of *NoesisView* must be enabled to activate manual updates. The *Camera* component must be disabled and manually repainted using the following code:

```
public class Redraw : MonoBehaviour
{
   void Update()
   {
      NoesisView view = gameObject.GetComponent<NoesisView>();
      view.ExternalUpdate();

      if (view.NeedsRendering)
      {
         Camera camera = gameObject.GetComponent<Camera>();
         camera.Render();
      }
   }
}
```

## World-Space UI

The user interface can also be rendered directly in 3D, without using render-to-texture. This is the recommended method when you want the UI to be occluded by objects in the 3D scene, or when aiming for the highest visual quality in Virtual Reality.

Note

The property 'World Space UI' must be enabled in the view. It is also recommended to disable PPAA and rely on GPU-based anti-aliasing for better results.

You can place multiple UI elements floating in 3D space, each one attached to a GameObject by using the Noesis World UI component.

![Unity3DTutorialImg64.png](/Unity3DTutorialImg64/png.md)

The following properties are exposed in this component:

- *View*: The Noesis View used to render the specified XAML.
- *XAML*: The UI placed in the GameObject position.
- *Container*: The Name of the Panel container (in the View) where the specified XAML will be inserted.
- *Scale*: Allows scaling UI pixels to scene units.
- *Offset*: Adjust UI position relative to the GameObject.
- *Center*: If enabled centers the UI in the GameObject position.

The Main View must contain a XAML with a container where child UIs are added. The name of the container is specified in the Noesis World UI component. It can be located anywhere in the XAML. For example:

```
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <Canvas x:Name="Root"/>
</Grid>
```

Note

There is an example in the package, 'World Space UI', showing how to setup a basic scene with 3D UI. It is also compatible with XR if the plugin 'XR Plugin Management' is installed.

![Unity3DTutorialImg65.png](/Unity3DTutorialImg65/png.md)

# Hit Testing

In some situations, it is necessary to check whether the mouse is hovering over or has clicked on an element in the UI. This can be achieved using the *HitTest* method available through the *VisualTreeHelper* class.

```
using UnityEngine;
using Noesis;

public class HitTestSample : MonoBehaviour
{
    Visual _root;

    void Start()
    {
        NoesisView view = GetComponent<NoesisView>();
        _root = (Visual)VisualTreeHelper.GetRoot(view.Content);
    }

    void OnMouseDown()
    {
        Vector3 mousePos = Input.mousePosition;
        Point point = _root.PointFromScreen(new Point(mousePos.x, Screen.height - mousePos.y));
        HitTestResult hit = VisualTreeHelper.HitTest(this._root, point);
        if (hit.VisualHit == null)
        {
            // No UI element was hit

            // ...your code here
        }
    }
}
```

# Platform Notes

## iOS

For now, *Bitcode* is not supported, it must be disabled. We recommend disabling it at project level to affect all targets in Xcode.

![Unity3DTutorialImg102.png](/Unity3DTutorialImg102/png.md)

## WebGL

Unity 2023.2+ (Emscripten 3.1.38) is [required](https://docs.unity3d.com/Manual/webgl-native-plugins-with-emscripten.html) for using NoesisGUI with WebGL.

![Unity3DTutorialImg201.png](/Unity3DTutorialImg201/png.md)