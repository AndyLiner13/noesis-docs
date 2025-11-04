# Differences between NoesisGUI and WPF/UWP

This guide is intended for users coming from XAML architectures like WPF, Silverlight, Xamarin or UWP. Being familiar with those architectures is definitely of great help to start being proficient with NoesisGUI. In the following sections we will analyze what is different in Noesis with respect to other XAML flavors and where you should put the focus if you are migrating projects to Noesis. If you are not familiar with XAML then you can probably skip this tutorial and continue reading the rest of [tutorials](https://www.noesisengine.com/docs/Gui.Core.Index.html#tutorials).

## Noesis is based on WPF

NoesisGUI was designed with WPF in mind. When we started this project we were in love with the architecture of WPF but we wanted it to be faster, optimized for realtime and multiplatform. NoesisGUI was programmed from scratch to be lightweight and without external dependencies. NoesisGUI is so deeply based on WPF that we always recommend the great [WPF Unleashed](https://www.amazon.com/WPF-4-5-Unleased-Adam-Nathan/dp/0672336979) book as the reference manual.

If you are planning to convert a project to NoesisGUI the first thing we recommend is porting your Visual Studio solution to WPF. This will make things easier than directly jumping from other XAMLs platforms like UWP or Xamarin.

There are two conceptually different APIs in NoesisGUI, the Framework API and the Integration API.

### Framework API

This is the API exposing high-level objects like [Controls](https://www.noesisengine.com/docs/Gui.Core.ControlsTutorial.html) and [Panels](https://www.noesisengine.com/docs/Gui.Core.LayoutPanelTutorial.html). It also exposes the corresponding serialization document, the XAML format, a key piece in all the architecture. The Framework API tries to be as similar to WPF as possible. Each version we release gets closer and closer to WPF. In fact any kind of deviation from WPF is considered a bug and you are recommended to file a bug if you encounter such things in Noesis.

If you are using the C# API, the interface is almost the same as in WPF. Being WPF based on C#, our C++ API is a bit different and was adjusted to feel more native. We needed to add key concepts like Reflection, Delegates and Nullables. These details are thoroughly described in the [C++ Architecture Guide](https://www.noesisengine.com/docs/Gui.Core.CppArchitectureGuide.html).

Our [Class Hierarchy](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html) index is language agnostic and exposes all the classes contained in the Integration API. If you want to know if something is implemented in Noesis or not , that's the place you should have a look first.

### Integration API

Noesis Core library is a low-level operating system agnostic component that needs to be provided with information about how to render, how to load resources, how to open [URIs](https://www.noesisengine.com/docs/Gui.Providers._Uri.html) and so on. These tasks correspond to the Integration API, exposed in the IntegrationAPI.h header under the Noesis.GUI namespace. If you are doing an integration of Noesis into your own engine, then you need to understand this API. It is described in great detail in the [Integration Tutorial](https://www.noesisengine.com/docs/Gui.Core.SDKGuide.html). If you are using Noesis in engines like Unity or Unreal then the integration is already done and you don't need to take care about.

We also offer an [Application Framework](https://www.noesisengine.com/docs/Gui.Core.ApplicationTutorial.html) that interacts with the integration API to offer an application model close to WPF with concepts like [Application](https://www.noesisengine.com/docs/App.ApplicationLauncher._Application.html) (App.xaml) and [Window](https://www.noesisengine.com/docs/App.ApplicationLauncher._Window.html) (Window.xaml). This framework is used by all our examples in the C++ and C# SDK.

The connection between the Integration API and the Framework API is performed by a View. A View encapsulates the interaction and rendering of a Visual Tree into a GPU surface. Views are threaded apartments and you can think about them as isolated WPF APIs. They are described with more detail in the [Rendering Architecture](https://www.noesisengine.com/docs/Gui.Core.RenderingTutorial.html) document.

## Noesis is not restricted to WPF

Although based on WPF, NoesisGUI also implements concepts from other XAML flavors in form of [Noesis Extensions](https://www.noesisengine.com/docs/Gui.Core.ExtensionsTutorial.html). These extensions are implemented as part of the Core Library and also exposed as a [NuGet](https://www.nuget.org/packages/Noesis.GUI.Extensions) package to be used in your Blend projects. These Blend extensions are, in many cases, empty implementations just to avoid compile errors in your WPF projects. For example, with NoesisGUI you can render [text with stroke](https://www.noesisengine.com/docs/Gui.Core.TextTutorial.html#color-properties), the corresponding extension in WPF won't render that effect. The source code of these extensions is also available on [GitHub](https://github.com/Noesis/Managed/tree/master/Src/Noesis/Extensions). There you will find extensions like the 3D transformations of Silverlight and the gamepad support of UWP. This set of extensions will keep growing with each new version of NoesisGUI.

## Code-Behind differences

In WPF, Visual Studio automatically generates parts of the [Code-Behind](https://www.noesisengine.com/docs/Gui.Core.CodeBehindTutorial.html) and stores them in hidden .g.cs files. This is not automatically done, at least not for now, in NoesisGUI. You must manually connect events and find elements by name in the [Code-Behind](https://www.noesisengine.com/docs/Gui.Core.CodeBehindTutorial.html) as described in the [Events](https://www.noesisengine.com/docs/Gui.Core.EventsTutorial.html) tutorial.

We recommend using preprocessor macros to handle these differences:

```csharp
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
    }

#if NOESIS
    TextBox Address;
    TextBlock EntryTitle;
    TextBlock EntryDesc;

    private void InitializeComponent()
    {
        GUI.LoadComponent(this, "MainWindow.xaml");

        this.Address = (TextBox)FindName("Address");
        this.EntryTitle = (TextBlock)FindName("EntryTitle");
        this.EntryDesc = (TextBlock)FindName("EntryDesc");
    }
#endif
}
```

## Namespaces differences

All framework classes are defined inside the Noesis namespace in NoesisGUI. This is different in WPF, where classes are spread between multiple namespaces.

```csharp
#if NOESIS
    using Noesis;
#else
    using System;
    using System.Windows;
    using System.Windows.Controls;
#endif
```

## Rendering differences

NoesisGUI is optimized for rendering dynamic interfaces and WPF is optimized for static high-quality interfaces. While WPF uses complex algorithms to render vectors at a perfect antialiasing quality, NoesisGUI renders the interface as a videogame engine. Almost all of our interfaces are rendered entirely per frame without using Bitmap caching. A modern and GPU aware UI middleware must be prepared to paint every pixel on every frame. You can find more details about this in the article we published on Gamasutra: [Defining the next generation of user interfaces](https://www.gamasutra.com/view/news/315057/Sponsored_Defining_the_next_generation_of_user_interfaces.php).

## Performance tradeoffs

Being NoesisGUI a multi-platform library, a few tradeoffs must be taken to render efficiently across all the range of supported devices: from low-end mobiles to high-performance game consoles.

### Floats

WPF uses doubles for almost all its fixed-point properties while NoesisGUI uses float for the same properties. For example, the ActualWidth property of FrameworkElement is a double in WPF but a float in NoesisGUI. If you are using the C# SDK and sharing the project between WPF and Noesis we recommend using an alias to encapsulate this difference.

```csharp
#if NOESIS
    using Float = System.Single;
#else
    using Float = System.Double;
#endif

private void Slider_ValueChanged(object sender, RoutedPropertyChangedEventArgs<Float> e);
private void UpdateColor(Float r, Float g, Float b, Float a);
```

### Exceptions

Being NoesisGUI a C++ core library optimized for performance, code is compiled with Exceptions and RTTI disabled. This means that in comparison with WPF, Noesis won't raise exceptions to notify about errors. In almost all cases, errors in Noesis are non-fatal and the execution of the program can continue after sending information about it to the user callback that is set up at initialization time.

In contrast, the C# layer built on top of the C++ uses exception to notify about critical errors that happens in the communication between those two layers.

## Application Dictionary

The Application Dictionary is the [ResourceDictionary](https://www.noesisengine.com/docs/Gui.Core._ResourceDictionary.html) you find inside App.xaml in a WPF application.

```xml
<Application xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">
  <Application.Resources>
    <ResourceDictionary>
      <SolidColorBrush x:Key="Background0" Color="#FF2F3F4F" />
      <SolidColorBrush x:Key="Background1" Color="SlateGray" />
      <SolidColorBrush x:Key="Foreground0" Color="White" />
      <SolidColorBrush x:Key="Foreground1" Color="SkyBlue" />
      <SolidColorBrush x:Key="Foreground2" Color="Black" />
      <SolidColorBrush x:Key="Border" Color="LightSlateGray" />
    </ResourceDictionary>
  </Application.Resources>
</Application>
```

An Application-Scope Resource Dictionary shared between all your XAMLs is one of the recommendations to optimize loading times and memory usage. The Integration API exposes Noesis::GUI::SetApplicationResources for this purpose. More information about how to set up a global style can be found in the [Styling Tutorial](https://www.noesisengine.com/docs/Gui.Core.StylingTutorial.html#global-style).

## Themes

By default, WPF uses the theme provided by the operating system. In Noesis we don't use the operating system for this. A minimalistic theme supporting all core controls is provided by default embedded in the core library. This explains why, by default, the render generated by Blend and by Noesis is different. In case you want our default theme in Blend you need to override it when the application is initialized. For example:

```csharp
public partial class App : Application
{
    public App()
    {
        // NoesisTheme added to Application.Resources to have same look as Noesis
        ResourceDictionary theme = (ResourceDictionary)LoadComponent(new Uri("NoesisTheme.xaml", UriKind.Relative));
        Resources.MergedDictionaries.Insert(0, theme);
    }
}
```

NoesisTheme.xaml is part of the Extensions package available in [NuGet](https://www.nuget.org/packages/Noesis.GUI.Extensions).