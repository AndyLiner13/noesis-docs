Source: https://www.noesisengine.com/docs/Gui.Core.GettingStartedManaged.html

# Getting Started with NoesisGUI C# SDK

The aim of this tutorial is to get you started with the *NoesisGUI C# SDK* and its directory structure. You will learn to build, configure and begin using the SDK to create high-performance managed applications.

# NuGet Repository

Noesis binaries are distributed as [NuGet](https://www.nuget.org/profiles/NoesisTechnologies) packages in the official repository. Packages are subdivided into two big categories: *Noesis*, the *Core* library; and *NoesisApp*, the [Application Framework](ApplicationTutorial.md) used by our samples. Source code for the *Application Framework* is also available at [GitHub](https://github.com/Noesis/Managed).

- Noesis

> - [Core Library](https://github.com/Noesis/Managed/tree/master/Src/Noesis/Core)
> - [Extensions](https://github.com/Noesis/Managed/tree/master/Src/Noesis/Extensions)

- NoesisApp

> - [Core Framework](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/Core)
> - Displays: [Win32](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/Displays/Win32), [WinRT](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/Displays/WinRT), [X11](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/Displays/X11), [UIKit](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/Displays/UIKit), [AppKit](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/Displays/AppKit), [Android.](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/Displays/Android)..
> - RenderContexts: [D3D11](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/RenderContexts/D3D11), [GLX](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/RenderContexts/GLX), [EGL](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/RenderContexts/EGL), [NSGL](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/RenderContexts/NSGL), [WGL](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/RenderContexts/WGL), [MTL](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/RenderContexts/MTL)...
> - [Noesis Theme](https://github.com/Noesis/Managed/tree/master/Src/NoesisApp/Theme)

# Building Samples

The Visual Studio 2017 root solution 'Samples.sln' contains all the examples for the supported platforms. Provided samples in the SDK comes with full source available in the '*/Src*' folder. Each sample also contains a [Blend](BlendTutorial.md) project inside its '*Projects*' folder. For example, the *Blend* project for the *Menu3D* sample is located at '*NoesisSDK/Src/Samples/Menu3D/Projects/blend/Menu3D-blend.csproj*'.

NOTE

Source code for each sample is also available on [GitHub](https://github.com/Noesis/Tutorials). We are happy to accept pull requests.

# Creating Applications

Once you're familiar with our samples, you are ready to start creating your own applications, for this we recommend using the [NoesisGUI C# Project Templates](https://marketplace.visualstudio.com/items?itemName=NoesisTechnologies.NoesisCSharpProjectTemplates) extension for Visual Studio 2022.

When installed, this extension will add a *C# App (NoesisGUI)* template to your new project templates. This template will create projects for Android, iOS, macOS, Windows/Linux (.Net 7.0), and UWP.

The generated solution directory will contain a *Projects* and *Src* folder:

- *Projects* contains a folder for each project. These project folders contain the entry points for each platform, in App.cs, along with platform specific files and configuration.
- *Src* contains all of shared files, including classes, XAML, and assets. Each project recursively updates links to these files when it is reloaded.

NOTE

Android, iOS, and macOS projects require Xamarin to be installed.

For Visual Studio 2022, Xamarin can be found in Visual Studio Installer as an Optional component under .NET Multi-platform App UI development.

For Visual Studio Mac, you will need to download and install the latest release of Xamarin.iOS 16.\* and Xamarin.Mac 9.\*, see [Releases](https://github.com/xamarin/xamarin-macios/releases).