Source: https://www.noesisengine.com/docs/Gui.Core.Changelog_v11.html

# NoesisGUI 1.1 Changelog

# Version 1.1.14

- Support for prefixes when using static extensions: {x:Static local:Settings.BaseColor}.
- Removed UseLayoutRounding from styles, so user can decide the behavior of the whole UI tree just by setting the value in the root.
- Unity Added TryLoadXaml to API.
- Unity Improved compatibility with Unity 4.6.
- Fixed Bindings with LostFocus/Explicit UpdateSourceTriggerMode where not working properly.
- Fixed Crash when clicking on TabItems (Linux).
- Fixed LinearGradientBrush not working in Absolute mode when used on certain Paths.
- Fixed Layout process of Grid with many items could produce an unhandled exception.
- Fixed DependencyProperty value storage not properly constructed when unserializing a StaticResourceExpression.
- Fixed Setting DataContext property from a Binding using parent DataContext.
- Fixed Calculation of PlaneProjection when surface size was 0.
- Fixed Binding inside DataTemplate using RelativeSource AncestorType not working if parent outside the DataTemplate visual tree.
- Fixed Comparing Pens was causing unnecessary tessellations per frame.
- Fixed Problem with ClearLocalValue() and inherited properties.
- Fixed In OSX, Alt key was not working properly.
- Fixed PPAA artifacts.
- Fixed Geometry being clipped by far plane when applying 3D transformations on Retina displays.
- Fixed Crash on Nvidia Shield tablets.
- Fixed Crash when moving ListView columns by dragging the column header.
- Fixed Crash in OSX when accessing empty clipboard.
- Unity Fixed Crash when focused item was removed in Unity while application is not focused.
- Unity Fixed Dumps are now generated in $(PROJECT)/Dumps folder.

# Version 1.1.13

- Unity XAMLs with a Window root are no longer accepted in Unity. A proper error is shown at build time.
- Unity Noesis.Extend.IsExtendType(type) is cached to speed up .As<T> conversions.
- Fixed Controls inside a template with event handlers added in constructor were ignored.
- Fixed UpdateSourceTrigger default value for TextBox.Text property was not correctly set to LostFocus.
- Fixed Crash on x64 when creating several renderers.
- Fixed PropertyChangedCallback being ignored when using default(string) as default value.
- Fixed Incorrect Extended instance being registered if another BaseComponent is created in its constructor.
- Fixed BaseComponent.AsType was failing when used with extended types.
- Fixed HitTesting failing on Popups.
- Fixed Bugs in TabControl when used along with ItemsSource property.
- Fixed Improved error reporting in VisualTreeHelper and LogicalTreeHelper.
- Fixed Slider moves erratically when receiving several Mouse events between updates.

# Version 1.1.12

- Added support for LineHeight in TextBlock.
- Support for TabControl using ItemsSource property.
- Support for GridLength animation.
- Support for xml:space="preserve".
- Changed TabItem in the DefaultStyle so content gets stretched as in WPF styles.
- Support for using Projection property in Blend WPF projects.
- Fixed Noesis.UserControlSource not needed in not final classes.
- Fixed DefaultStyle padding bindings.
- Fixed Button not reacting to interaction when changing Visibility per frame.
- Fixed VS2013 compilation issues.
- Fixed XCode 6 issues.
- Fixed Crash in ComboBox when using a UIElement as SelectionBoxItem.
- Fixed Some Bindings to UserControl root were failing when using the UserControl inside another xaml.
- Unity Support for passing string to HeaderedContentControl.SetHeader().
- Unity Exposed UIElement.UpdateLayout() to C#.
- Unity Under certain conditions, Image Effects affects to NoesisGUI.
- Unity DX9 Render glitches when resizing fixed.
- Unity No longer crashing when changing DX9 <-> DX11 in Player settings. There is a bug in Unity about this.
- Unity Several functions in UnityBindings not properly protected against exceptions were crashing Unity.
- Unity Subclassed controls used inside a Template now correctly clone their properties.
- Unity Error displayed when switching to a platform that is not active in NoesisGUI settings.

# Version 1.1.11

- PPAA algorithm improved. Now it works properly with animations and it is faster.
- Experimental support added for profiling CPU and Memory using NoesisGUI console.
- Added support for more system types (int16, int32, uint16, uint32, single and double) in a ResourceDictionary. Fixed also the XAML parser because it was using the assembly name instead of the namespace to expand type name.
- Fixed TemplateTriggerProvider was trying to invalidate the properties of an object that was being destroyed.
- Fixed Line geometry was not correctly updated when changing the thickness of the stroke. This bug could also affect other geometries.
- Fixed An incorrect type of value could be assigned to a dependency property coming from a StaticResource.
- Fixed TextTrimming incorrectly generating extra line.
- Fixed Problem when item being removed in the SelectionChanged handler or any other Mouse event handler.
- Fixed ItemContainerStyle bindings to data item properties are now working.

```
<Setter Property="IsSelected" Value="{Binding IsItemSelected, Mode=TwoWay}"/>
```

- Unity functions for injecting input events added.
- Unity GUI render no longer affected by Unity Post Processing. Added a toggle to revert to previous behavior.
- Unity Try versions of FindStringResource and FindTypeResource added.
- Unity Fixed Error inside FindStringResource and FindTypeResource functions was crashing Unity.
- Unity Fixed Ramps not properly rendered when activating Linear Color Space in Player Settings.
- Unity Fixed more keycode problem fixed in Linux.

# Version 1.1.10

- BaseButton.Command exported to Unity/C#.
- Unity: Implemented mechanism to detect package upgrades.
- Fixed Setter serializing a Command set in its Value member.
- Fixed Container not found when calling ItemsControl.GetContainerFromItem passing the container itself.
- Fixed TreeViewItem failing to select the item if already had the focus.
- Fixed SelectionChanged event not working when using a ComboBox with template
- Fixed Crash on application exit.
- Unity Fixed Mac Shortcuts not working (CMD+key)

# Version 1.1.9

- Added constructor for RotateTransform and SkewTransform with parameters for easier initialization.
- Added support for serializing boxed items in a collection.
- SelectionBoxItemTemplate is now a read-only property like in WPF.
- DX9Texture and GLTexture constructors now receive an isInverted boolean.
- Dependency to libbfd eliminated in Linux.
- Reading from the clipboard implemented in Linux.
- Unity Support for setting log filename and dumps folder by creating a noesis.ini in StreamingAssets folder.
- Unity Now XAML are processed after their corresponding .cs, if any, is built by Unity.
- Unity Added support for split application binaries in Android.
- Unity Renamed mobile exported function Noesis\_UnityRenderEvent to avoid name conflicts with other third parties.
- Unity UnityRenderHook library renamed to NoesisUnityRenderHook.
- Unity Software keyboard management re-factorized to facilitate user override.
- Unity Unity tutorial updated with information about how to override default software keyboard behavior.
- Fixed problem with consecutive MouseDown events in OS X standalone.
- Fixed Crash in bindings with nested paths.
- Fixed RoutedEventConverter working in events with a namespace prefix.
- Fixed Binding to inherited DataContext not resolved on Freezables.
- Fixed Bindings don't update when Path doesn't resolve the first time.
- Fixed ProgressBar Indicator element was not updated after modifying Minimum or Maximum properties.
- Fixed ProgressBar default template was making the control to grow to infinite when Value==Maximum.
- Fixed Resource look-up from inside a DataTemplate was broken.
- Fixed GridLengthConverter was not taking into account Auto (NaN) value when converting from a numeric value.
- Fixed Support for complex namespace (A.B.C) prefix in PropertyPath.
- Unity Fixed Problem when modifying a property defined in the base class of a Unity extended class.
- Unity Fixed Mouse and keyboard events handled properly in Linux.

# Version 1.1.8

- Added support for SelectAll command (Ctrl+A) to the TextBox.
- TextBlock: Justify implemented, Wrap implemented (we only had WrapWithOverflow) and Trimming implemented. Added a new xaml in the Text tutorial showing all the combinations.
- Added support for RenderOptions.BitmapScalingMode. Created a new entry in the Image tutorial explaining it.
- Unity Changed default 3D scene used as background in our samples because performance was not good on old mobiles.
- Unity Now XAMLs are automatically built if they were modified during Editor Play.
- Fixed Runtime Error on Progress Bar Animation: the target name 'IndicatorIndeterminate' cannot be found in the xaml namescope.
- Fixed Error handling improved when trying to use Items collection while ItemsSource is set. Class documentation updated to explain this scenario.
- Fixed Items displayed twice when being added to a ComboBox.
- Fixed Small Arc CW flag not working properly.
- Fixed In rare cases DirectX9 device creation was failing. Solves the error with standalone applications not using the Gui.Launcher.
- Fixed In Viewbox.SetChild, old child could be accessed after destroyed.
- Fixed NameScope of UserControl not correctly copied when used as the root of a template.
- Fixed Touch events not working properly when a scale was being applied to a ScrollViewer.
- Fixed Numeric converters are now able to convert from integer to float and vice versa.
- Fixed ProgressBar control was assuming that its template always contained "PART\_Track" and "PART\_Indicator" elements. Now it is optional.
- Fixed StaticResource evaluation in templates, it was not reapplied and resource look-up could fail (crash in Browser Gallery when changing theme).

# Version 1.1.7

- Unity Added HitTest sample to Unity First Steps Tutorial.
- Fixed Error with files and paths containing Unicode characters.
- Fixed Error with ListBoxItem container not found.
- Fixed Text wrapping being applied when it shouldn't due to precisions problems.
- Fixed Crash in Mouse::SetOver.
- Fixed SetCaretIndex() right after SetText() have no effect issue.
- Fixed Performance issues with Storyboard of Duration=0 and RepeatBehavior=Forever.
- Fixed Crash when rendering stroked text.
- Fixed ContentPresenter incorrectly raising an error when another ContentPresenter was present in the same template.
- Unity Fixed Crash when device was lost in scenes using Unity Render Textures as XAML images.
- Unity Fixed Casting fix in BaseComponent.As<T>.

# Version 1.1.6

- Added Debug Marks wrapping GUI render for PIX or similar.
- Input managers (keyboard, mouse, touch) created before connecting content to Renderer so they are available when controls are initialized.
- Improved text rendering quality when vertically flipped (for example, rendering to an OpenGL texture).
- Unity Added support for CornerRadius properties in extended classes.
- Fixed Text rendering problem with kerning and space characters that was causing strange wrappings.
- Fixed Plugins extension set to .dylib in OSX. It was incorrectly set to .so
- Fixed TextBox not capturing correctly focus when inside another control.
- Fixed TabControl content layout was not deterministic.
- Fixed DataTemplate were not found when stored by type in a ResourceDictionary.
- Fixed ItemsPresenter was not filled with items sometimes when ItemsControl.ItemsSource was set.
- Fixed RoutedUICommand::Create(), text and name parameters were used incorrectly.
- Fixed UserControl root element used by VisualStateManager to look for VisualStateGroups must be the UserControl.Content, instead of the template root child as it occurs in the rest of Controls.
- Fixed ItemsControl not regenerating items when ItemsPanel or ItemsTemplate properties are modified.
- Fixed ItemsControl not correctly cloned when it was part of a template.
- Fixed ContextMenu defined in a Style or ResourceDictionary was not opening.
- Fixed TouchMove and TouchUp were not correctly promoted to mouse events when hit testing returned null.
- Fixed Crash when changing selected item in a ComboBox with a SelectionBoxItemTemplate set.
- Fixed Unnecessary clipping when mixing elements with different UseLayoutRounding values.
- Fixed Horizontal size of ComboBox Popup gets clipped if inside a Viewbox bigger than screen width.
- Fixed Improved error descriptions from filesystem.
- Unity Fixed Error when trying to register classes from assemblies returning empty reflection information.
- Unity Fixed problem when noesisGUI was not the only native plugin present in an Unity project.
- Unity Fixed rare crash when pressing Stop inside the editor.

# Version 1.1.5

- Implemented CombinedGeometry GetBounds and Contains point.
- Improvements to integration tutorial regarding saving and restoring state. Fixed GL sample.
- Added IVGLFont::GetGlyphAdvance() function.
- Unity UIRenderer fully qualified in Unity to avoid name collisions.
- Unity Touch sample improved with scale min/max values.
- Unity Exposed Noesis.Font class. Font.GetGlyphAdvance(uint ch) returns the advance for the specified character.
- Unity Improved memory efficiency of proxies.
- Unity Improved the stability of the plugin. Now the error handler mechanism is a lot faster inside the Editor and more robust.
- Fixed Crash when GPU queries not supported.
- Fixed Problems with TextBox.MaxLength when inserting non-ascii tex.
- Fixed Problem with KeyboardNavigation using arrow keys.
- Fixed FrameworkElement Width & Height value validation. It was failing for NaN values.
- Fixed Glitch when rendering text rotated by 180 degrees.
- Fixed RenderNodes correctly unconnected on Renderer destruction. This was causing crashes on shutdown.
- Fixed ContentPresenter and ItemsPresenter now disconnects content when template is removed.
- Fixed In rare occasions IRenderer::WaitForUpdate() was locking for ever.
- Fixed Tab/Directional navigation: now selected item gets the focus.
- Unity Fixed UnityEditor.DockArea.OnGUI() error messages.
- Unity Fixed Memory leak when returning const references from math structs.
- Unity Fixed Classes belonging to C# proxies are now always destroyed in the main thread. It was unsafe doing it in the garbage collector thread.
- Unity Fixed ControlGallery sample working in iPad retina.

# Version 1.1.4

- Support for specifying a StaticResource in the Binding.Source property of a xaml.
- Support for using ItemsControl directly in a xaml.
- Support for "./" in UriConverter paths.
- Minimal improvements to Images Tutorial in the section "Generating Images at Runtime".
- Substitution of glyphs not found in the font file with the [replacement character](http://www.fileformat.info/info/unicode/char/0fffd/index.htm). (U+FFFD or a simple question mark).
- UI Clipboard implemented using operating system clipboard.
- Improved error messages when parsing SVG paths.
- Improvements to [Class Hierarchy](/Gui.Core/_ClassHierarchy.md) documentation. Class methods added.
- Unity Added support for PropertyChangedCallback when creating PropertyMetadata for dependency properties.
- Unity Removed "using Noesis" from Unity samples. Now all class names are fully qualified to avoid name collisions with user classes.
- Unity UserControls defined in samples moved to Assets/NoesisGUI/UserControls. This folder will contain any UserControl we develop.
- Unity Added DependencyProperty.RegisterAttached() function to match WPF API.
- Unity Improved API for Point, Transform2, Transform3, Matrix2, Matrix3, Matrix4. Deleted the 'f' at the end of the class name. For example, Transform2f has been renamed to Transform2.
- Fixed Added error message when NullExtension can't find target property.
- Fixed Bug with IUITreeNode when setting DataContext property to itself.
- Fixed Bug in TwoWay bindings when binding expression needed a full reevaluation.
- Fixed Bug in nested ResourceDictionaries when they are loaded more than once.
- Fixed Bug when selecting text during GotFocus event after clicking down over TextBox.
- Fixed Bug in TextBox not accepting characters with accents.
- Fixed Robustness improvements when using very small or very big matrices.
- Fixed Bug in TimeManager when transferring animations from a loaded xaml to the Renderer TimeManager.
- Fixed Bug when calculating the transformed bounds of a render node.
- Fixed TextBox edit problems on OSX.
- Fixed Changes to Clip geometry are now correctly notified to Visual, to update its bounding box.
- Unity Fixed Rendered content was lagging one frame from Unity. This implied lagging performance to user.
- Unity Fixed Crash when an Unity texture used by a xaml was destroyed.
- Unity Fixed Occasional crash when closing.
- Unity Fixed Bug in UnityBindings that were not restoring focused element after window deactivation.
- Unity Fixed Bug in UnityBindings when an error was thrown while freeing RendererInfo resources during shutting down.
- Unity Fixed Problems with StreamGeometryContext not closing on dispose solved.
- Unity Fixed Memory leaks.
- Unity Fixed Texture2D flickering in Android.
- Unity Fixed "Noesis.dll not unloaded" error after stopping Unity Player.

# Version 1.1.3

- PPAA algorithm (antialiasing emulation without using GPU full-scene antialiasing) reimplemented from scratch. Now it is faster and without glitches.
- Improved tessellation algorithm. Better generation of triangles.
- Improvements to XAML parser: crashes fixed, error messages improved.
- Improved CompilerSettings.h to avoid polluting clients code.
- Improved threading performance of XamlPlayer.
- New statistics panel added to XamlPlayer (F2, SHIFT + F2)
- New debug modes in XamlPlayer: wireframe (CTRL + W), overdraw (CRTL + O) and color batch (CTRL + B).
- Size optimization in our binaries. The size of noesis.dll has been reduced.
- Added support for FontFamily syntax "FontPath/FontFile.ext#FontFamily". This syntax is used by Blend when you add a font file (a .ttf for example) to the project and select it.
- Exposed TextBox.CaretIndex property.
- Improvements to documentation: new core documents (memory, reference counting, boxing, delegates) added to index.
- New tutorial: [Optimizing NoesisGUI Performance](/Gui.Core/Optimizing.md).
- Unity Added support for modifying scripts while in Play mode.
- Unity Added support for creating a TextureSource from any type of UnityEngine.Texture objects (video, render texture, texture).
- Unity BindingOperations exposed to Unity.
- Unity Debugging flags exposed in NoesisGUI component.
- Fixed Update Z-order when inserting a child in a VisualCollection.
- Fixed Crash when using a TemplateBinding outside a ControlTemplate.
- Fixed Opacity groups rendering glitches.
- Fixed Projection glitches.
- Fixed Renderer stats were not working.
- Fixed Geometry loses quality when placed closer to right side of screen due to half float precision.
- Fixed Border issue when drawing images.
- Fixed When Building resources that use Binding, sometimes the properties were not bound properly.
- Fixed Bindings were not using the target property converter if available.
- Fixed ComboBoxItem IsSelected was not updating ComboBox.SelectedItem correctly.
- Fixed StreamGeometryContext now calls automatically StreamGeometry.Close() when is destroyed, as it occurs in WPF.
- Fixed Crash in XamlPlayer when resizing.
- Unity Fixed As<T>() crashes.
- Unity Fixed Memory issues. XAML resources were not properly unloaded from memory.

# Version 1.1.2

- ScrollViewer: implemented PanningMode, PanningDeceleration and PanningRatio.
- Implemented inertia in touch manipulations.
- Implemented PasswordBox control.
- New tutorial: [Touch and Manipulation](/Gui.Core/TouchTutorial.md)
- SamplesGallery demo added to OSX SDK.
- Added constructors for PropertyPath and Binding accepting a DependencyProperty as path.
- Improved Image tutorial with a note about premultiplied alpha.
- Improved Unity tutorial with information about stencil buffer.
- Unity Support for Unity standalone in batchmode.
- Unity RenderTexture reimplemented. Now the implementation is a lot simpler. OSX crashes fixed.
- Unity Mouse events are ignored in mobile platforms. We only consider Touches.
- Unity All scene samples moved to the same folder. Added a default 3D scene.
- Unity Optimized the size of commands sent to the GPU.
- Unity Fixed offscreen images in render to texture and deferred rendering.
- Unity Fixed hit testing when 2+ render to texture being used.
- Unity Added an icon for NoesisGUI component.
- Unity Errors and warnings displayed in the component.
- Unity Added menus for Release Notes and Bug Reporting.
- Unity New Touch sample.
- Unity Added support for creating PropertyMetadata using an extended Unity Type as default value.
- Unity Added support for dependency properties of enum type.
- Unity Improved error checking when working with user controls and dependency properties.
- Fixed Recursion problems during layout process that occurred sometimes with ScrollViewers.
- Fixed Enabled MipMapping in GUI images.
- Fixed Images changing size when being updated.
- Fixed Loading errors in SamplesGallery demo.
- Fixed memory problem with Dependency Objects in OSX 64bits.
- Fixed Right aligned text manages now correctly trailing spaces on ending lines.
- Fixed Added error messages when non valid items are inserted into a collection.
- Fixed Proxies not raising Destroyed event and bindings crashed on shutdown.
- Fixed TextBox losing focus when virtual keyboard was shown.
- Fixed Dependency Object validate callback was being called with an invalid pointer to the value.
- Fixed Memory overflow when handling errors (this is the main reason v1.1.1 was so unstable).
- Fixed Parser now ignores Setter/Trigger/Condition values when property is not found.
- Unity Fixed managed exceptions crashing Unity in OS X.
- Unity Fixed Unity scene disappearing in iOS and Android.
- Unity Fixed headers for missing functions in proxies.
- Unity Fixed PPA gets disabled on resize.

# Version 1.1.1

- Implemented the following multi touch events (working in Unity, iOS, Android and Windows8). Documentation and samples will be added in the next version.
  - TouchDown
  - TouchMove
  - TouchUp
  - TouchEnter
  - TouchLeave
  - GotTouchCapture
  - LostTouchCapture
  - ManipulationStarting
  - ManipulationStarted
  - ManipulationDelta
  - ManipulationCompleted
- Added IRenderer::TouchDown, IRenderer::TouchMove, IRenderer::TouchUp to inject touch events.
- Improvements in error reporting for 64 bits platforms.
- Fixed An element that needed to be clipped because of max size constraints was not always being clipped.
- Fixed ComboBox item selection crash when holding mouse button.
- Fixed crash when using an empty ListView in xaml.
- Fixed strange random crash in UIElement.
- New converters for MatrixTransform and Transform (eg: <Rectangle RenderTransform="1 0 0 1 50 50"/>).
- Fixed Unity crashing when building xamls using incorrect DependencyProperties. Now an error is displayed.
- Support for DependencyProperties of type Color, Point, Rect, Size and Thickness.
- Unity Fixed Dependency properties in Unity extended classes were being serialized twice.
- Unity Added support for UnityEngine.RenderTexture to create a TextureSource within Unity. Now, Unity scene renders can be integrated inside NoesisGUI panels.
- Unity Fixed RoutedEventArgs.source was missing.

# Version 1.1.0

- Unity Improved C# API. Please read tutorials because old code need to be updated.

> - No more need of a swigCPtr member, custom constructors, Dispose or static Register function on extended classes.
> - Dependency properties are now registered in the static class constructor.
> - Classes are now extended by specifying the [Noesis.Extended] class attribute.
> - UserControl associated xaml is now specified by the [Noesis.UserControlSource(string)] class attribute.
> - Notifications of property changes are now done using NotifyPropertyChanged(string).
> - SuppressUnmanagedCodeSecurity attribute added to PInvoke functions.
> - Improvements to the following documentation:
>   - Unity3D Tutorial.
>   - Extending NoesisGUI Tutorial.
>   - Commands Tutorial.
>   - UserControl Tutorial. Includes new ColorPicker sample.

- Unity Added support for changing Image.Source at runtime by creating a TextureSource from a UnityEngine.Texture2D.
- Two new sections added to Images Tutorial: 9-Slice Scaling and Generating Images at Runtime.
- Added FrameworkElement.GetTemplateChild() and FrameworkTemplate.FindName() was modified to accept a templated parent element like in WPF.
- Unity Added Enable Keyboard/Mouse toggle to NoesisGUIPanel component in Unity.
- Unity Missing functions and types exposed to Unity API:
  - ListBox.SelectedItems.
  - ListView and ListViewItem.
  - Nullable types for Color, Point, Rect, Size and Thickness.
- Improved Binding.StringFormat implementation. Updated Binding tutorial.
- Markup parser in XamlImporter improved.
- Fixed Storyboard is constructed now with the children collection always created.
- Fixed Crash when using a StoryBoard that can't resolve target names.
- Fixed Bug when an exception was thrown while creating a Renderer.
- Fixed Commas are now optional specifying a MatrixTransform.Transform in xaml.
- Fixed Text blurriness in positions above 1024px.
- Fixed Slider.IsMoveToPointEnabled was not working properly for vertical sliders.
- Fixed Unity Problems with Alt+Tab when in fullscreen.
- Fixed Unity Error messages with internal path "Unity/Unity/" cleaned.
- Fixed Unity Fixed rendering glitches in standalone.

# Version 1.0.4

- New platform: Linux, native runtime and Unity standalone player
- New 64 bits platforms for OS X and Windows
- Size of runtimes considerably reduced
- Default style modified to reflect local properties set in controls. For example <Button Background="Red"/> now renders a button with a red background, instead of using the default color for the style
- New sample in ControlGallery showing buttons with different styles
- Implemented Mouse.GetPosition() relative to an element
- Unity VisualTreeHelper.HitTest exposed to Unity
- Unity HitTesting for render texture using RaycastHit.textureCoord. GameObject needs a valid MeshCollider. Unity tutorial updated
- Fixed Fixed ListBox crashing when changing items that use ItemTemplate
- Fixed When changing style of the inner ScrollViewer of a TextBox internal TextBoxView was not correctly set and measured
- Fixed TextBox clipping was lost when the style of the internal ScrollViewer changed
- Fixed TextBox was not updating the insertion point and selection indexes when Text property was set through code
- Fixed Unity UV coordinates were vertically flipped with respect to Unity convention
- Fixed Unity Null string objects in unity are now treated as string.Empty
- Fixed Unity Improved stability when errors happening in native
- Fixed Unity Fixed a rare crash when resizing Unity standalone

# Version 1.0.3

- New Tutorial: [First Steps with Blend in Unity](/Gui.Core/BlendTutorial.unity.md)
- Added StreamGeometry converter to allow things like this: <StreamGeometry>M0,0 L100,0</StreamGeometry>
- Implemented callbacks for showing software keyboard on touch devices
- Improved text rendering with transforms. Now text inside a Viewbox displays without blurriness
- Unity Improved error messages when building resources
- Unity An error is shown when executing on a platform whose resource cache was not built
- Unity Many small fixes that improve Unity stability
- Fixed Offscreen atlas algorithm giving negatives values and crashing sometimes
- Fixed Masking problems that were causing scrollviewers clipping issues
- Fixed sdcard accessing problems solved in android
- Fixed Unity Problems with properties in C# on classes extending NoesisGUI
- Fixed Unity TextBox.AcceptsReturn not working

# Version 1.0.2

- Fixed Unity Deferred lighting issues
- Fixed Unity Render artifacts with DirectX. NoesisGUI was corrupting the scene of Unity
- Fixed Unity OpenGL stencil buffer glitches
- Fixed Unity Render performance was very poor on some GPU cards
- Fixed Unity Unity scripts updated, robustness against errors improved
- Fixed Unity LoadScene is now possible in Unity
- Fixed Unity Problem with properties in c#. They were not properly serialized. Read-only properties crashing.
- Fixed Unity Input event args are now correctly exported to Unity
- Fixed Unity Shift key was ignored due to a bug in Unity Event.current notification
- Fixed Unity Navigation tab working now for Unity
- Shader used for masks optimized in GL ES
- Improved batching of draw image
- Fixed Compatibility problem in Windows8, noesis library was not unloaded correctly
- Gui/3rdParty package copied to <https://github.com/Noesis/noesisgui-contrib>
- Fixed broken links to Tutorials. Now, each tutorial is a zip included inside the documentation
- Improvements to index documentation. Now tutorials for native and unity are separated
- Improvements to Styling Tutorial. Sample using Themes added.
- Improvements to Text Tutorial informing about .font resources
- Grid issues:
  - Static functions for setting grid attached properties were using the incorrect type.
  - Modifications of grid attached properties were not notifying to the parent grid. The same happened for DockPanel Dock attached property.
- TextBox events (KeyDown, KeyUp, TextInput, etc) were not calling user handlers.

# Version 1.0.1

- Unity: NoesisGUI menu moved from Component to Window top menu entry because Unity3D is buggy and our menu was disappearing sometimes.
- Text tutorial improved.
- README file and root index.html added to .unitypackage.
- Minor changes to Unity tutorial.
- SamplesGallery builds needed resources automatically. Now it doesn't crash the first time it is executed.
- Fixed XamlPlayer crashing when maximized
- Fixed Unity was unable to build .xaml resources when the active platform was not PC & MAC.
- Fixed Improved Unity stability. Crashes when clicking Play or Stop resolved.
- Fixed inheriting from extended classes in Unity was not working.
- Fixed Added namespace to Unity class name so xamls designed in Blend using namespaces work correctly.
- Fixed Binding FallbackValue was not serialized correctly when it contains a boxed value.
- Fixed ControlGallery TextBlock sample was missing.
- Fixed Clipping problems in Unity 4.2.

# Version 1.0.0

- All tutorials have been improved. Many examples were outdated. Now every sample that is mentioned in the documentation is included in the package Gui/Tutorials and can be viewed with XamlPlayer. Following the suggestions from beta testers we have explained those concepts that were not clear.
- New tutorial: [Extending NoesisGUI](/Gui.Core/ExtendingTutorial.md).
- New tutorial: [Commands](/Gui.Core/CommandsTutorial.md)
- New tutorial: [Bindings](/Gui.Core/DataBindingTutorial.md)
- API for integration NoesisGUI within an application has been simplified.
- Unity improvements:
  - Setting a SDK is not needed anymore.
  - File Resources .xaml and .font can be stored in any directory of the project. There are no restrictions now.
  - Links for documentation included inside unity.
  - New samples added.
  - New platforms added: OS X and iOS.

# Version 0.9.9

## Features

- OpenGL renderer optimized. Many improvements have been incorporated.
- Improved OpenGL ES 2.X implementation optimized for tiled based architectures. Now samples run fine in Android.
- New platform: iOS. iPhone and iPad supported with iOS 5 or later.
- New SDK platform: Mac OS X v10.5 or later. This SDK is yet experimental and not as complete as the Windows version.
- Support for multisample added in GL. For now only the extensions APPLE\_framebuffer\_multisample, EXT\_framebuffer\_multisample and EXT\_multisampled\_render\_to\_texture are supported.
- Opacity Groups (aka Render to Texture) have been heavily optimized. Now, you must indicate the resolution of off-screen surfaces when constructing a xaml renderer. By default, two extra textures of the same resolution are created.
- Improvements to the [Integration Tutorial](/Gui.Core/SDKGuide.md). iOS integration described. Simplified interface for loading a xaml and setting up the renderer.
- Tessellation quality improved. Now the aspect of curves at medium quality is better.
- Glyph atlases are now a single channel (A8) texture on mobile platforms.
- Added default style support that is loaded by default with each xaml. Can be overridden by IUISystem::SetTheme().
- Added support for strings in ResourceDictionary.
- Unity improvements:
  - New unity directory layout following the suggestions from the forum.
  - UserControls can be created now on Unity.
  - [Unity3d Tutorial](/Gui.Core/Unity3DTutorial.md) updated with UserControl, Binding and Commands information.
  - Primitives sample updated with a ListBox and a ColorPicker.
  - New LoadXaml function.
  - Extended classes are automatically registered now.
  - NoesisGui API is now inside the namespace Noesis.
  - Added Noesis.Reflection.DoLaunchChangedEvent() function to implement INotifyPropertyChange in Unity extended classes.
  - New demo, Shooter Demo, distributed as an standalone unity project.
  - Video tutorial created with the [Shooter Demo](https://vimeo.com/65549290).
  - Added a Command (MVVM) example.

## Bug fixes

- Fixed Masking (Stencil) was not working properly on several scenarios.
- Fixed DependencyProperty was not taking into account Condition.SourceName to search for the property in the appropriate type.
- Fixed DynamicResourceExpression was not returning UnsetValue when resource key was not found.
- Fixed VisualState and VisualTransition were not implementing IUITreeNode and name lookups failed.
- Fixed BindingExpression was failing when DataContext was being set from code.
- Fixed Thickness, Point and Size parsers accepting now " " and "," as separators.
- Fixed UnityDeviceDX9 rendering xamls to textures and to camera in the same scene were failing.
- Fixed Problems reloading NoesisGUI components in standalone mode.
- Fixed Crash when rendering to a texture that was not being used.
- Fixed Atlases between surfaces was not shared properly (same glyphs were inserted several times).
- Fixed When closing a Pop-up sometimes it was clearing any binding set in the IsOpen property.
- Fixed TextBox handling Unicode characters properly.
- Fixed Bugged animation in Button Pressed state in NoesisStyle.
- PlaneProjection FOV adjusted to match WPF.

# Version 0.9.8

## Features

- Many improvements in the integration layer between NoesisUI C++ API and Mono. Now, Noesis classes can be extended to create new controls. All samples upgraded with the new improvements.
- Unity pipeline simplified. Now changes to assets are automatically detected. You can be editing a XAML, save the changes and the results are automatically shown on Unity.
- New Unity sample: Primitives.
- [Unity3d Tutorial](/Gui.Core/Unity3DTutorial.md) updated.
- Android platform. This is the first release to include runtime support for Android. Both standalone and Unity environment are supported. Although this is still a preliminary work and many optimizations are pending, all the samples are working properly.
- Improvements to the [Integration Tutorial](/Gui.Core/SDKGuide.md). Android integration described.
- Functions in GUI receiving a BaseComponent\* that accept a boxed value, are now overloaded with a string parameter to make it easier to use in this case (90% of the time). The functions affected are:
  - IList: Set, Add, Insert
  - ContentControl: SetContent
  - ContentPresenter: SetContent
  - FrameworkElement: SetTag
- Added more documentation to [Class Hierarchy](/Gui.Core/_ClassHierarchy.md) list. All main classes are now documented.
- OpenGL renderer optimized.
- New tutorial: *OpenSceneGraph integration*.

## Bug fixes

- Fixed Unity crash when the device is lost.
- Fixed Items in ItemsControl not updated when using ItemSource external collection.
- Fixed xaml being modified with Unity editor in play mode

# Version 0.9.7

## Features

- New Unity demos: MasterMind, RenderToTexture and Primitives.
- New sample: CarHud
- Implemented render to texture in Unity
- UnityExporter console application deprecated. A new tool is implemented directly inside the editor of Unity3d
- Improvements to [Unity3d Tutorial](/Gui.Core/Unity3DTutorial.md), describing all the things that are new
- Several improvements to text rendering. Subpixel positioning implemented.
- OpenGL RenderSystem implementation
- Improvements to the [Integration Tutorial](/Gui.Core/SDKGuide.md). OpenGL integration described
- XamlPlayer: Drag&Drop feature removed. It was confusing to the user where resources could be dragged from
- XamlPlayer: new resource browser panel added to select the XAML to load
- XamlPlayer: animations panel now shows a list of storyboards each one with its own play / pause / stop buttons.
- XamlPlayer: wait for vsync when rendering. When the window is not active, it stops continuously rendering
- Improvements to the [Class Hierarchy](/Gui.Core/_ClassHierarchy.md) documentation. All supported classes, with properties and events are summarized.

## Bug fixes

- Fixed If available the OS/2 table of OpenType fonts is used. Same behavior than WPF.
- Fixed DrawText snapping parameter removed. Now text is like the rest of primitives, that are aligned at integer positions
- Fixed Text rendering with alpha was not correct
- Fixed tessellation of circles generated extra triangles in some scenarios
- Improvements to BuildTool that sometimes never returned. Background and foreground color properly restored

# Version 0.9.6

## Features

- New demo: TicTacToe.
- New demo: SamplesGallery. Added as a scene to the unity package too.
- New tutorial: [Layout & Panels](/Gui.Core/LayoutPanelTutorial.md).
- New tutorial: *OGRE Tutorial*.
- New samples: Brushes, Butterfly, Canvas, DockPanel, Grid, Palette, ProgressBar, StackPanel, StatusBar, ToolBar, Tiger, WrapPanel.
- Improvements to the Unity runtime. Now it is smaller and faster. Errors are properly handled now.
- Changes to Enums in C#. For example, HorizontalAlignment\_Center is now HorizontalAlignment.Center.

## Bug fixes

- Many bugs fixed related to bindings of NoesisGui to C# (affecting the Unity runtime).
- Fixed Unity runtime crashing on exit.
- Fixed LineGeometry was not calculating correctly its bounds when a non identity transform was used.
- Fixed Compilation errors with Visual Studio 2010.
- Fixed UserControl was not copying correctly triggers during loading process.

# Version 0.9.5

## Features

- New tutorial: [Unity3d Tutorial](/Gui.Core/Unity3DTutorial.md)
- Improvements to the [Integration Tutorial](/Gui.Core/SDKGuide.md)
- Fonts with embedded bitmaps were not properly rendered.
- New IStoryboard interface.
- Implemented PauseStoryboard, ResumeStoryboard and StopStoryboard triggers actions.
- Added Pause/Resume/Stop buttons to XamlPlayer animations panel.
- Improvements to stroke generation.
- DirectX InputSystem no longer used in the SDK.
- PixelWidth and PixelHeight properties added to BitmapSource and TextureSource.
- Many functions have been changed from receiving a smart pointer to a raw pointer.

## Bug fixes

- Fixed EventTrigger was not invoking trigger actions with the correct target and namescope.
- Fixed Focused Button was not launching Click event when space bar was pressed.
- Fixed PropertyPath path was being serialized twice.
- Fixed When a merged dictionary contains more than one merged dictionary, an incorrect error was thrown.
- Fixed PushTransform matrix multiplication order in UIElement was wrong
- Fixed Compilation errors with Visual Studio 2010

# Version 0.9.4

## Features

- New exporter for [TexturePacker](http://www.texturepacker.com/) inside *Gui/3rdParty/Content/TexturePacker*. With this plugin atlases that are compatible with NoesisGui can be generated. See the [Images Tutorial](/Gui.Core/ImagesTutorial.md).
- Animations on sample *Time.xaml* are now not launched automatically, use the animation panel to launch them.
- Support for Triggers in DataTemplates.
- ListView control implemented with column reordering, and *ListView.xaml* sample added to Gui/Samples.
- Improvements to text rendering quality.
- Support for stroking text in TextBlock. See included *Text.xaml* example in Gui/Samples.
- TextBox control implemented with Copy/Cut/Paste commands. *TextBox.xaml* example added to Gui/Samples.
- ScrollBar and Slider controls now react to key input gestures when control is focused.

## Bug fixes

- Fixed Track element was not taking IsDirectionReversed into account in arrange code to layout DecreaseButton and IncreaseButton correctly.
- Fixed Crash building a Style without a TargetType.

# Version 0.9.3

## Features

- Added ImageSource.Width and ImageSource.Height properties.
- ImageSource now uses image resolution to calculate its size (width and height) in device independent units.
- All TileBrush tiling modes (None, Tile, FlipX, FlipY, FlipXY) correctly implemented.
- New [tutorial](/Gui.Core/ImagesTutorial.md) for images added. Related examples added: ImageAtlas, ImageBrushStretch, ImageBrushTile and ImageBrushViewBox.
- Automatic atlases no longer generated. Now atlases must be created manually.
- Image.Source and ImageBrush.ImageSource properties are now of ImageSource type. Added ImageSourceConverter to convert image paths into a valid ImageSource (TextureSource if a texture compiler is available, or BitmapSource otherwise).
- XamlPlayer now shows and can launch animations found in the Resources property of the loaded XAML root.
- New option in XamlPlayer to view loaded XAML in wireframe mode.
- Support for Style.BasedOn property implemented.

## Bug fixes

- Fixed GridView.ColumnHeaderContainerStyle property was registered with a wrong name.
- Fixed ClipToBounds was not correctly implemented.

# Version 0.9.2

## Features

- Xaml files that define a ResourceDictionary are now cached when they are loaded for the first time.
- Mouse CaptureMode SubTree implemented.
- Now ComboBoxes, Menus and ContextMenus capture the mouse while its Popup is open.
- Added a Find() function to IDictionary so Contains() + Get() consecutive calls can be optimized.
- INameScope FindName() now returns a raw pointer.
- IUITreeNode FindNodeResource() and FindNodeName() now return a raw pointer.

## Bug fixes

- Fixed Behaviour of Popup and its StaysOpen property was not correct.
- Fixed Problems with HitTest clipping and opacity groups inside Popup elements.
- Fixed The order of events raised when Keyboard focus changed is now correct: if the PreviewGotKeyboardFocus event or the PreviewLostKeyboardFocus event is handled, keyboard focus does not change.
- Fixed Destroying a ContextMenu or ToolTip while its popup is open was crashing.
- Fixed Referencing resources of a merged dictionary inside another merged dictionary was failing.

# Version 0.9.1

## Features

- Added ResetInputState() to IRenderer, so mouse buttons and keys that were pressed can be reseted when an application is deactivated.
- Optimized Border geometry generation using StreamGeometryContext, and now is robust against limit cases (corners bigger than border size, etc.).
- UIResource dependencies are now stored as GUID instead of strings (it is recommended to rebuild UI resources).
- Implemented PushClip drawing context command (to be used within OnRender).
- Added Timeline Completed event to reflection so it can be used from XAML.
- Optimized PropertyPath memory space used by instances, and path is now parsed and serialized to avoid parsing in runtime as much as possible (it is recommended to rebuild UI resources).
- Added static methods to RelativeSource to obtain unique instances of Self, TemplatedParent, or PreviousData relative sources.
- Improvements to XamlReader to detect errors writing markup extensions or the {} escape sequence.

## Bug fixes

- Fixed DependencyProperties that Inherits didn't notify OnSubPropertyChanged correctly.
- Fixed Grid layout of star cells was failing when there were 2 or more cells with the same measure size.
- Fixed Track that was part of a ScrollBar didn't specify a minimum size for the Thumb control.
- Fixed BlendTutorial color selector sliders were not correctly initialized.
- Fixed ListBox in single selection mode was failing when Ctrl clicking an item.
- Fixed Some DependencyObject derived classes were not constructing the UI tree correctly, causing failures during resource look up.

# Version 0.9.0

First version released in the private beta program.