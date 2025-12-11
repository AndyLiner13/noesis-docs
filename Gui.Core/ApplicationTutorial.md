Source: https://www.noesisengine.com/docs/Gui.Core.ApplicationTutorial.html

# Application Framework

![github](https://www.noesisengine.com/docs/github.png) [Tutorial Data](https://github.com/Noesis/Tutorials/tree/master/Samples/ApplicationTutorial)

![ApplicationTutorialImg1.png](https://www.noesisengine.com/docs/ApplicationTutorialImg1.png)

Although noesisGUI can be fully integrated within your application, as shown in the [integration](SDKGuide.md) tutorial, an *Application Framework* is also provided. This framework is an *Open Source* library that provides abstractions to create multiplatform applications. The framework is a good example about how to use Noesis and it provides many helpers that can be useful. All our public samples use the application framework.

The extensions provided, like [Application](../App.ApplicationLauncher/_Application.md) and [Window](../App.ApplicationLauncher/_Window.md), are compatible with WPF, so compatible with *Microsoft Blend*. Using the application framework you can design applications that will indistinctly run in a Windows window, macOS window, iPhone screen, or Xbox TV for example. The framework supports all the platforms where NoesisGUI is available.

The following is a list of the functionality exposed by the *Application Framework*:

- Multiplatform abstractions for [Application](../App.ApplicationLauncher/_Application.md) and [Window](../App.ApplicationLauncher/_Window.md).
- Multiplatform handling of input events: keyboard, mouse, touch, gamepads and VR controllers.
- Support for playing sounds.
- Video playback functionality using the [MediaPlayer](../App.MediaElement/_MediaPlayer.md).
- [Resource Providers](ProvidersTutorial.md) implementation for loading assets.
- [Noesis Theme](#noesis-theme).
- Render implementations for each supported graphics API.
- [ShaderCompiler](#shader-compiler) tool.
- [Shader Effects and Brushes](ShadersTutorial.md).
- The [Interactivity](../App.Interactivity/Behaviors.md) package.
- A [Language Server](LanguageServer.md) compatible with [Visual Studio Code](https://noesisengine.com/vscode).

NOTE

Application Framework provides the functionality needed by our samples and tutorials. It should be never used as a 'Production Ready' library. Clients should take the code as a starting point that must be adapted and tweaked for each specific scenario.

# Headers and Namespace

Headers for the application framework are contained within the *NsApp* and *NsRender* modules. The API is exposed in the *NoesisApp* namespace.

```
#include <NsApp/EntryPoint.h>
#include <NsApp/Application.h>
#include <NsApp/ApplicationLauncher.h>
#include <NsApp/Window.h>
#include <NsApp/EmbeddedXamlProvider.h>
#include <NsApp/EmbeddedFontProvider.h>

using namespace Noesis;
using namespace NoesisApp;
```

NOTE

Note how framework headers are not inside standard NoesisGUI include folder neither part of 'NoesisPCH.h' precompiled header.

# Entry Point

As *main()* is not available in all platforms, the framework provides a portable entry point, *NsMain*. You will normally create here a *Launcher*, configure it and *Run()* it.

```
int NsMain(int argc, char **argv)
{
    AppLauncher launcher;
    launcher.SetArguments(argc, argv);
    launcher.SetApplicationFile("App.xaml");
    return launcher.Run();
}
```

# Launcher

The *Launcher* is the first instance you create. It is in charge of application initialization and main message loop. It also provides a few important overridable functions:

- *RegisterComponents*: for registering classes in the component factory. Each extended class that need to be instantiated by XAML needs to be registered here as explained in the [Extending NoesisGUI](ExtendingTutorial.md) tutorial. For the framework you need to register at least the *Application* and *Window* class.
- *GetXamlProvider*, *GetFontProvider* and *GetTextureProvider*: for customizing how resources are loaded. You can install custom handlers for XAMLs, font and textures as explained in the [Customizing Resource Loading](ProvidersTutorial.md) tutorial.

```
class AppLauncher final: public ApplicationLauncher
{
private:
    void RegisterComponents() const override
    {
        RegisterComponent<RssReader::App>();
        RegisterComponent<RssReader::MainWindow>();
    }

    Ptr<XamlProvider> GetXamlProvider() const override
    {
        EmbeddedXaml xamls[] =
        {
            { "App.xaml", App_xaml },
            { "MainWindow.xaml", MainWindow_xaml }
        };

        return *new EmbeddedXamlProvider(xamls);
    }

    Ptr<FontProvider> GetFontProvider() const override
    {
        EmbeddedFont fonts[] =
        {
            { "", Roboto_Regular_ttf },
            { "", Roboto_Bold_ttf }
        };

        return *new EmbeddedFontProvider(fonts);
    }
};
```

NOTE

The Embedded family of resource providers found in the framework allows you to embed resources in the executable. Each time you edit a resource contained in the project it is automatically converted to a header file using 'bin2h', an tool distributed with each sample. For example, 'Roboto-Regular.ttf.bin.h' is automatically regenerated each time 'Roboto-Regular.ttf' changes. The same for the rest of resources.

# Application

The [Application](../App.ApplicationLauncher/_Application.md) class directly correspond to the [WPF Application Class](https://msdn.microsoft.com/en-us/library/system.windows.application(v=vs.110).aspx). Each application provides its own implementation inheriting from *Application* base class.

```
namespace RssReader
{
    class App final: public Application
    {
        NS_IMPLEMENT_INLINE_REFLECTION_(App, Application, "RssReader.App")
    };
}
```

The main purpose of the *Application* is providing a global resource dictionary and setting the main window, the *StartupUri*.

App.xaml

```
<Application
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  StartupUri="MainWindow.xaml"
  x:Class="RssReader.App">

<Application.Resources>
  <ResourceDictionary>
    <ResourceDictionary.MergedDictionaries>
      <ResourceDictionary Source="Theme/NoesisTheme.DarkBlue.xaml"/>
    </ResourceDictionary.MergedDictionaries>
    <SolidColorBrush x:Key="Background0" Color="#FF2F3F4F"/>
    <SolidColorBrush x:Key="Background1" Color="SlateGray"/>
    <SolidColorBrush x:Key="Foreground0" Color="White"/>
    <SolidColorBrush x:Key="Foreground1" Color="SkyBlue"/>
    <SolidColorBrush x:Key="Foreground2" Color="Black"/>
    <SolidColorBrush x:Key="Border0" Color="LightSlateGray"/>
  </ResourceDictionary>
</Application.Resources>

</Application>
```

# Window

The [Window](../App.ApplicationLauncher/_Window.md) class mimics the [WPF Window Class](https://msdn.microsoft.com/en-us/library/system.windows.window(v=vs.110).aspx). It is a container that shows its content inside an operating system window. Public properties like *Title*, *ResizeMode*, *WindowStyle*, *Width* and *Height* control the aspect of the native window.

MainWindow.xaml

```
<Window
   xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
   Title="NoesisGUI - RSS Reader" Width="487" Height="630" ResizeMode="NoResize"
   Background="{StaticResource Background0}"
   Foreground="{StaticResource Foreground0}"
   FontFamily="{StaticResource DefaultFont}"
   x:Class="RssReader.MainWindow">

  <Viewbox>
    <DockPanel Background="{StaticResource Background0}" LastChildFill="True"
               KeyboardNavigation.TabNavigation="Contained"
               KeyboardNavigation.DirectionalNavigation="Contained" Width="325" Height="420">
      <TextBlock DockPanel.Dock="Top" Text="RSS Reader" FontSize="32" FontWeight="Bold"
                 TextAlignment="Center" Margin="0,10,0,0"/>
      <Border DockPanel.Dock="Top" Background="{StaticResource Background1}"
              BorderBrush="{StaticResource Border}" BorderThickness="1" CornerRadius="2"
              Margin="10" Padding="15,5">
        <Grid>
          <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto"/>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="Auto"/>
          </Grid.ColumnDefinitions>
          <TextBlock Grid.Column="0" Text="URL: " VerticalAlignment="Center"/>
          <TextBox x:Name="Address" Grid.Column="1" Text="http://www.metacritic.com/"/>
          <Button x:Name="GoTo" Grid.Column="2" Content="Go" Click="OnGoToClicked" Margin="2,0,0,0"/>
        </Grid>
      </Border>
      <Grid DockPanel.Dock="Bottom" Margin="10">
        <Grid.ColumnDefinitions>
          <ColumnDefinition/>
          <ColumnDefinition/>
        </Grid.ColumnDefinitions>
        <Grid.Resources>
          <Style TargetType="Button">
            <Setter Property="BorderBrush" Value="{StaticResource Background1}"/>
          </Style>
        </Grid.Resources>
        <Button x:Name="Prev" Grid.Column="0" Content="Prev" Click="OnPrevClicked"/>
        <Button x:Name="Next" Grid.Column="1" Content="Next" Click="OnNextClicked"/>
      </Grid>
      <Border Background="{StaticResource Background1}" BorderBrush="{StaticResource Border}"
              BorderThickness="1" CornerRadius="2" Margin="10,0" Padding="5">
        <Grid x:Name="ContentPanel" Margin="10,0">
          <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="*"/>
          </Grid.RowDefinitions>
          <TextBlock x:Name="EntryTitle" Grid.Row="0" FontSize="20" FontWeight="Bold"
                     Foreground="{StaticResource Foreground1}" TextAlignment="Center" Margin="0,5,0,5"/>
          <ScrollViewer Grid.Row="1"  Margin="0,10" Focusable="False"
                        HorizontalScrollBarVisibility="Disabled" VerticalScrollBarVisibility="Auto">
            <TextBlock x:Name="EntryDesc" TextWrapping="Wrap" Margin="10,0"
                       Foreground="{StaticResource Foreground2}" FontSize="14"/>
          </ScrollViewer>
        </Grid>
      </Border>
    </DockPanel>
  </Viewbox>

</Window>
```

*Window* base class is normally extended to implement [code-behind](CodeBehindTutorial.md) functionality.

```
namespace RssReader
{
    class MainWindow final: public Window
    {
    public:
        MainWindow(): _index(0)
        {
            InitializeComponent();

            _title = FindName<TextBlock>("EntryTitle");
            _title->SetText(gTitles[0]);

            _desc = FindName<TextBlock>("EntryDesc");
            _desc->SetText(gBodies[0]);
        }

    private:
        void InitializeComponent()
        {
            Noesis::GUI::LoadComponent(this, "MainWindow.xaml");
        }

        bool ConnectEvent(BaseComponent* source, const char* event, const char* handler) override
        {
            NS_CONNECT_EVENT(Button, Click, OnGoToClicked);
            NS_CONNECT_EVENT(Button, Click, OnPrevClicked);
            NS_CONNECT_EVENT(Button, Click, OnNextClicked);
            return false;
        }

        void OnGoToClicked(BaseComponent* /*sender*/, const RoutedEventArgs& /*e*/)
        {
        }

        void OnPrevClicked(BaseComponent* /*sender*/, const RoutedEventArgs& /*e*/)
        {
            _index = _index == 0 ? 2 : _index - 1;
            _title->SetText(gTitles[_index]);
            _desc->SetText(gBodies[_index]);
        }

        void OnNextClicked(BaseComponent* /*sender*/, const RoutedEventArgs& /*e*/)
        {
            _index = _index == 2 ? 0 : _index + 1;
            _title->SetText(gTitles[_index]);
            _desc->SetText(gBodies[_index]);
        }

    private:
        int _index;
        TextBlock* _title;
        TextBlock* _desc;

        NS_IMPLEMENT_INLINE_REFLECTION(MainWindow, Window)
        {
            NsMeta<TypeId>("RssReader.MainWindow");
        }
    };
}
```

# Noesis Theme

Included in the framework, there is a rich-featured theme with support for *Accent* colors and *Dark* and *Light* modes. To use it, just add our [Noesis.GUI.Extensions](https://www.nuget.org/packages/Noesis.GUI.Extensions) NuGet package to the Blend project and reference the theme in the application resources.

| Dark Modes | Light Modes |
| --- | --- |
| NoesisTheme.DarkRed.xaml | NoesisTheme.LightRed.xaml |
| NoesisTheme.DarkGreen.xaml | NoesisTheme.LightGreen.xaml |
| NoesisTheme.DarkBlue.xaml | NoesisTheme.LightBlue.xaml |
| NoesisTheme.DarkOrange.xaml | NoesisTheme.LightOrange.xaml |
| NoesisTheme.DarkEmerald.xaml | NoesisTheme.LightEmerald.xaml |
| NoesisTheme.DarkPurple.xaml | NoesisTheme.LightPurple.xaml |
| NoesisTheme.DarkCrimson.xaml | NoesisTheme.LightCrimson.xaml |
| NoesisTheme.DarkLime.xaml | NoesisTheme.LightLime.xaml |
| NoesisTheme.DarkAqua.xaml | NoesisTheme.LightAqua.xaml |

App.xaml

```
<Application>
  <Application.Resources>
    <ResourceDictionary Source="pack://application:,,,/Noesis.GUI.Extensions;component/Theme/NoesisTheme.DarkBlue.xaml" />
  </Application.Resources>
</Application>
```

![NoesisTheme.png](https://www.noesisengine.com/docs/NoesisTheme.png)

# Command Line Switches

The following command line switches are supported by all applications created with the *Application Framework*:

- **--render [D3D11|GL|Metal|...]**: overrides the default renderer.
- **--vsync [0|1]**: disables vertical synchronization.
- **--samples N**: enables multisample anti-aliasing (MSAA), by default it is off.
- **--ppaa [0|1]**: enables [cheap antialiasing](AntialiasingTutorial.md#per-primitive-antialiasing) anti-aliasing (enabled by default).
- **--linear**: for switching to [linear rendering](http://www.kinematicsoup.com/news/2016/6/15/gamma-and-linear-space-what-they-are-how-they-differ), by default rendering happens in gamma space.
- **--lcd [0|1]**: enables subpixel rendering compatible with LCD displays.
- **--log\_binding**: to increase the verbosity of logging when using data binding.
- **--emulate\_touch**: enables emulation of touch input from mouse events.
- **--root dir\_path**: to read resources from the specified filesystem path (for hot-reloading).

# Shortcut Keys

The following shortcuts enable debugging functionality to inspect the performance of your application:

- **CTRL + T**: displays the debug toolbar.
- **CTRL + W**: toggles wireframe mode when rendering triangles.
- **CTRL + B**: each batch submitted to the GPU is given a unique solid color.
- **CTRL + O**: displays pixel overdraw using blending layers. Different colors are used for each type of triangle: *green* for normal, *red* for opacities and *blue* for clipping masks.
- **CTRL + P**: [per-primitive Antialiasing](AntialiasingTutorial.md#per-primitive-antialiasing) extrudes the contours of the geometry and smooths them. Useful when GPU multisampling is not enabled.
- **CTRL + F**: display a [performance](Optimizing.md) stats panel.
- **F10**: takes a [RenderDoc](https://renderdoc.org/) capture.

# Shader Compiler

The *ShaderCompiler* command line tool is used to compile pixel shaders for the different graphics platforms supported by Noesis. The shader language is based on HLSL and it uses preprocessor macros to transform this language into other platforms.

The following defines are available for each supported platform:

| Define symbol | Graphics API |
| --- | --- |
| TARGET\_HLSL | D3D11, D3D12 |
| TARGET\_GLSL | OpenGL |
| TARGET\_ESSL | OpenGL ES, WebGL |
| TARGET\_SPIRV | Vulkan |
| TARGET\_MTL | Apple Metal |
| TARGET\_PSSL\_ORBIS | PlayStation 4 |
| TARGET\_PSSL\_PROSPERO | PlayStation 5 |
| TARGET\_NVN | Nintendo Switch |

Some differences between vanilla HLSL and ShaderCompiler language:

- Types *half4*, *half3*, *half2* and *half* are used for mediump precision.
- Types *fixed4*, *fixed3*, *fixed2* and *fixed* are used for lowp precision.
- Uniforms constants are enclosed in a global *uniforms* structure.
- For [Brushes](_BrushShader.md), the header 'BrushHelpers.h' must be used.
- For [Effects](_ShaderEffect.md), the header 'EffectsHelper.h' must be used.
- The entry point is *main\_brush* for [Brushes](_BrushShader.md) and *main\_effect* for [Effects](_ShaderEffect.md).

The different between brushes and effects is described in this [Shader tutorial](ShadersTutorial.md).

The following code is an example of *Brush*:

Monochrome.noesisbrush

```
#include "BrushHelpers.h"

uniforms
{
    fixed4 _color;
};

fixed4 main_brush(float2 uv)
{
    fixed4 c = SampleImage(uv);
    fixed l = c.r * 0.30 + c.g * 0.59 + c.b * 0.11;
    return float4(_color.r * l, _color.g * l, _color.b * l, c.a);
}
```

And this is an example of an *Effect*:

Tint.noesiseffect

```
#include "EffectHelpers.h"

uniforms
{
    fixed4 _color;
};

fixed4 main_effect()
{
    fixed4 c = GetInput();

    return float4
    (
        c.r * _color.r,
        c.g * _color.g,
        c.b * _color.b,
        c.a + _color.a * (1.0f - c.a)
    );
}
```