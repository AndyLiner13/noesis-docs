Source: https://www.noesisengine.com/docs/Gui.Core.Changelog_v12.html

# NoesisGUI 1.2 Changelog

# Version 1.2.6f5

- Enhancement [UIElement](/Gui.Core/_UIElement.md) GetMeasureConstraint/GetArrangeConstraint removed from documentation.
- Enhancement C++ [DependencyProperty](/Gui.DependencySystem/_DependencyProperty.md) *ValidateValueCallback* return type is now bool to match WPF.
- Enhancement Minimal OS X version is 10.6 again (was 10.8 in previous builds).
- Fixed [Binding](/Gui.Core/_Binding.md) was not returning *FallbackValue* or default value if target property validation failed.
- Fixed Crash if element was captured during mouse over management.
- Fixed StaticResource failing when referencing a MergedDictionary in a [UserControl](/Gui.Core/_UserControl.md).
- Fixed BuildTool output problems when using pipes in Windows 10.
- Fixed Rare crash in DirectX11 when updating texture surfaces.

# Version 1.2.6f4

- Unity Internal *GetMeasureConstraint* and *GetArrangeConstraint* removed from [UIElement](/Gui.Core/_UIElement.md).
- Enhancement *PredictFocus* and *MoveFocus* added to [UIElement](/Gui.Core/_UIElement.md).
- Enhancement C# *IsInverted* flag exposed when creating TextureSource.
- Fixed BuildTool output problems when using pipes in Windows 10.
- Fixed Rare crash in DirectX11 when updating texture surfaces.
- Fixed Added validation of FontSize values.
- Fixed Crash when touch scrolling [ListBox](/Gui.Core/_ListBox.md) and ScrollUnit="Pixel".
- Fixed Crash when using [ListView](/Gui.Controls/_ListView.md) without *View*.
- Fixed C# Strange crash in KeyDown event.
- Fixed C# Incorrectly exporting mangled C++ symbols.
- Fixed Unity Android crashes due to improperly handling *GL\_OES\_vertex\_array\_object*.
- Fixed Unity No longer trying to instantiate abstract classes in windows phone.

# Version 1.2.6f3

- Enhancement C# Added renderer configuration functions to C# SDK.
- Enhancement C# Missing [ScrollViewer](/Gui.Core/_ScrollViewer.md) properties added.
- Enhancement Binding.DoNothing was missing.
- Fixed Strange problem causing UI not rendering in iOS. More platforms could be affected.
- Fixed [ScrollViewer](/Gui.Core/_ScrollViewer.md) was not binding to all the scrolling properties of templated parent.
- Fixed Caret not showing with [ScrollViewer](/Gui.Core/_ScrollViewer.md) of [TextBox](/Gui.Core/_TextBox.md) template having null width.
- Fixed Issues with the position of [TextBox](/Gui.Core/_TextBox.md) cursor.
- Fixed VirtualizingStackPanel incorrectly initializing estimated size of virtualized items.
- Fixed VirtualizingStackPanel.BringIndexIntoView not working correctly with certain item sizes.
- Fixed Support in ItemsControl for null items.
- Fixed Binding to struct sub-property not working.
- Fixed Clicking on a ContextMenu triggered from a button will also click on the button

# Version 1.2.6f2

- Feature UI virtualization implemented and enabled by default for [ListView](/Gui.Controls/_ListView.md) and [ListBox](/Gui.Core/_ListBox.md) controls.
- Feature [ItemContainerGenerator](/Gui.Core/_ItemContainerGenerator.md) added and used by [ItemsControl](/Gui.Core/_ItemsControl.md) to generate item containers.
- Feature Support for OTF (Open Type) fonts.
- Feature New platform: Android x86.
- Unity Feature New option in NoesisGUI component to enable touch emulation using mouse.
- Feature C++ Support for C++11 lambdas in events.
- Enhancement Huge performance improvements on element initialization, element destruction and layout process.
- Enhancement C# Removed unnecessary allocations in managed layer.
- Enhancement [Selector](/Gui.Core/_Selector.md) properties now stay in sync when being modified.
- Enhancement *ScrollIntoView* implemented in [ListBox](/Gui.Core/_ListBox.md).
- Enhancement *IsDeferredScrollingEnabled* implemented in [ScrollViewer](/Gui.Core/_ScrollViewer.md).
- Enhancement Added Scroll commands to [ScrollViewer](/Gui.Core/_ScrollViewer.md).
- Enhancement Added support for *IScrollInfo* and *CanContentScroll* in [ScrollViewer](/Gui.Core/_ScrollViewer.md).
- Enhancement C# *IScrollInfo* interface exposed to C#.
- Enhancement *OnRender* raised now inside *Arrange* to match WPF behavior.
- Enhancement Support for C# properties of type *System.Type*.
- Enhancement Improved stability when importing XAMLs in OSX.
- Enhancement C++ Removed Destroyed delegate from *INotifyPropertyChanged*.
- Enhancement Collections matching WPF behavior:
  - Item comparison uses now Equals method, so boxed values can be correctly found.
  - Collections can add the same item multiple times now.
  - Removing an item that is not found in the collection doesn't throw error anymore.
- Unity Enhancement Improved how C# reflection is exposed to C++. Huge performance improvements.
- Unity Enhancement Boxing avoided whenever possible to improve performance.
- Unity Enhancement Native support for C# double properties.
- Unity Enhancement Support for binding struct properties.
- Unity Fixed WPhone Managed strings properly converted to UTF8 when passsed to C++.
- Unity Fixed Boxed values coming from Unity were incorrectly released sometimes.
- Unity Fixed Multithreading issue when creating and destroying renderers.
- Unity Fixed Rarely random crash in Mono arm implementation when using many lambda expressions.
- Unity Fixed [Button](/Gui.Core/_Button.md) command being incorrectly invoked when inside a manipulation.
- Fixed [ListBox](/Gui.Core/_ListBox.md) selection failing when using boxed values.
- Fixed *NullableConverter.ConvertTo* failing when using a null *Nullable*.
- Fixed Returning null from *Binding.Converter* should work even if target property does not support null values.
- Fixed C++ Reflection macros added to [ObservableCollection](/Gui.Core/_ObservableCollection.md) to allow dynamic casting.
- Fixed Support for carriage return when displaying text.
- Fixed [TextBox](/Gui.Core/_TextBox.md) caret shown outside control bounds when using a template without a [ScrollContentPresenter](/Gui.Core/_ScrollContentPresenter.md) .
- Fixed Incorrect caret position in right/center aligned [TextBox](/Gui.Core/_TextBox.md).
- Fixed [TextBox](/Gui.Core/_TextBox.md) with right aligned wrapped text not positioning caret correctly.
- Fixed *HorizontalContentAlignment* not working in [TextBox](/Gui.Core/_TextBox.md).
- Fixed [Slider](/Gui.Core/_Slider.md) input crashing.
- Fixed Fixed return type of Freezable.Clone and related.
- Fixed Unity Focused element being lost when starting the application.
- Fixed *Style.BasedOn* can be set to itself leading to infinite loop during initialization.
- Fixed HorizontalOffset/HorizontalChange of *ScrollChangedEventArgs* not delivering correct values.
- Fixed *Text.Stroke* rendering incorrectly if only setting *Text.StrokeThickness*.
- Fixed *ContentTemplate* not being applied without setting content.
- Fixed Mouse over properties not updated on mouse wheel events.
- Fixed Setting binding in freezable inside template.
- Fixed KeyBinding incorrectly matching modifiers.
- Fixed Crash if panel destroyed before children collection.
- Fixed Enums with different names for the same value not correctly registered.
- Fixed Commands not setting *Handled* member to *True* when processing event.
- Fixed [ListView](/Gui.Controls/_ListView.md) column headers can't be dragged if pressing over the header content.
- Fixed [Path](/Gui.Core/_Path.md) stretching not working correctly due to bug in bound calculations.
- Fixed Value converters ignored by [DataTrigger](/Gui.Core/_DataTrigger.md).
- Fixed [DataTrigger](/Gui.Core/_DataTrigger.md) not being evaluated correctly if condition fulfilled during initialization.
- Fixed Collapsing/Uncollapsing not updating desired size correctly.
- Fixed Problem with generics and AOT causing strange crashes.
- Fixed Crash when animating properties with incorrect type.
- Fixed Width of elements using *Grid.ColumnSpan* being applied to each single column.
- Fixed [UserControl](/Gui.Core/_UserControl.md) not transferring *InputBindings* and *CommandBindings* from associated xaml.
- Fixed Can't set Resources property of [UserControl](/Gui.Core/_UserControl.md) when inside another xaml.
- Fixed Vertical [ProgressBar](/Gui.Core/_ProgressBar.md) not rendering the same as WPF.

# Version 1.2.5f11

- Unity Fixed Support for dynamically changing screen resolution and antialiasing in OpenGL.
- Unity Fixed Rare crash when using extra mouse buttons and hovering over elements.
- Unity Fixed Keyboard and Mouse incorrectly disabled in mobile platforms (needed for example in Android TV).

# Version 1.2.5f10

- Fixed [ScrollContentPresenter](/Gui.Core/_ScrollContentPresenter.md) accessing destroyed scroll info during measure.
- Unity Fixed GLCore renderer was not working properly in Windows.

# Version 1.2.5f9

- Unity NoesisGUI is now compatible with Unity 5.3.
- Fixed ContentPresenter content template not correctly disconnected when being invalidated.
- Unity Fixed C# PropertyChanged event binder being accessed after destruction.
- Fixed Crash when using PPA with very big meshes. PPA disabled in those cases now.

# Version 1.2.5f8

- Feature Implementation of [DataTrigger](/Gui.Core/_DataTrigger.md) and [MultiDataTrigger](/Gui.Core/_MultiDataTrigger.md). New [sample](https://github.com/Noesis/Tutorials/tree/master/Samples/DataTriggers) at GitHub.
- Unity Improved compatibility with Unity 5.2.
- Unity Feature Added support for rendering inside uGUI using a *RawImage* component.
- Enhancement [FrameworkElement](/Gui.Core/_FrameworkElement.md) value providers re-factorized as static classes to reduce memory usage.
- Enhancement Group opacity shader optimized.
- Enhancement Improved how system resources stop notifying dynamic resources.
- Enhancement Improved exception safety in Kernel initialization. *Init* and *Shutdown* are more robust now.
- Enhancement Some important keys (like comma, period, minus, plus...) where missing from Key enum.
- Unity Enhancement [Documentation folders](https://www.noesisengine.com/forums/viewtopic.php?f=3&t=755) no longer stored inside *Assets/*.
- Unity Enhancement Log and Dump directories were not being created. We needed them to be pre-created.
- Unity Enhancement Compatibility with [OpenGLCore](http://blogs.unity3d.com/es/2015/05/26/dx11-features-on-mobile/) Unity Graphics API.
- Unity Enhancement Multithreaded Rendering working in Android.
- Unity Enhancement Errors going from C# to C++ are sent to the Unity log.
- Unity Enhancement Improved rendering performance (Android) when no group opacities being used.
- Unity Enhancement Improved the way noesis native errors are handled. We no longer show alien dialogs.
- Unity Enhancement UnityRenderHook dynamic libraries no longer needed in standalone.
- Unity Enhancement Various *VisualTreeHelper* methods used uint instead of int.
- Unity Enhancement Support for extending [ResourceDictionary](/Gui.Core/_ResourceDictionary.md). Required to implement [DesignTimeResourceDictionary](https://www.noesisengine.com/forums/viewtopic.php?f=3&t=806).
- Fixed Crash and leaks returning strings between C++ <-> C#.
- Fixed Logical tree is now built when object gets initialized, so *FindResource* can find resources correctly.
- Fixed [TextBlock](/Gui.Core/_TextBlock.md) does not wrap when using a scale *LayoutTransform*.
- Fixed Unhandled exception when using a *CombinedGeometry* without setting both geometries.
- Fixed Nothing drawn when using *GeometryGroup* or *CombinedGeometry* in *Path.Data* property.
- Fixed Remove class/property name size limitation in *PropertyPath* parsing.
- Fixed Style storyboards shouldn't reference named elements.
- Fixed TwoWay binding failing with Nullable<double> source.
- Fixed Crash with animated *ProgressBar* style.
- Fixed Access Violation closing submenu.
- Fixed Exception after Offscreen Error.
- Fixed Sometimes the *DisplayMemberPath* property does not seem to work in *ComboBoxes*.
- Fixed Scroll not working when VerticalScrollBarVisibility was disabled.
- Fixed Strange crash in Linux related to mouse input handling.
- Fixed Accessing deleted template elements when a *ContentControl* was destroyed.
- Fixed Accessing deleted *PropertyMetadata* object when destroying its *PropertyChangedCallbackBind*.
- Fixed Crash accessing *TimelineEventArgs.Target* on Completed event handler.
- Fixed Visual glitch / Strange render issues when geometry transform updated.
- Unity Fixed Errors when initializing a XAML renderer were causing unhandled exception and closing Unity.
- Unity Fixed *UserControl.Triggers* for *FrameworkElement.Loaded* affect only on the second frame.
- Unity Fixed Crash at shutdown when binding to *ObservableCollection<bool>*.
- Unity Fixed TextureSource was not returning the correct values for PixelWidth, PixelHeight and Dpis.
- Unity Fixed Can't use a *Converter* in *Binding* if target property is nullable.
- Unity Fixed Custom nullable properties (CLR and DP) in C#.
- Unity Fixed Runtime crash of Unity editor when style storyboard references template name.
- Unity Fixed Can't patch file when building for Windows Store Universal.
- Unity Fixed Unity crash using runtime view model with bindings.
- Unity Fixed Linux plugins not properly configured for Universal Builds.
- Unity Fixed Notify Property Change for indexers not working.

# Version 1.2.4

- Unity NoesisGUI is now 100% compatible with Unity 5.1.
- Unity Feature Added support for the new [unified OpenGL rendering backend](http://blogs.unity3d.com/2015/05/26/dx11-features-on-mobile/) in Unity 5.1.
- Unity Feature Support for indexed properties in data-binding. Int and String key types supported.
- Feature Implemented DisplayMemberPath property in [ItemsControl](/Gui.Core/_ItemsControl.md) class.
- Feature Implemented SelectedValue and SelectedValuePath properties in [Selector](/Gui.Core/_Selector.md) class.
- Feature Implemented support for [HierarchicalDataTemplates](/Gui.Core/_HierarchicalDataTemplate.md).
- Feature Implemented [UniformGrid](/Gui.Core/_UniformGrid.md).
- Feature Added support for [TextBox](/Gui.Core/_TextBox.md) properties: IsSelectionActive, SelectionStart, SelectionLength and SelectedText.
- Enhancement Resource lookup (FindResource with StaticResource and DynamicResource) reviewed to match WPF behavior.
- Enhancement Avoid iterating the logical tree multiple times when doing a resource lookup.
- Enhancement Visual.HitTest() now expects position in visual coordinates, as in WPF.
- Enhancement InputBindings are now DependencyObjects and Command is a DependencyProperty so bindings can be set.
- Enhancement Improved XAML parser checks setting duplicate properties.
- Enhancement Added DataContextChanged and Initialized events to [FrameworkElement](/Gui.Core/_FrameworkElement.md).
- Enhancement Added [PasswordBox](/Gui.Core/_PasswordBox.md) login sample.
- Enhancement BuildTool errors redirected to *stderr*. Exit code is now the number of errors found.
- Enhancement Improved OSX editor stability.
- Enhancement Improved the rendering performance of radial gradients.
- Enhancement ManipulationInertiaStartingEventArgs changed to be more WPF compliant.
- Enhancement Doc [Touch Tutorial](/Gui.Core/TouchTutorial.md) updated. Sample moved to [github repository](https://github.com/Noesis/Tutorials/tree/master/Content/Touch).
- Enhancement Doc Added a new entry explaining UniformGrid to [Panels Tutorial](/Gui.Core/LayoutPanelTutorial.md).
- Enhancement Doc [Data Binding Tutorial](/Gui.Core/DataBindingTutorial.md) commenting about HierarchicalDataTemplate, DisplayMemberPath and Indexers.
- Enhancement Doc Updated the documentation for Windows Store in the [Unity Tutorial](/Gui.Core/Unity3DTutorial.md). Steps simplified a bit.
- Unity Enhancement [DataTemplateSelector](/Gui.Core/_DataTemplateSelector.md) properly exposed to C#. It was only available in C++ before.
- Unity Enhancement Non-routed events for [UIElement](/Gui.Core/_UIElement.md) and [FrameworkElement](/Gui.Core/_FrameworkElement.md) exposed.
- Unity Enhancement Support for overriding ToString, Equals and GetHashCode in custom classes.
- Unity Enhancement Added ShowSlices property to NineSlice UserControl to render a visual hint for the slices.
- Unity Enhancement Removed obsolete Resources.LoadAssetAtPath().
- Unity Enhancement Added support for C# properties of type TimeSpan, Duration and KeyTime.
- Fixed Incorrect rendering of asymmetric radial gradients in iOS.
- Fixed [TextBlock](/Gui.Core/_TextBlock.md) inlines not working inside a template.
- Fixed [TextBlock](/Gui.Core/_TextBlock.md) alignment within data template not working properly.
- Fixed StringFormat parser not working properly in rare cases.
- Fixed Text is now updated on editable [ComboBox](/Gui.Core/_ComboBox.md) when writing in the [TextBox](/Gui.Core/_TextBox.md).
- Fixed Crash destroying elements after showing [ToolTips](/Gui.Core/_ToolTip.md).
- Fixed [Line](/Gui.Core/_Line.md) shape was not calculating correctly the stretch transform applied to the [LineGeometry](/Gui.Core/_LineGeometry.md).
- Fixed Circular references could be created when binding content to UserControl as DataContext.
- Fixed [ScrollViewer](/Gui.Core/_ScrollViewer.md) scrollbars not hiding or showing when content changed its size.
- Fixed LayoutTransform failing with negative scales.
- Fixed Bindings to elements in template being lost when changing template.
- Fixed Changed the behavior of Loaded event to be [WPF compliant](http://blogs.msdn.com/b/mikehillberg/archive/2006/09/19/loadedvsinitialized.aspx). Now it is raised after element is ready to be rendered.
- Fixed Controls remain focused when they or their parent are hidden.
- Fixed Strange crash in focus management when doing ALT + TAB in Linux.
- Fixed Template visual tree was not reevaluating inherited properties and dynamic resources after connecting it to the Control.
- Fixed [ToolTips](/Gui.Core/_ToolTip.md) were not being hidden after moving mouse outside their owner.
- Fixed SelectedIndex and SelectedItem were not updated after modifying ItemsSource.
- Fixed ItemCollection was not connecting inner collections to the UI tree.
- Fixed [ComboBoxes](/Gui.Core/_ComboBox.md) opened inside a [ScrollViewer](/Gui.Core/_ScrollViewer.md) were also scrolling the ScrollViewer.
- Unity Fixed Access violation using List or ObservableCollection<T> with basic types as ItemsSource of a [Selector](/Gui.Core/_Selector.md) control.
- Unity Fixed [ListBox](/Gui.Core/_ListBox.md) failing to select items bound to a List or ObservableCollection<T> for non-reference types.
- Unity Fixed Removing item from data bound [ListBox](/Gui.Core/_ListBox.md) via command binding causing crashes.
- Unity Fixed Dependency GetValue not unboxing BaseComponent sometimes.
- Unity Fixed Crash when closing an application that lost the focus at initialization time in OSX.
- Unity Fixed In some cases items passed to a managed list were not unboxed, producing an ArgumentException in Unity.
- Unity Fixed TryFindResource now returns null when resource is not found as in WPF.

# Version 1.2.3

- Feature New platform supported: x86\_64 in Linux.
- Enhancement Remove border and background from the styles of base control classes.
- Enhancement Improve error message setting a Binding in a CLR property.
- Enhancement Updated iOS and Android sections in [integration tutorial](/Gui.Core/SDKGuide.md). New [integration sample](https://github.com/Noesis/Tutorials/tree/master/Content/Integration/Android) for Android.
- Enhancement RTTI is now enabled by default in GCC (as in XCode) to avoid linking issues in client projects.
- Enhancement RemoveUnusedProxies optimized, it should no longer appear in the profiler hot spots.
- Enhancement Unity Exceptions raised in C# like event handlers no longer generating native exceptions in standalone.
- Fixed Selector properties SelectedIndex, SelectedItem and SelectedValue should be TwoWay bound by default
- Fixed Arrow keys moving focus out of TextBox when text was empty.
- Fixed Popup with StaysOpen=false was not updating IsOpen property when closing it by clicking outside the popup.
- Fixed Enter actions of control template Triggers were not fired on initialization.
- Fixed Default ProgressBar template changed to allow modifying the height.
- Fixed GCC 4.8 compilation issues.
- Fixed Binding failed to assign compatible values when source property was BaseComponent.
- Fixed Simple Run inside a TextBlock was not working.
- Fixed TextBox caret not always visible when interacting with text.
- Fixed Caret position wrong in Wrap mode when a word doesn't fit in a line.
- Fixed Big Paths (>64K indices) crashing.
- Fixed Issue with degenerated cubic Bezier curves.
- Fixed GLSL 140 path was being incorrectly taken in GL3+ instead of GL3.1+.
- Fixed Extension GL\_EXT\_multisampled\_render\_to\_texture not working correctly in OpenGL ES 3.
- Unity Fixed Type already registered problem when base type can end up registering the same type.

# Version 1.2.2

- Unity 5 We have fixed all the known problems and now NoesisGUI is fully compatible with Unity5. All supported platforms.
- Unity Enhancement Dependency to tbb.dll eliminated
- Fixed Strange issue in OpenGL drivers (OSX) causing random flickering.
- Fixed Proper detection of max multisample values. Was not correct in several mobile devices.
- Fixed Serialization of Dependency Properties was crashing in a few scenarios (C++ SDK).
- Fixed Crash setting a non-dictionary root in ResourceDictionary.Source.
- Fixed BuildTool crashing with a few incorrect markups.
- Fixed PlaneProjection.CenterOfRotation{X,Y,Z} not working properly.
- Fixed Crash setting a Style object in the Template property using a Binding.
- Fixed BaseComponentConverter now CanConvertTo string as expected.
- Fixed Pure Virtual Function Call when a binding was partially resolved and last Path property type was not a BaseComponent.
- Fixed Render glitches in win\_x86\_64 due to non-finite math problems (NaN, Infinites)
- Unity Fixed Windows Phone platform crashing at startup although it was working properly if generating a store package.
- Unity Fixed Weird interaction with Unity was activating a slow path in the OpenGL driver (OSX performance problem).
- Unity Fixed Crash passing structs from Mono to C++ in the OSX version of Mono.
- Unity Fixed Proper error shown if Metal API is active in iOS

# Version 1.2.1

- Unity Feature Unity 5 compatibility.
- Unity Feature Added NoesisGUIPanel.LoadXaml(xaml) to create noesisGUI panels by code.
- Unity Enhancement IDisposable no longer implemented in BaseComponent.
- Enhancement TextBox.AcceptsTab implemented.
- Enhancement Keyboard events are now properly raised/canceled when user sets Handled=true.
- Enhancement Fixed parameters of KeyEventArgs and TextCompositionEventArgs to be WPF compliant.
- Fixed DataContext being incorrectly reset when Visual parent removed.
- Fixed Initialization error in several Android devices.
- Fixed Crash restoring focus on a TextBox/PasswordBox.
- Fixed Crash when using StaticResources to set properties of a DataTemplateSelector in XAML.
- Unity Fixed Problem with DependencyProperties in controls that are instanced from code.
- Unity Fixed MouseEventArgs.GetPosition(UIElement relativeTo) crashes when null element was passed.
- Unity Fixed Memory leaks when creating StringMarshal objects.
- Unity Fixed NullReferenceException destroying disabled NoesisGUIPanel.
- Unity Fixed Error when Stopping with a NoesisGUIPanel disabled.
- Unity Fixed Registered missing native types in Unity.
- Unity Fixed DependencyProperty and PropertyMetadata types not exposed correctly in Unity.
- Unity Fixed Render to texture not working properly on Android.
- Fixed Memory leak when DataContext is set to itself (usually in UserControl.OnPostInit() { DataContext = this}).

# Version 1.2.0

- Feature New platforms supported:
  - DirectX11
  - Windows Store and Windows Phone 8.1
  - OpenGL3+
  - OpenGL ES 3
  - iOS arm64
- Unity Feature Absolute [URIs](/Gui.Providers/_Uri.md) are now supported.
- Unity Feature [MVVM](https://github.com/Noesis/UnityMVVM) project shared to be compatible with uFrame.
- Enhancement New batching algorithm. Draw Calls reduced significantly.
- Enhancement Optimized the way ramps are uploaded to the GPU.
- Enhancement Dashing generation improved.
- Enhancement Improved filling and stroking generation. Less triangles generated. Better quality of strokes.
- Enhancement Reduced the number of redundant state changes. Improved the synchronization with client state.
- Enhancement Serialization file format increased to version 5. Size is 10% smaller in general.
- Enhancement Dynamic libraries are smaller now in comparison to v1.1.
- Enhancement Static library (iOS) is now prelinked and stripped.
- Enhancement Simplified resource architecture. XAMLs can be everywhere right now.
- Enhancement New *BuildTool*. Core resources (like default shaders and styles) are now hidden inside binaries.
- Enhancement Disabled mipmaps in preprocessed textures.
- Enhancement Implemented texture compression in GL.
- Enhancement XamlPlayer is more flexible now. Files can be dropped from any location.
- Enhancement Support for passing .xaml to be displayed in command line in *XamlPlayer*.
- Enhancement Support for Visual Studio 2013 added.
- Enhancement Improvements to documentation:
  - All tutorials have been reviewed. Data is now hosted in [GitHub](https://github.com/Noesis/Tutorials).
  - New: [A quick guide to XAML tutorial](/Gui.Core/XamlIntroduction.md).
  - New: [Data Binding Tutorial](/Gui.Core/DataBindingTutorial.md).
  - New: [Introducing Controls Tutorial](/Gui.Core/ControlsTutorial.md).
- Enhancement Optimization of theme styles. Opacity usage reduced. *Noesis Style* is faster at this version.
- Enhancement Added support for setting a fallback *VisualState* in *Control.GoToState()*
- Enhancement Added support for changing *Theme* after initialization.
- Enhancement Support for manually specifying which surfaces must be cleared (only stencil by default).
- Enhancement Unity Render textures are cleared to transparent.
- Enhancement Added *BooleanToVisibilityConverter*.
- Enhancement Added Rendering event to *IRenderer*. Also exposed to Unity through *NoesisGUIPanel*.
- Enhancement Added support for GL\_EXT\_debug\_marker. Easier to analyze frames now in XCode.
- Enhancement Unity ControlGallery demo redesigned to be much more touch friendly.
- C++ API changes:
  - Dependencies properties of type *NsString* are now set and get using *const char\**.
  - NoesisGUI.h, a header with all the API (under Noesis namespace). To be used as *Precompiled Header*.
  - XCode library built with RTTI enabled.
  - We have reduced the exposed API. All integration functionality is under *Noesis::GUI*.
  - *ObservableCollection* implemented in C++ (for symmetry with C#).
- C# API changes:
  - Basic types like *Point*, *Size*, *Transform2*, *Matrix3* are now structs to reduce the stress of the GC.
  - Properties instead of Get/Set methods.
  - Animation correctly exposes *From*, *To* and *By* properties.
  - KeyFrame correctly exposes Value property.
  - KeyFrameCollection exposed.
  - Support for native casting (*as*, *is* operators). As<T> deprecated.
  - Support for boxing. Our API now exposes *System.Object* instead of *Noesis.BaseComponent*.
  - Support for the following interfaces: *ICommand*, *IValueConverter*, *IList*, *IDictionary*, *INotifyPropertyChanged*, and *INotifyCollectionChanged*.
  - Support for ObservableCollection<T>.
  - Generics are now supported.
  - DependencyObject *GetValue* and *SetValue* API changed to match WPF, now object is used.
  - *NewValue* and *OldValue* to *DependencyPropertyChangedEventArgs*.
  - Many event arguments modified to expose members as C# properties.
  - Noesis.Extended attribute deprecated.
  - Removing a delegate from an empty event no longer throws as expected in C#.
- Fixed Unnecessary Offscreen passes being generated on each frame.
- Fixed Bug in state transitions when both *VisualTransition* and *VisualState* defined a *Storyboard*.
- Fixed *ListView* multiple selection was not working.
- Fixed *RadioButton* was not working with an indeterminate (null value) *RadioButton* in the group.
- Fixed MergedDictionaries were incorrectly traversed forward when looking for a resource.
- Fixed *TouchEnter* and *TouchLeave* events not properly generated