Source: https://www.noesisengine.com/docs/Gui.Core.GettingStartedNative.html

# Getting Started with NoesisGUI C++ SDK

The aim of this tutorial is to get you started with the *NoesisGUI C++ SDK* and its directory structure. You will learn to build, configure and begin using the SDK to create high-performance native applications.

In the root directory of the SDK you can find [XamlPlayer](FirstSteps.md), a useful tool to quickly do your first UI experiments.

NOTE

In the root directory you can also find 'SDKBrowser', an application that will give you a quick overview of the SDK

# Building Samples

All provided samples in the SDK, including the [Application Framework](ApplicationTutorial.md), comes with full source. There is a solution for each platform inside the '*NoesisSDK/Build/*' directory for building all the examples. For example, *Visual Studio* solution for 64-bits can be found at '*NoesisSDK/Build/NoesisGUI-win-x86\_64.sln*'.

Each sample also contains a [Blend](BlendTutorial.md) solution inside its '*Data*' folder. For example, the *Blend* project for the *Menu3D* sample is located at '*NoesisSDK/Src/Packages/Samples/Menu3D/Data/Menu3D-blend.sln*'.

NOTE

Source code for each sample is also available on [GitHub](https://github.com/Noesis/Tutorials). We are happy to accept pull requests.

Three configurations are available for each project:

- **Debug**: with asserts, logging, instrumentation and inspector enabled.
- **Profile**: fully optimized, minimal logging, instrumentation and inspector enabled.
- **Release**: fully optimized, LTO in many platforms.

## Building Windows / UWP

[Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/) 2015+ is needed. Just open the solution (.sln) and build the desired configuration.

## Building macOS / iOS

[XCode](https://developer.apple.com/xcode/) 11.4+ is needed. Just open the workspace (.xcworkspace) and build the desired configuration.

## Building Linux

- [Ubuntu](https://ubuntu.com) 20.04 LTS
- [GNU Make](https://www.gnu.org/software/make/) 4.2.1+
- [GCC](https://gcc.gnu.org/) 9.3.0+

Make sure to install GL and X11 headers:

```
> sudo apt-get install mesa-common-dev libx11-dev
```

With all prerequisites satisfied just build the generated makefile (.mk) for the desired configuration.

```
> make -f NoesisGUI-linux-x86_64.mk CONFIG=Release
```

## Building WebGL

- [GNU Make](https://www.gnu.org/software/make/) 4.2.1+ is needed.
- [Emscripten](https://emscripten.org/) 3.1.39+

Make sure 'emcc', 'em++' and 'emar' are [available](https://emscripten.org/docs/getting_started/Tutorial.html#tutorial) from the command promp and just build the makefile (.mk) for the desired configuration.

```
> make -f NoesisGUI-wasm.mk CONFIG=Release
```

## Building Android

- [GNU Make](https://www.gnu.org/software/make/) 4.2.1+ is needed
- [JDK 22+](https://www.oracle.com/java/technologies/javase-downloads.html)
- [Android NDK](https://developer.android.com/ndk) r28.1+ has been tested with the following package versions:

> | Path | Version | Description | Location |
> | --- | --- | --- | --- |
> | build-tools;36.0.0 | 36.0.0 | Android SDK Build-Tools 36 | build-tools\36.0.0 |
> | ndk;28.1.13356709 | 28.1.13356709 | NDK (Side by side) 28.1.13356709 | ndk\28.1.13356709 |
> | platform-tools | 35.0.2 | Android SDK Platform-Tools | platform-tools |
> | platforms;android-36 | 2 | Android SDK Platform 36 | platforms\android-36 |

- The following environment variables must be set:

> - **ANDROID\_NDK** must point to NDK (eg: *C:\Android\SDK\ndk\28.1.13356709*)
> - **ANDROID\_PLATFORM** must point to SDK platforms (eg: *C:\Android\SDK\platforms\android-36*)
> - **JAVA\_HOME** must point to Java installation path (eg: *C:\Program Files\Java\jdk-22*)

- The following binaries must be available in **PATH** environment variable:

> - ndk prebuilt toolchains: clang, clang++, llvm-strip, llvm-objcopy
> - java compiler: javac
> - build-tools: d8, aapt, zipalign, apksigner
> - platform-tools: adb

With all prerequisites satisfied just build the generated makefile (.mk) for the desired configuration.

```
> make -f NoesisGUI-android-arm.mk CONFIG=Release
```

# Running Samples

Binaries are generated in '*NoesisSDK/Bin/*'. There is one sub-folder for each supported platform. For example, *Menu3D* sample for Windows 64-bits will be generated at '*NoesisSK/Bin/windows\_x86\_64/Samples.Menu3D.exe*'.

All our samples are built using the [Application Framework](ApplicationTutorial.md) and support common functionality like:

- The following command line switches:
  - **--render [D3D11|GL|Metal|...]**: overrides the default renderer.
  - **--vsync [0|1]**: disables vertical synchronization.
  - **--samples N**: enables multisample anti-aliasing (MSAA), by default it is off.
  - **--ppaa [0|1]**: enables [cheap antialiasing](AntialiasingTutorial.md#per-primitive-antialiasing) anti-aliasing (enabled by default).
  - **--linear**: for switching to [linear rendering](http://www.kinematicsoup.com/news/2016/6/15/gamma-and-linear-space-what-they-are-how-they-differ), by default rendering happens in gamma space.
  - **--lcd [0|1]**: enables subpixel rendering compatible with LCD displays.
  - **--log\_binding**: to increase the verbosity of logging when using data binding.
  - **--emulate\_touch**: enables emulation of touch input from mouse events.
  - **--root dir\_path**: to read resources from the specified filesystem path (for [hot-reloading](HotReloadTutorial.md#hot-reload-in-sdk-samples)).
- The following Shortcut keys:
  - **CTRL + T**: display the debug toolbar.
  - **CTRL + W**: toggles wireframe mode when rendering triangles.
  - **CTRL + B**: each batch submitted to the GPU is given a unique solid color.
  - **CTRL + O**: display pixel overdraw using blending layers. Different colors are used for each type of triangle: *green* for normal, *red* for opacities and *blue* for clipping masks.
  - **CTRL + P**: [per-primitive Antialiasing](AntialiasingTutorial.md#per-primitive-antialiasing) extrudes the contours of the geometry and smooths them. Useful when GPU multisampling is not enabled.
  - **CTRL + F**: display a [performance](Optimizing.md) stats panel.
  - **F10**: takes a [RenderDoc](https://renderdoc.org/) capture.

# Creating Applications

Once you get familiar with our samples you are ready to start creating your own applications. For that purpose we highly recommend reading the following documents:

- The [C++ Architecture Guide](CppArchitectureGuide.md), to learn about NoesisGUI C++ architecture.
- The [Integration guide](SDKGuide.md), to discover how to integrate NoesisGUI into your own application.

# VSCode Extension

We also provide a [Visual Studio Code Extension](https://noesisengine.com/vscode), which provides a rich editing experience for the XAML documents, using the NoesisGUI language server. For more information on the language server, see our [Language Server tutorial](LanguageServer.md)