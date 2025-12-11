Source: https://www.noesisengine.com/docs/Gui.Core.Changelog_v20.html

# NoesisGUI 2.0 Changelog

# Version 2.0.2f2

- Enhancement Thread affinity checks added to ensure objects are accessed from the correct thread.
- Enhancement Improved [Setter](_Setter.md), [Trigger](_Trigger.md) and [Condition](_Condition.md) error messages when value type is incorrect.
- Fixed C# Crash during shutdown deleting C# proxies still having a C++ reference.

# Version 2.0.2f1

- Feature Support for Xbox One in Unity.
- Feature Unity Support for game pads ([more info](Unity3DTutorial.md#game-pad)).
- Feature Implemented [Underline](_Underline.md) and [Hyperlink](_Hyperlink.md) inlines.
- Enhancement Linux platform is back again in NoesisGUI 2.0.
- Enhancement Improved D3D11 renderer to support *Fast Semantics* in Xbox One.
- Enhancement Improvement parallelism between *Update* and *Render* allowing separate frequencies.
- Enhancement XamlParser reporting as error unknown properties or events (was a warning before).
- Enhancement Added cursor property to [TextBox](_TextBox.md), [PasswordBox](_PasswordBox.md) and [Hyperlink](_Hyperlink.md) in our styles.
- Documentation Improved [performance optimization tutorial](Optimizing.md).
- Documentation [UserControl tutorial](UserControlTutorial.md) adapted to NoesisGUI 2.0.
- Documentation [Unity3D tutorial](Unity3DTutorial.md) improved with mentions to game pads and texture import settings.
- Fixed OpenGL renderer no longer leaving internal objects bound in client code (to avoid potential modifications).
- Fixed OpenGL renderer incorrectly casting glGetUniformLocation() to Int8.
- Fixed glDiscardFramebufferEXT incorrectly used in OpenGL ES 2.0.
- Fixed Rendering issue with half float vertices in OpenGL ES 2.0.
- Fixed Crash when setting *Projection* or *RenderTransform* properties to null.
- Fixed Crash when pressing space in a focused [ComboBox](_ComboBox.md).
- Fixed Unity Textures with mipmaps rendering as black.
- Fixed Unity Editor process never ending in OSX sometimes.
- Fixed Unity Offscreen rendering not working properly in a few scenarios.
- Fixed Unity Xaml post processor not detecting property values with single quotes.
- Fixed Unity Caret disabled when software keyboard is shown in iOS.
- Fixed C# Deletion of native proxies was not thread-safe (infrequent random crashes).

# Version 2.0.1f1

- Feature *Cursor* property implemented in [FrameworkElement](_FrameworkElement.md). *SetCursorCallback* added to integration API.
- Enhancement Support for RGBA8 and RGB besides BGRA8 in [BitmapSource](_BitmapSource.md).
- Enhancement Improved error messages in XAML parser. Added line and column information whenever possible.
- Enhancement Improved how [BindingExpression](_BindingExpression.md) unregister sources to avoid unexpected errors.
- Enhancement Added support for absolute URIs starting with '/' or a drive letter 'C:/'. [URIs](../Gui.Providers/_Uri.md) tutorial updated.
- Enhancement Two-way bindings from *Float* to *Text* are now using proper roundtrip conversion to avoid imprecisions.
- Enhancement C# Compilation issues for .NETCore.
- Enhancement C++ Support for passing user data to cursor and keyboard callbacks in *IntegrationAPI*.
- Enhancement NoesisGUI is now compatible with Unity 5.6.
- Fixed [ContextMenu](_ContextMenu.md) no longer allowing logical or visual parent.
- Fixed Some *ItemsControl* default templates were not using [ItemsPresenter](_ItemsPresenter.md).
- Fixed Crash closing application while [ContextMenu](_ContextMenu.md) open.
- Fixed Registered named elements not found when [UserControl](_UserControl.md) is root of a template.
- Fixed Storyboard cannot be empty.
- Fixed *FrameworkPropertyMetadata* allowed negative values for options parameter.
- Fixed Crash accessing destroyed element when binding source *NameScope* changed.
- Fixed Crash when setting an invalid identifier to *x:Name* property.
- Fixed Crash binding *TwoWay* or *OneWayToSource* to read only properties.
- Fixed [UserControl](_UserControl.md) inside a template was ignoring any *Resource* or *Trigger* defined in the associated XAML.
- Fixed *Caret* selection and positioning was wrong in multiline [TextBox](_TextBox.md).
- Fixed C++ Our delegates no longer give error when removing non existent callbacks.
- Fixed Crash when accessing nonexistent static resource.
- Fixed Crash in [TextBlock](_TextBlock.md) due to uninitialized software keyboard callbacks.
- Fixed Crash when using invalid FontFamily in a XAML.
- Fixed Unity annoyingly crashing continuously when a LoadXaml() was crashing first time.
- Fixed Unity *NoesisView* inspector was not marking asset as dirty when modified.
- Fixed Unity Crash when registering enum properties and setting incorrect default value type.
- Fixed Unity Initialization automatically done first time any PInvoke function is used.
- Fixed Unity 'Reimport All' button in settings is now working properly.
- Fixed Unity *EnablePostProcess* property deprecated. Must use multiple cameras now. Unity [tutorial](Unity3DTutorial.md) updated.
- Fixed Unity Offscreen phase is now always done before rendering *any* camera.
- Fixed Unity Fixed vertical flipping issue with Unity 5.6.

# Version 2.0.0f1

- Doc Unity [tutorial](Unity3DTutorial.md) documentation updated.
- Enhancement Unity Support for dragging XAMLs into Scene and Hierarchy.
- Enhancement Unity Better error messages when importing XAMLs.
- Enhancement Unity More examples: *DataTriggers* and *ControlGallery*.
- Enhancement XamlPlayer included in the native SDK.
- Fixed Unity Offscreen rendering not working when removing all lights.
- Fixed Improved handling of corrupted fonts.

# Version 2.0.0rc1

- PS4 C++ New platform supported.
- Enhancement Improved the batching algorithm with optimal number of draw calls in many scenarios.
- Enhancement Optimized stencil usage trying to avoid it whenever possible.
- Enhancement C# Resource providers exposed to customize how XAMLs, textures and fonts are loaded.
- Enhancement C# Support for multiple initializations in *Noesis.GUI.Init()*.
- Enhancement C# Support for hot reloading of assemblies.
- Enhancement C# Renamed *DependencyProperty()* parameter names to match WPF.
- Enhancement C# Support for readonly keyword in static *DependencyProperties*.
- Enhancement C# *FontStretches*, *FontStyles* and *FontWeights* added.
- Enhancement C# *RenderOptions.BitmapScalingMode* is now available.
- Enhancement C# *Texture* class exposed with methods to wrap native texture pointers (*ID3D11Texture\** and *GLuint*).
- Enhancement *StreamGeometry.ToString* implemented as in WPF.
- Enhancement Support for destroying *IView* and *IRenderer* independently to avoid having to wait for the render thread.
- Enhancement Added support for *Paste* and *SelectAll* commands in [PasswordBox](_PasswordBox.md).
- Enhancement Support for showing [ToolTip](_ToolTip.md) on disabled elements.
- Fixed Stencil artifacts when batching primitives.
- Fixed C# String property callbacks were not correctly converting between UTF8 and Unicode.
- Fixed [TextBox](_TextBox.md) inside [ListBox](_ListBox.md) was losing focus when space key was pressed.

# Version 2.0.0b4

- Feature Apple Metal renderer. Integration sample added to SDK.
- Feature Implemented support for events in code-behind. New tutorial on [events](EventsTutorial.md).
- Feature C++ Tessellation optimizations to *DrawingContext*:
  - All geometries must be drawn using *DrawingContext::DrawGeometry*.
  - Deprecated *DrawLine*, *DrawEllipse*, *DrawRectange* and *DrawRoundedRectangle*.
  - *MeshGeometry* is a new kind of geometry for drawing pre-tessellated paths.
- Enhancement C++ Support for non-fatal (recoverable) errors. Execution can continue after this kind of errors.
  - Whenever possible we generate non-fatal errors in noesisGUI.
  - A new boolean is passed to the error handler to indicate if the error is fatal or not.
- Enhancement C++ Changes to *RenderDevice* API:
  - All shader constants are now pointers that can be null in case the constant is unused.
  - A hash is provided for each shader constant to avoid uploading redundant data to GPU.
  - Shader generation is now isolated in each implementation using custom scripts.
  - Reduced the number of sampler combinations from 8-bits to 6-bits
  - Added information about the surface size in *BeginTile* to allow vertical flipping avoiding API gets.
  - Deprecated *DeviceCaps.maxSamples*, no longer needs to be implemented by renderers.
- Enhancement C++ Improved the implementation of *Delegates* using C++11 features.
- Enhancement Error mechanism improved in C# bindings, heavily reducing binary size and runtime performance.
- Enhancement Stencil only used when strictly necessary.
- Enhancement Xcode compiling now with libc++ (OSX minimal version is now 10.7).
- Enhancement iOS minimal version set to 6.0.
- Enhancement RTTI enabled for iOS to avoid linking issues in client code.
- Enhancement Theme dictionary made global to all views. Noesis::GUI::SetTheme(ResourceDictionary\* theme).
- Enhancement StaticResources resolved while parsing, matching WPF behavior.
- Enhancement Faster XAML loading times.
- Enhancement Improvements to [TreeView](_TreeView.md) creation times.
- Enhancement Path no longer cloning geometry to apply the stretching. Faster loading times.
- Enhancement Key enumeration matching WPF.
- Doc Added note to [Unity tutorial](Unity3DTutorial.md#building-on-android) about problems using Android OBBs.
- Fixed Due to layout issues [ListBox](_ListBox.md) shows empty even though it is populated with data.
- Fixed First element of the [ListBox](_ListBox.md) was moved 1 pixel down when scrolling.
- Fixed [TextBlock](_TextBlock.md) not updating layout after a new measure, rendering nothing.
- Fixed Problems disposing C# proxy instances.
- Fixed [ComboBox](_ComboBox.md) selecting incorrect item after scrolling a long list with mouse wheel.
- Fixed Duplicate name registration when having the same [UserControl](_UserControl.md) several times in a template.
- Fixed Crash if caret arranged before [TextBox](_TextBox.md).
- Fixed Crash when loading non-existent XAML files. Now a non-fatal error is raised.
- Fixed Bindings in DataContext property not updating.
- Fixed Setting empty string to a property was not supported in XAML: <Setter Property="Text" Value=""/>.
- Fixed Crash when focusing a [TextBox](_TextBox.md) before doing its layout.
- Fixed Crash in [TreeView](_TreeView.md) when clearing ItemsSource collection.
- Fixed Invalid generated geometry when stroking an empty [Rectangle](_Rectangle.md).

# Version 2.0.0b3

- Feature D3D11 Support for activating linear space rendering (sRGB) in *D3D11RenderDevice* constructor.
- Feature Support for creating [ImageSource](_ImageSource.md) from memory buffer using BitmapSource::Create.
- Feature Support for creating [TextureSource](_TextureSource.md) from native (GL, D3D) handles.
- Feature [BindingExpression](_BindingExpression.md) exposed to public API.
- Enhancement Static text rendering quality improved. Vertical hinting is active by default right now.
- Enhancement CPU performance greatly improved in our vector graphics engine. For complex scenes the improvement is >50%.
- Enhancement Improved performance when rendering [VisualBrush](_VisualBrush.md).
- Enhancement Added support for high-resolution mouse wheels.
- Enhancement [Popup](_Popup.md) *Opened* and *Closed* events exposed to C#.
- Fixed [Path](_Path.md) hit testing failing sometimes with multiple figures.
- Fixed Glyph kerning was sometimes incorrect at the beginning of a line.
- Fixed [ToolBar](_ToolBar.md) not measuring correctly children.
- Fixed [ContextMenu](_ContextMenu.md) opening and closing events now matches WPF order.

# Version 2.0.0b2

- Enhancement Visual Studio 2015 officially supported.
- Xbox One C++ New platform supported.
- Doc New [resource providers tutorial](ProvidersTutorial.md).
- Doc Tutorial for the new [rendering architecture](RenderingTutorial.md).
- Enhancement Improvements to *RenderDevice* architecture to better support complex offscreen scenarios. With these changes it is easier to avoid redundant state changes and it better supports TBR architectures.
- Enhancement *Source* attribute deprecated in *UserControls* and *Code-Behind classes*. Corresponding XAML must now be loaded from constructor using *LoadComponent(this, uri)*. This matches the WPF behavior.

  ```
  class MyUserControl: public Noesis::UserControl
  {
  public:
      MyUserControl()
      {
          InitializeComponent();
      }

  private:
      void InitializeComponent()
      {
          Noesis::GUI::LoadComponent(this, "Controls/MyUserControl.xaml");

          // Do FindNames and hook to events here
      }
  };
  ```
- Fixed Support for using *StaticResources* defined in a different XAML file.
- Fixed Sometimes parser was creating an extra instance of each *UserControl* and inmmediately destroying it.
- Fixed Pressing *Up* arrow in empty [TextBox](_TextBox.md) unfocus the control.
- C++ Deprecated *NsFunc* no longer supported in reflection macros. Events must be manually registered.

# Version 2.0.0b1

- Feature New multithreading rendering architecture. Class *IRenderer* split into *IView* (for the main thread) and *IRenderer* (for the renderer thread, if any). More information at the [rendering tutorial](RenderingTutorial.md).
- Enhancement C++ Base class for renderers have been simplified. With 2.0 we expect all our clients to provide custom renderer implementations. Shouldn't take more than 2 - 3 day to implement one following our reference implementation.
- C++ Our official runtimes no longer provide renderer implementations. It must be implemented by client code. We will provide reference implementations for all our platforms within the SDK. D3D11 and GL/GL\_ES provided in this version.
- Feature New resource providers architecture:
  - BuildTool deprecated. Textures, Fonts and XAMLs no longer needs preprocessing.
  - [Custom loaders](ProvidersTutorial.md) must be passed to *Noesis::GUI::SetResourceProvider()*. We support local files by default (similar to 1.2).
  - *Noesis::Stream* simplified to allow easier specialization.
- Enhancement New font rendering architecture:
  - Support for all kind of brushes in text: solid, linear, radial and image.
  - Support for text inlines like *<Bold>*, *<Italic>* and *<Span>*.
  - Glyphs are now cached in a single atlas and dynamically recycled. Atlas resolution can be configured.
  - New text rendering algorithm with enhanced subpixel positioning. Hinting and ClearType no longer used.
  - Big glyphs are now rasterized with triangles instead of bitmaps. Threshold can be configured.
  - *FontWeight*, *FontStyle* and *FontStretch* properties fully supported.
- Enhancement *Kernel::Tick()* removed. Client code no longer needs to call this function.
- Enhancement We no longer clear external surfaces. *DoNotClearStencil* and *ClearColor* flags deprecated. Client code must do it.
- Enhancement Offscreen rendering performance greatly improved.
- Enhancement Offscreen view configuration is now sane by default. *SetOffscreenSize* function removed.
- Enhancement Performance of bin-packing algorithm, used by offscreens and glyphcache, improved.
- Enhancement TBB is no longer a dependency.
- Enhancement VisualBrush generation no longer forcing re-tessellation.