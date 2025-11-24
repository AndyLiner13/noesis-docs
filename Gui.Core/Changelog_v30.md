Source: https://www.noesisengine.com/docs/Gui.Core.Changelog_v30.html

# NoesisGUI 3.0 Release Notes

# Version 3.0.12

*Released 4 May 2021* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Added support for all types of [Popup](/Gui.Core/_Popup.md) animations: *Fade*, *Slide*, and *Scroll*.
- Enhancement Added *Focus* method to allow users to focus controls in code without engaging.
- Enhancement Improved custom controls documentation ([#1965](https://www.noesisengine.com/bugs/view.php?id=1965)).
- Enhancement C# Added *IsGrabbed()* helper function to extends code ([#1974](https://www.noesisengine.com/bugs/view.php?id=1974)).
- Enhancement Unity Added error message when an explicit dependency cannot be found ([#1985](https://www.noesisengine.com/bugs/view.php?id=1985)).
- Fixed Binding not reevaluated if source property changed while invalidating target property ([#1945](https://www.noesisengine.com/bugs/view.php?id=1945)).
- Fixed Crash generating [TickBar](/Gui.Core/_TickBar.md) for a [Slider](/Gui.Core/_Slider.md) with many ticks.
- Fixed Crash when [BindingExpression](/Gui.Core/_BindingExpression.md) destroyed while invalidating target.
- Fixed [ComboBox](/Gui.Core/_ComboBox.md) not focusing or scrolling when no default selected item ([#1958](https://www.noesisengine.com/bugs/view.php?id=1958)).
- Fixed [Tooltip](/Gui.Core/_ToolTip.md) issues ([#1879](https://www.noesisengine.com/bugs/view.php?id=1879)).
- Fixed [Viewbox](/Gui.Core/_Viewbox.md) also scales [Tooltip](/Gui.Core/_ToolTip.md) ([#1956](https://www.noesisengine.com/bugs/view.php?id=1956)).
- Fixed [TextBox](/Gui.Core/_TextBox.md) crashing when using a [ScrollViewer](/Gui.Core/_ScrollViewer.md) without *IScrollInfo* ([#1968](https://www.noesisengine.com/bugs/view.php?id=1968)).
- Fixed Incorrect layout of [Path](/Gui.Core/_Path.md) with *Uniform* stretch inside [WrapPanel](/Gui.Core/_WrapPanel.md) ([#1972](https://www.noesisengine.com/bugs/view.php?id=1972)).
- Fixed [GridView](/Gui.Controls/_GridView.md) *Column* is frozen ([#1973](https://www.noesisengine.com/bugs/view.php?id=1973)).
- Fixed [TabControl](/Gui.Core/_TabControl.md) focus inconsistent with WPF standard ([#1979](https://www.noesisengine.com/bugs/view.php?id=1979)).
- Fixed [DataTemplate](/Gui.Core/_DataTemplate.md) XAML reports duplicate name elements ([#1994](https://www.noesisengine.com/bugs/view.php?id=1994)).
- Fixed Game renders black screen in *OnePlus* phones with *Android 10* ([#1919](https://www.noesisengine.com/bugs/view.php?id=1919)).
- Fixed Compile error in *Error.h* when running static analysis ([#1953](https://www.noesisengine.com/bugs/view.php?id=1953)).
- Fixed XamlPlayer crashing when dropping *App.xaml* files ([#1978](https://www.noesisengine.com/bugs/view.php?id=1978)).
- Fixed Const correctness for collection methods *IndexOf*, *Contains* and *Remove* ([#1997](https://www.noesisengine.com/bugs/view.php?id=1997)).
- Fixed *ManipulationDelta* events only raised when finger is moved or on inertia.
- Fixed Cancel manipulation inertia when source element removed from tree.
- Fixed Compiling error on Linux ([#1944](https://www.noesisengine.com/bugs/view.php?id=1944)).
- Fixed Item collection failing when calling *Move* with same index.
- Fixed C# .NET 5 has broken *RunClassConstructor* workaround ([#1897](https://www.noesisengine.com/bugs/view.php?id=1897)).
- Fixed C# Crash destroying [ItemsControl](/Gui.Core/_ItemsControl.md) if attached to its [ItemContainerGenerator](/Gui.Core/_ItemContainerGenerator.md) events.
- Fixed C# Keyboard missing *ClearFocus()* method ([#1983](https://www.noesisengine.com/bugs/view.php?id=1983)).
- Fixed Unity Preview stats compatible with both Light/Dark themes.
- Fixed Unity Crash in Editor after entering play mode ([#1943](https://www.noesisengine.com/bugs/view.php?id=1943)).
- Fixed Unity Can't get ApplicationResources dictionary ([#1962](https://www.noesisengine.com/bugs/view.php?id=1962)).
- Fixed Unity Crash when calling *LoadXaml()* in *NoesisView* without being enabled ([#1964](https://www.noesisengine.com/bugs/view.php?id=1964)).
- Fixed Unreal Random crashes when modifying *Blueprint* classes.
- Fixed Unreal Removed *RestoreUITexturePNGPremultipliedAlpha* from *NoesisSettings* ([#1959](https://www.noesisengine.com/bugs/view.php?id=1959)).
- Fixed Unreal Array notifications for members of parent classes not working ([#1960](https://www.noesisengine.com/bugs/view.php?id=1960)).

# Version 3.0.11

*Released 15 March 2021* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature Unreal Support for [localization](/Gui.Core/UnrealTutorial.md#localization) using *LocText* and *LocTable* extensions.
- Enhancement Added new [RadialMenu](https://github.com/Noesis/Tutorials/tree/master/Samples/RadialMenu) sample.
- Enhancement View exposing threshold parameters for *Tapped*, *DoubleTapped* and *Holding* ([#1931](https://www.noesisengine.com/bugs/view.php?id=1931)).
- Enhancement Added information about touching fingers to manipulation events ([#1913](https://www.noesisengine.com/bugs/view.php?id=1913)).
- Enhancement C# Added support for disabling *Keyboard*, *Mouse* or *Touch* input events in a [Window](/App.ApplicationLauncher/_Window.md).
- Fixed Manipulation inertia generating *NaN* values for angular velocity.
- Fixed [Popup](/Gui.Core/_Popup.md) not checking if target element is in the tree ([#1928](https://www.noesisengine.com/bugs/view.php?id=1928)).
- Fixed Crash updating inherited values with closing [Tooltip](/Gui.Core/_ToolTip.md) ([#1933](https://www.noesisengine.com/bugs/view.php?id=1933)).
- Fixed [ContextMenu](/Gui.Core/_ContextMenu.md) and [Tooltip](/Gui.Core/_ToolTip.md) are no longer logical children to match WPF.
- Fixed Error converting [PathGeometry](/Gui.Core/_PathGeometry.md) *Figures* property from string ([#1929](https://www.noesisengine.com/bugs/view.php?id=1929)).
- Fixed [FormattedText](/Gui.Core/_FormattedText.md) GetBounds(), GetGlyphPosition() and HitTest() returning inverted y-coordinate ([#1878](https://www.noesisengine.com/bugs/view.php?id=1878)).
- Fixed Better antialiasing geometry for underlines when [PPAA](/Gui.Core/AntialiasingTutorial.md) enabled ([#1922](https://www.noesisengine.com/bugs/view.php?id=1922)).
- Fixed [Slider](/Gui.Core/_Slider.md) Ticks disappearing ([#1924](https://www.noesisengine.com/bugs/view.php?id=1924)).
- Fixed Vertical [Slider](/Gui.Core/_Slider.md) rendering ticks in reverse order.
- Fixed Reversed [Slider](/Gui.Core/_Slider.md) rendering selection incorrectly.
- Fixed Crash with more than 5 active manipulations ([#1932](https://www.noesisengine.com/bugs/view.php?id=1932)).
- Fixed RTTI not correctly enabled in Android for official SDKs ([#1855](https://www.noesisengine.com/bugs/view.php?id=1855)).
- Fixed Crash shutting down Gallery if [TextBox](/Gui.Core/_TextBox.md) context menu was opened.
- Fixed Removed PPAA glitches in Menu3D.
- Fixed Unreal Use RuntimeDependencies with *$(BinaryOutputDir)* to manage copying *Noesis.dll*.
- Fixed Unity Crash when *Target* destroyed before [TargetedTriggerAction](/App.Interactivity/_TargetedTriggerAction.md) ([#1930](https://www.noesisengine.com/bugs/view.php?id=1930)).
- Fixed Unity Crash importing XAML with *DP* type not matching default value type ([#1936](https://www.noesisengine.com/bugs/view.php?id=1936)).
- Fixed Unity Warnings when building WebGL with development flag.
- Fixed C# [ChangePropertyAction](/App.Interactivity/_ChangePropertyAction.md) converter not using *InvariantCulture*.
- Fixed App C# Inconsistent behavior in OpenGL RenderContexts ([#1923](https://www.noesisengine.com/bugs/view.php?id=1923)).

# Version 3.0.10

*Released 10 Feb 2021* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Better error message when calling *TransformToAncestor* with non related visuals.
- Enhancement Added *VerifyAccess* to [Visual](/Gui.Core/_Visual.md) functions to detect uses from other threads.
- Enhancement New [Workflow](/Gui.Core/WorkflowTutorial.md) tutorial.
- Fixed Touch on [TextBox](/Gui.Core/_TextBox.md) not receiving focus as expected ([#1918](https://www.noesisengine.com/bugs/view.php?id=1918) [#1887](https://www.noesisengine.com/bugs/view.php?id=1887)).
- Fixed Touch capture not released when cancelling *ManipulationStarted* ([#1883](https://www.noesisengine.com/bugs/view.php?id=1883)).
- Fixed Syntax difference with WPF when using *TimeSpan* in XAML ([#1917](https://www.noesisengine.com/bugs/view.php?id=1917)).
- Fixed Template [DataTrigger](/App.Interactivity/_DataTrigger.md) spams binding log channel when recreating *ItemsSource* collection.
- Fixed Animations using key frames not cloned when used inside templates.
- Fixed Mouse position not reset after cancelling or completing a manipulation.
- Fixed Support optional suffix "Extension" for [MarkupExtensions](/Gui.Core/_MarkupExtension.md) ([#1885](https://www.noesisengine.com/bugs/view.php?id=1885)).
- Fixed Error when [TextBox](/Gui.Core/_TextBox.md) caret blinks inside a [Popup](/Gui.Core/_Popup.md) ([#1907](https://www.noesisengine.com/bugs/view.php?id=1907)).
- Fixed Crash using invalid [MultiBinding](/Gui.Core/_MultiBinding.md) inside a [DataTrigger](/Gui.Core/_DataTrigger.md) ([#1904](https://www.noesisengine.com/bugs/view.php?id=1904)).
- Fixed [MultiBinding](/Gui.Core/_MultiBinding.md) inside [DataTemplate](/Gui.Core/_DataTemplate.md) not working ([#1893](https://www.noesisengine.com/bugs/view.php?id=1893)).
- Fixed [MultiBinding](/Gui.Core/_MultiBinding.md) *Converter* should be called even if inner bindings failed to resolve.
- Fixed Inner bindings *BindingMode* not correctly applied ([#1900](https://www.noesisengine.com/bugs/view.php?id=1900)).
- Fixed Nine-slice *ToolTips* showing lines in the background when opened multiple times ([#1891](https://www.noesisengine.com/bugs/view.php?id=1891)).
- Fixed Crash in *Inspector* when tracking focused element with menus ([#1895](https://www.noesisengine.com/bugs/view.php?id=1895)).
- Fixed Non thread-safe code in *Inspector* *TextureProvider* ([#1898](https://www.noesisengine.com/bugs/view.php?id=1898)).
- Fixed 'GL\_EXT\_buffer\_storage' blacklisted for Mali devices in GL renderer.
- Fixed Unity Crash when entering play while destroying a [ListBox](/Gui.Core/_ListBox.md) ([#1911](https://www.noesisengine.com/bugs/view.php?id=1911)).
- Fixed Unity Crash with effects while idling in scene mode ([#1882](https://www.noesisengine.com/bugs/view.php?id=1882) [#1916](https://www.noesisengine.com/bugs/view.php?id=1916)).
- Fixed C# [TargetedTriggerAction](/App.Interactivity/_TargetedTriggerAction.md) crashing when binding value type to *TargetObject* ([#1908](https://www.noesisengine.com/bugs/view.php?id=1908)).
- Fixed C# Setting *WindowState* *Minimized* not working as expected ([#1914](https://www.noesisengine.com/bugs/view.php?id=1914)).

# Version 3.0.9

*Released 12 Jan 2021* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Unreal plugin updated to UE4.26.
- Enhancement Added support for hyphens to line breaking algorithm ([#1860](https://www.noesisengine.com/bugs/view.php?id=1860)).
- Enhancement Added new [LoadContentAction](/App.Interactivity/_LoadContentAction.md) to set the content of a [ContentControl](/Gui.Core/_ContentControl.md) by loading a XAML file ([#1864](https://www.noesisengine.com/bugs/view.php?id=1864)).
- Enhancement RTTI enabled in Android for official SDKs ([#1855](https://www.noesisengine.com/bugs/view.php?id=1855)).
- Enhancement Added *SetEmulateTouch()* to *View* for touch emulation from mouse input.
- Enhancement App Implemented support for HDPI in macOS display.
- Enhancement C# Added support for custom [MarkupExtensions](/Gui.Core/_MarkupExtension.md) ([#1401](https://www.noesisengine.com/bugs/view.php?id=1401)).
- Fixed Crash destroying [GridViewColumnHeader](/Gui.Controls/_GridViewColumnHeader.md) in [ListView](/Gui.Controls/_ListView.md) ([#1853](https://www.noesisengine.com/bugs/view.php?id=1853)).
- Fixed [ChangePropertyAction](/App.Interactivity/_ChangePropertyAction.md) Value not always updated when action invoked.
- Fixed Crash when inheriting [Binding](/Gui.Core/_Binding.md) or [MultiBinding](/Gui.Core/_MultiBinding.md) and using new class in XAML ([#1861](https://www.noesisengine.com/bugs/view.php?id=1861)).
- Fixed Removed circular reference when using [EventTrigger](/App.Interactivity/_EventTrigger.md) or [TargetedTriggerAction](/App.Interactivity/_TargetedTriggerAction.md).
- Fixed [ListBox](/Gui.Core/_ListBox.md) and [ListView](/Gui.Controls/_ListView.md) not cycling from last to first item ([#1862](https://www.noesisengine.com/bugs/view.php?id=1862)).
- Fixed [ListBoxItem](/Gui.Core/_ListBoxItem.md) automatically being focused even when a foreground element consumed the *MouseDown* ([#1866](https://www.noesisengine.com/bugs/view.php?id=1866)).
- Fixed Crash on MacBook Pro with Radeon GPUs ([#1851](https://www.noesisengine.com/bugs/view.php?id=1851)).
- Fixed Crash unregistering bindings from [Tooltip](/Gui.Core/_ToolTip.md) ([#1872](https://www.noesisengine.com/bugs/view.php?id=1872)).
- Fixed *DoubleTapped* is now properly promoted to *DoubleClick*.
- Fixed Crash closing [Tooltip](/Gui.Core/_ToolTip.md) ([#1875](https://www.noesisengine.com/bugs/view.php?id=1875)).
- Fixed C# Enum [DependencyProperty](/Gui.DependencySystem/_DependencyProperty.md) getting wrong int values ([#1877](https://www.noesisengine.com/bugs/view.php?id=1877)).
- Fixed Unity Crash on [Binding](/Gui.Core/_Binding.md) *GetConverterHelper* when serializing object ([#1867](https://www.noesisengine.com/bugs/view.php?id=1867)).
- Fixed Unity Crash in editor using destroyed texture native pointer ([#1871](https://www.noesisengine.com/bugs/view.php?id=1871)).
- Fixed Unity Circular dependencies in XAMLs causing stack overflow when resolving dependencies ([#1874](https://www.noesisengine.com/bugs/view.php?id=1874)).
- Fixed Unreal *ApplicationResources* and *DefaultFonts* destroyed when loading map ([#1876](https://www.noesisengine.com/bugs/view.php?id=1876)).

# Version 3.0.8

*Released 4 Dec 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Added [NineSlice](https://github.com/Noesis/Tutorials/tree/master/Samples/NineSlice) sample.
- Enhancement Added [DataEventTrigger](/App.Interactivity/_DataEventTrigger.md) to interactivity for view model event triggers.
- Enhancement Created [MessageBox](/App.ApplicationLauncher/_MessageBox.md) user control ([#1833](https://www.noesisengine.com/bugs/view.php?id=1833)).
- Enhancement Offscreen rendering avoided when using element *Opacity* on simple nodes ([#1568](https://www.noesisengine.com/bugs/view.php?id=1568)).
- Fixed [Button](/Gui.Core/_Button.md) *Click* event not raised when pressing gamepad *Accept* with *Alt* key pressed ([#1834](https://www.noesisengine.com/bugs/view.php?id=1834)).
- Fixed Crash on [TextBox](/Gui.Core/_TextBox.md) using template with no 'PART\_ContentHost' ([#1836](https://www.noesisengine.com/bugs/view.php?id=1836)).
- Fixed Changes made to *ApplicationResources* not notified to the tree ([#1802](https://www.noesisengine.com/bugs/view.php?id=1802)).
- Fixed [ItemContainerGenerator](/Gui.Core/_ItemContainerGenerator.md) *StartBatch* and *StopBatch* methods should be public.
- Fixed Missing "template" statements in TypePropertyUtil.h ([#1843](https://www.noesisengine.com/bugs/view.php?id=1843)).
- Fixed D3D11RenderDevice not clearing pixel shader resource slots ([#1844](https://www.noesisengine.com/bugs/view.php?id=1844)).
- Fixed Crash using [MultiBinding](/Gui.Core/_MultiBinding.md) inside [DataTrigger](/Gui.Core/_DataTrigger.md) ([#1784](https://www.noesisengine.com/bugs/view.php?id=1784), [#1812](https://www.noesisengine.com/bugs/view.php?id=1812)).
- Fixed [ListBox](/Gui.Core/_ListBox.md) selection always reverted to last focused item ([#1839](https://www.noesisengine.com/bugs/view.php?id=1839)).
- Fixed C# [FormattedText](/Gui.Core/_FormattedText.md) exposes nothing ([#1831](https://www.noesisengine.com/bugs/view.php?id=1831)).
- Fixed C# Exposed [Texture](/Render.RenderDevice/_Texture.md) properties: *Width*, *Height*, *HasMipMaps*, *IsInverted*.
- Fixed C# *TypeDescriptor* can't find a valid *TypeConverter* for [Brush](/Gui.Core/_Brush.md) ([#1817](https://www.noesisengine.com/bugs/view.php?id=1817)).
- Fixed Unreal Font dependencies with absolute paths or relative paths using '..' not working.
- Fixed Unreal Incorrect *View* and *Texture* dimensions for first frame.
- Fixed Unreal Data binding textures not being reloaded.
- Fixed Unity NoesisPostProcessor 'Sharing violation' exception importing fonts ([#1841](https://www.noesisengine.com/bugs/view.php?id=1841)).
- Fixed Unity Metal assertion 'Already have uncommitted encoder' ([#1832](https://www.noesisengine.com/bugs/view.php?id=1832)).

# Version 3.0.7

*Released 29 Oct 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement PS4 render device performance improvements.
- Enhancement Potential crash when loading several pipelines in Metal render device.
- Enhancement Added support for *BufferStorage* to GL renderer.
- Enhancement Implemented support for setting the global culture ([#1803](https://www.noesisengine.com/bugs/view.php?id=1803)).
- Enhancement Allow moving selected frame in *Inspector* using left/right arrow keys when paused.
- Enhancement App Implemented support for NDK Choreographer in Android to pump frames.
- Enhancement App Added support for EGL\_ANDROID\_get\_frame\_timestamps in GL render context to measure frames.
- Enhancement C++ Matrix and Transform codegen inline improvements.
- Enhancement C# Added *TransformBounds* to *Matrix* class.
- Enhancement Unity Unity Texture supported in DataBinding, internally converted to TextureSource.
- Enhancement Unity Thumbnails are correctly generated when linear rendering is enabled.
- Enhancement Unity Render to texture is no longer using an internal camera ([#1815](https://www.noesisengine.com/bugs/view.php?id=1815)).
- Enhancement Unity Support for explicit update in NoesisView.
- Enhancement Unity Added 'Assets->Create->Noesis Render Texture' ([#1825](https://www.noesisengine.com/bugs/view.php?id=1825)).
- Enhancement Unity NoesisSettings file is now created by default in 'Assets/Resources'.
- Fixed Cancelled drag operations incorrectly notifying allowed effects ([#1648](https://www.noesisengine.com/bugs/view.php?id=1648)).
- Fixed *BringIntoView* ignores target rectangle ([#1810](https://www.noesisengine.com/bugs/view.php?id=1810)).
- Fixed Blur and Shadow fragment shaders unrolled in OpenGL ES to avoid issues in older drivers.
- Fixed [RepeatButton](/Gui.Core/_RepeatButton.md) can crash if unloaded while timer is active.
- Fixed Memory leak when using [ContextMenuService](/Gui.Core/_ContextMenuService.md) *PlacementTarget* ([#1798](https://www.noesisengine.com/bugs/view.php?id=1798)).
- Fixed [Selector](/Gui.Core/_Selector.md) not synchronizing selected index correctly when binding *SelectedValue* ([#1809](https://www.noesisengine.com/bugs/view.php?id=1809)).
- Fixed Wheel scrolling possible with [Menu](/Gui.Core/_Menu.md) opened inside a [ScrollViewer](/Gui.Core/_ScrollViewer.md).
- Fixed Use of deprecated texture2D() in OpenGL 3.1+ shaders ([#1813](https://www.noesisengine.com/bugs/view.php?id=1813)).
- Fixed Character spacing + viewbox does not calculate bounds correctly ([#1824](https://www.noesisengine.com/bugs/view.php?id=1824)).
- Fixed C# ManipulationDeltaEventArgs *DeltaManipulation* incorrectly returning cumulative values.
- Fixed C# ManipulationDelta *Scale*, *Translation* and *Expansion* returning a Vector, as in WPF.
- Fixed Unity Crash entering play or updating XAMLs ([#1806](https://www.noesisengine.com/bugs/view.php?id=1806)).
- Fixed Unity Using Render texture mode with HDRP causes render overlap ([#1811](https://www.noesisengine.com/bugs/view.php?id=1811)).
- Fixed Unity Crash closing Unity after compiling scripts while playing ([#1814](https://www.noesisengine.com/bugs/view.php?id=1814)).
- Fixed Unity iOS Build Errors when using only Metal in Graphics APIs ([#1818](https://www.noesisengine.com/bugs/view.php?id=1818)).
- Fixed Unity Noesis settings asset fields occasionally reset ([#1716](https://www.noesisengine.com/bugs/view.php?id=1716)).
- Fixed Unity Crash destroying [Selector](/Gui.Core/_Selector.md) while compiling script changes.

# Version 3.0.6

*Released 25 Sep 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Added "Auto connect" option to Inspector.
- Enhancement Inspector render/update performance graphs stacked.
- Fixed Crash rendering text when changing foreground ([#1794](https://www.noesisengine.com/bugs/view.php?id=1794), [#1797](https://www.noesisengine.com/bugs/view.php?id=1797)).
- Fixed [ContextMenu](/Gui.Core/_ContextMenu.md) ignores keyboard keys ([#1792](https://www.noesisengine.com/bugs/view.php?id=1792)).
- Fixed Inspector performance graph not drawn until hovered with the mouse.
- Fixed Inspector render stats showing 0 or INF values when pausing just after connection.
- Fixed Calling Focus() on previously collapsed [TextBox](/Gui.Core/_TextBox.md) not showing caret and can't write ([#1795](https://www.noesisengine.com/bugs/view.php?id=1795)).
- Fixed Making selection changes on a collapsed [TextBox](/Gui.Core/_TextBox.md) not working.
- Fixed Shift key not extending mouse selection in [TextBox](/Gui.Core/_TextBox.md).
- Fixed [TextBox](/Gui.Core/_TextBox.md) Foreground ignored when template ScrollViewer has different Foreground ([#1791](https://www.noesisengine.com/bugs/view.php?id=1791)).
- Fixed Collection.Move doesn't keep the bound selected item ([#1796](https://www.noesisengine.com/bugs/view.php?id=1796)).
- Fixed C# [KeyTrigger](/App.Interactivity/_KeyTrigger.md) not working if *ModifierKeys* property wasn't set ([#1799](https://www.noesisengine.com/bugs/view.php?id=1799)).

# Version 3.0.5

*Released 18 Sep 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature Tapped, DoubleTapped, Holding and RightTapped [events](/Gui.Core/TouchTutorial.md#gesture-events) implements in [UIElement](/Gui.Core/_UIElement.md) ([#1533](https://www.noesisengine.com/bugs/view.php?id=1533)).
- Enhancement Showing context menu on *Holding* event for touch devices.
- Enhancement Added *UpdateInspector()* to integration API.
- Enhancement Added *ScrollIntoView()* for [ComboBox](/Gui.Core/_ComboBox.md) ([#1778](https://www.noesisengine.com/bugs/view.php?id=1778)).
- Enhancement Performance improvements in OpenGL shaders.
- Enhancement Improved memory allocations in Linear gradients.
- Enhancement Brushes correctly rendering inside text Runs ([#1221](https://www.noesisengine.com/bugs/view.php?id=1221)) ([preview](https://www.noesisengine.com/xamltoy/8bccdac28a26e01db7440daee192e2bd)).
- Enhancement GetTouchPoint() implemented in *TouchEventArgs* ([#962](https://www.noesisengine.com/bugs/view.php?id=962)).
- Enhancement C# Memory usage stats exposed ([#1764](https://www.noesisengine.com/bugs/view.php?id=1764)).
- Enhancement Inspector Support for multiple applications in the same machine.
- Enhancement Inspector Improved compatibility with Unity and Unreal editors.
- Enhancement Unreal Support for hot reloading of xamls and textures.
- Enhancement Unreal Performance improvements to RHI RenderDevice implementation.
- Enhancement Unity Continuous Rendering property is now only visible when rendering to texture.
- Enhancement Unity Added 'Subpixel Rendering' toggle to view component.
- Enhancement Unity Realtime stats panel refined.
- Fixed Crash when using *SharedSizeGroup* with collapsed grids ([#1768](https://www.noesisengine.com/bugs/view.php?id=1768)).
- Fixed Crash when adding/removing [Grid](/Gui.Core/_Grid.md) in a shared size group during measure ([#1776](https://www.noesisengine.com/bugs/view.php?id=1776)).
- Fixed [Storyboard](/Gui.Animation/_Storyboard.md) *FillBehavior* ignored by children timelines ([#1775](https://www.noesisengine.com/bugs/view.php?id=1775)).
- Fixed Unable to set [Storyboard](/Gui.Animation/_Storyboard.md) *Target* in code ([#1774](https://www.noesisengine.com/bugs/view.php?id=1774)).
- Fixed OneTime bindings not reevaluated when source changed ([#1714](https://www.noesisengine.com/bugs/view.php?id=1714)).
- Fixed Changing *ItemTemplate* property not updating item container template.
- Fixed Crash defining [ResourceDictionary](/Gui.Core/_ResourceDictionary.md) with x:Name inside Resources ([#1780](https://www.noesisengine.com/bugs/view.php?id=1780)).
- Fixed Metadata overrides for [DependencyObject](/Gui.DependencySystem/_DependencyObject.md) type ignored ([#1782](https://www.noesisengine.com/bugs/view.php?id=1782)).
- Fixed Rare shader compiler error in Android ([#1770](https://www.noesisengine.com/bugs/view.php?id=1770)).
- Fixed Crash inside event handler ([#1769](https://www.noesisengine.com/bugs/view.php?id=1769)).
- Fixed Crash rendering offscreen effects ([#1779](https://www.noesisengine.com/bugs/view.php?id=1779)).
- Fixed [Canvas](/Gui.Core/_Canvas.md) positions can't be *Infinity* ([#1756](https://www.noesisengine.com/bugs/view.php?id=1756)).
- Fixed Absolute radial gradients not rendering on some android devices due to precision problems.
- Fixed Crash when using Binding in [StoryboardCompletedTrigger](/App.Interactivity/_StoryboardCompletedTrigger.md) *Storyboard* property.
- Fixed Some duration formats are not supported by xaml parser ([#1785](https://www.noesisengine.com/bugs/view.php?id=1785)).
- Fixed Differing header files between Linux and Win distribution ([#1787](https://www.noesisengine.com/bugs/view.php?id=1787)).
- Fixed Collection *Move* not supported by [ItemCollection](/Gui.Core/_ItemCollection.md) and [VirtualizingStackPanel](/Gui.Core/_VirtualizingStackPanel.md).
- Fixed TSF When used in tablet, tapping any part of the window makes keyboard appear ([#1760](https://www.noesisengine.com/bugs/view.php?id=1760)).
- Fixed C# Signature mismatch of *RoutedEventArgs* constructor ([#1773](https://www.noesisengine.com/bugs/view.php?id=1773)).
- Fixed C# Queue empty exception on C# *Dispatcher* ([#1767](https://www.noesisengine.com/bugs/view.php?id=1767)).
- Fixed C# Numeric value displayed for enums instead of string value ([#1714](https://www.noesisengine.com/bugs/view.php?id=1714)).
- Fixed C# Crash on interactivity triggers defined inside templates.
- Fixed Unreal Rare crash compiling Blueprint.
- Fixed Unreal View debug visualizations crashing.
- Fixed Unity HDRP rendering UI in Scene View window ([#1766](https://www.noesisengine.com/bugs/view.php?id=1766)).
- Fixed Unity Crash destroying [Selector](/Gui.Core/_Selector.md) with data bound *ItemsSource*.

# Version 3.0.4

*Released 31 Jul 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Revamped UE4 integration

> - Many bug fixes and major improvements to workflow.
> - Added compatibility with UE4.25.
> - New [First Steps Tutorial](/Gui.Core/UnrealTutorial.md).

- Enhancement Sharing column or row sizes between [Grids](/Gui.Core/_Grid.md) with *ShareSizeGroup* ([#1552](https://www.noesisengine.com/bugs/view.php?id=1552)).
- Enhancement Gradients are now always interpolated in sRGB space (as in WPF).
- Enhancement Implemented [GradientBrush](/Gui.Core/_GradientBrush.md) [ColorInterpolationMode](https://www.noesisengine.com/xamltoy/372dc1a0750b543bdeee7648d87c5bed) property.
- Enhancement Added support for [CharacterSpacing](https://www.noesisengine.com/xamltoy/e9acf66b6812283bdfd54465a2ee6489) ([#1500](https://www.noesisengine.com/bugs/view.php?id=1500)).
- Enhancement Noesis Update no longer blocking, behaving again as in 2.2 ([#1688](https://www.noesisengine.com/bugs/view.php?id=1688)).
- Enhancement Unity Support for Multi-display ([#1593](https://www.noesisengine.com/bugs/view.php?id=1593)).
- Fixed *HorizontalOffset* and *VerticalOffset* to move [Tooltip](/Gui.Core/_ToolTip.md) does not work ([#1757](https://www.noesisengine.com/bugs/view.php?id=1757)).
- Fixed [Tooltip](/Gui.Core/_ToolTip.md) *PlacementTarget* not updated to owner.
- Fixed Can't set items *Row* or *Column* within an [ItemsControl](/Gui.Core/_ItemsControl.md) with [Grid](/Gui.Core/_Grid.md) items host ([#1758](https://www.noesisengine.com/bugs/view.php?id=1758)).
- Fixed Template resources defined in visual tree incorrectly shared ([#1759](https://www.noesisengine.com/bugs/view.php?id=1759)).
- Fixed Attributes with d: prefix not ignored if defined before mc:Ignorable attribute ([#1762](https://www.noesisengine.com/bugs/view.php?id=1762)).
- Fixed Added support for linear rendering to GL renderer ([#1678](https://www.noesisengine.com/bugs/view.php?id=1678)).
- Fixed Random crash in complex scenes ([#1750](https://www.noesisengine.com/bugs/view.php?id=1750)).
- Fixed Crash on drag completed if target was destroyed during drop operation.
- Fixed Unity Incorrect *OnPostprocessTexture* alpha premultiplication in linear rendering.

# Version 3.0.3

*Released 13 Jul 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Added missing .sln for all sample Blend projects.
- Enhancement C# App Defined default system font fallbacks.
- Fixed Static extension can't parse types with nested namespaces ([#1728](https://www.noesisengine.com/bugs/view.php?id=1728)).
- Fixed Cannot set a property inside of a converter using a resource ([#1729](https://www.noesisengine.com/bugs/view.php?id=1729)).
- Fixed [SkewTransform](/Gui.Core/_SkewTransform.md) does not look the same as in WPF ([#1731](https://www.noesisengine.com/bugs/view.php?id=1731)).
- Fixed Crash when clicking on a [TextBox](/Gui.Core/_TextBox.md) without a default font ([#1733](https://www.noesisengine.com/bugs/view.php?id=1733)).
- Fixed [TextBox](/Gui.Core/_TextBox.md) with IsFocusEngagementEnabled="False" does not work properly ([#1732](https://www.noesisengine.com/bugs/view.php?id=1732)).
- Fixed Crash after dragging [ListView](/Gui.Controls/_ListView.md) headers ([#1740](https://www.noesisengine.com/bugs/view.php?id=1740)).
- Fixed Crash reloading a xaml with duplicate *x:Name* elements ([#1741](https://www.noesisengine.com/bugs/view.php?id=1741)).
- Fixed Can't use [StaticResource](/Gui.Core/_StaticResourceExtension.md) for [MultiBinding](/Gui.Core/_MultiBinding.md) inner bindings ([#1735](https://www.noesisengine.com/bugs/view.php?id=1735)).
- Fixed Crash when playing visual state animations ([#1743](https://www.noesisengine.com/bugs/view.php?id=1743)).
- Fixed *VGLFontFace* crashes on unloading ([#1689](https://www.noesisengine.com/bugs/view.php?id=1689)).
- Fixed *DragDrop.DoDragDrop* incorrectly reporting effects ([#1746](https://www.noesisengine.com/bugs/view.php?id=1746)).
- Fixed [Tooltip](/Gui.Core/_ToolTip.md) *ShowDuration* doesn't work ([#1739](https://www.noesisengine.com/bugs/view.php?id=1739)).
- Fixed *VirtualizationMode=Recycling* breaks inheritance ([#1745](https://www.noesisengine.com/bugs/view.php?id=1745)).
- Fixed Bindings not working inside [ContentPresenter](/Gui.Core/_ContentPresenter.md) when using visual content ([#1747](https://www.noesisengine.com/bugs/view.php?id=1747)).
- Fixed Crash destroying [TextBlock](/Gui.Core/_TextBlock.md) with multiple brushes ([#1749](https://www.noesisengine.com/bugs/view.php?id=1749)).
- Fixed [TabControl](/Gui.Core/_TabControl.md) selection issue ([#1751](https://www.noesisengine.com/bugs/view.php?id=1751)).
- Fixed Interactivity [TargetedTriggerAction](/App.Interactivity/_TargetedTriggerAction.md) not executing sometimes ([#1755](https://www.noesisengine.com/bugs/view.php?id=1755)).
- Fixed Assert in GlyphCache::GetGlyph ([#1753](https://www.noesisengine.com/bugs/view.php?id=1753)).
- Fixed C# Implementations of *IScrollInfo* being ignored ([#1734](https://www.noesisengine.com/bugs/view.php?id=1734)).
- Fixed Unity Crash on reimporting xaml ([#1725](https://www.noesisengine.com/bugs/view.php?id=1725)).
- Fixed Unity Crash when stopping and playing scene ([#1737](https://www.noesisengine.com/bugs/view.php?id=1737)).

# Version 3.0.2

*Released 6 Jun 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- C++ Added support for *x86* and *ARM* in UWP ([#1721](https://www.noesisengine.com/bugs/view.php?id=1721)).
- Fixed C++ Window class size changing with NS\_PROFILE macro ([#1723](https://www.noesisengine.com/bugs/view.php?id=1723)).
- Fixed Controls occupying the entire surface disappearing when using effects ([#1654](https://www.noesisengine.com/bugs/view.php?id=1654), [#1655](https://www.noesisengine.com/bugs/view.php?id=1655), [#1687](https://www.noesisengine.com/bugs/view.php?id=1687)).
- Fixed [ComboBox](/Gui.Core/_ComboBox.md) selection not updating when model changes ([#1708](https://www.noesisengine.com/bugs/view.php?id=1708)).
- Fixed [Popup](/Gui.Core/_Popup.md) and [ComboBox](/Gui.Core/_ComboBox.md) do not work together nicely ([#1713](https://www.noesisengine.com/bugs/view.php?id=1713)).
- Fixed Crash when you click on [TextBox](/Gui.Core/_TextBox.md) with a not found FontFamily ([#1715](https://www.noesisengine.com/bugs/view.php?id=1715)).
- Fixed Incorrect binding error messages loading an [ItemsControl](/Gui.Core/_ItemsControl.md) ([#1718](https://www.noesisengine.com/bugs/view.php?id=1718)).
- Fixed Can't move focus to [ItemsControl](/Gui.Core/_ItemsControl.md) items using arrows ([#1719](https://www.noesisengine.com/bugs/view.php?id=1719)).
- Fixed Font dependency incorrectly including TTF file ([#1720](https://www.noesisengine.com/bugs/view.php?id=1720)).
- Fixed Unity Crash while playing in editor ([#1717](https://www.noesisengine.com/bugs/view.php?id=1717)).

# Version 3.0.1

*Released 28 May 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Removed includes to <windows.h> in public headers ([#1690](https://www.noesisengine.com/bugs/view.php?id=1690)).
- Enhancement Noesis not compiling properly with Clang as static libraries ([#1695](https://www.noesisengine.com/bugs/view.php?id=1695)).
- Enhancement Visual Studio *NatVis* not working when building static lib ([#1694](https://www.noesisengine.com/bugs/view.php?id=1694)).
- Fixed *Win32Display* not working on Windows 7 ([#1698](https://www.noesisengine.com/bugs/view.php?id=1698)).
- Fixed Crash when rendering first frame before initial *View* Update ([#1696](https://www.noesisengine.com/bugs/view.php?id=1696), [#1701](https://www.noesisengine.com/bugs/view.php?id=1701)).
- Fixed Crash in SDF generator ([#1700](https://www.noesisengine.com/bugs/view.php?id=1700)).
- Fixed Crash in *RenderOffscreen* ([#1692](https://www.noesisengine.com/bugs/view.php?id=1692)).
- Fixed Unity [Application](/App.ApplicationLauncher/_Application.md) resources can't use *StaticResource* between merged dictionaries ([#1699](https://www.noesisengine.com/bugs/view.php?id=1699)).
- Fixed Unity Crash doing "Reimport All" ([#1697](https://www.noesisengine.com/bugs/view.php?id=1697), [#1702](https://www.noesisengine.com/bugs/view.php?id=1702)).

# Version 3.0.0

*Released 21 May 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement App Implemented *OpenUrl* in *UIKitDisplay*.
- Fixed App *AppKitDisplay* never closing when *About* menu is visible.
- Fixed App Support for *SizeToContent* in *AppKitDisplay*.
- Fixed C# Potential leak in view *Timers*.
- Fixed Rare glitch when rendering [BlurEffect](/Gui.Core/_BlurEffect.md).
- Fixed Generated makefiles were incorrectly using 'mv' instead of 'move' in Windows.

# Version 3.0.0rc7

*Released 12 May 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Reviewed samples included in C++ SDK.
- Enhancement Added 3D transforms to Inventory sample.
- Enhancement Unity plugin is now a *.dylib* in macOS.

# Version 3.0.0rc6

*Released 11 May 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Exposed *DispatcherPriority* in *Dispatcher* ([#1679](https://www.noesisengine.com/bugs/view.php?id=1679)).
- Enhancement Added default font fallbacks for Asian scripts in Linux.
- Enhancement Binaries for macOS notarized.
- Enhancement Inspector improvements:

> - Adorners showing as filled paths matching Chrome browser inspection colors.
> - Fixed Changing selected node not updating adorners.
> - Fixed Padding adorner not updated when changing *Padding*.
> - Fixed HitTest was picking selection path adorner.

- Fixed Crash if [ItemsControl](/Gui.Core/_ItemsControl.md) gets destroyed before its [ItemCollection](/Gui.Core/_ItemCollection.md).
- Fixed Missing Info.plist on Noesis.bundle at macOS ([#1680](https://www.noesisengine.com/bugs/view.php?id=1680)).
- Fixed Issue when hot-reloading pattern paints ([#1681](https://www.noesisengine.com/bugs/view.php?id=1681)).

# Version 3.0.0rc5

*Released 7 May 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement New [NoesisGUI Extensions](/Gui.Core/ExtensionsTutorial.md) tutorial.
- Enhancement Inspector improvements:

> - Added 3d subtree content bounds debugging.
> - Avoid scaling adorners and update them only when needed.
> - Prevent the debug canvases from showing in the visual tree.

- Fixed Caret disappearing when [TextBox](/Gui.Core/_TextBox.md) gets scaled down.
- Fixed C# Interactivity classes causing memory leaks ([#1671](https://www.noesisengine.com/bugs/view.php?id=1671)).
- Fixed C# Unity samples using [WeakReference pattern](/Gui.Core/EventsTutorial.md#weak-events-in-c) to attach to events.
- Fixed Unity NoesisPostProcessor *NullReferenceException* after font deletion ([#1668](https://www.noesisengine.com/bugs/view.php?id=1668)).
- Fixed Unity WebGL build fails with errors ([#1676](https://www.noesisengine.com/bugs/view.php?id=1676)).

# Version 3.0.0rc4

*Released 4 May 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Added OculusVR sample to C++ SDK.
- Enhancement [3D Transforms tutorial](/Gui.Core/Transform3DTutorial.md).
- Fixed Render glitches when using 3D Transforms.
- Fixed Named elements not added to the tree on hot reloading.
- Fixed Crash invalidating geometries ([#1674](https://www.noesisengine.com/bugs/view.php?id=1674)).
- Fixed Selection lost when activating *Inspector* window.
- Fixed Debug glyph and ramp textures not showing when adorners were selected in *Inspector*.
- Fixed C# Not using Key/ModifierKeys native types and converters.

# Version 3.0.0rc3

*Released 30 Apr 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Fixed C# Linking issues in iOS projects.
- Fixed C# AppKitDisplay crash closing application.
- Fixed C# Crash after reloading scripts ([#1675](https://www.noesisengine.com/bugs/view.php?id=1675)).

# Version 3.0.0rc2

*Released 28 Apr 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Improvements to [Rendering Architecture](/Gui.Core/RenderingTutorial.md) document.
- Enhancement C# LogicalTreeHelper API is now as in WPF.
- Fixed C# App V-sync not enabled by default.
- Fixed C# Memory leaks when using [ResourceDictionary](/Gui.Core/_ResourceDictionary.md) in code.

# Version 3.0.0rc1

*Released 28 Apr 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- NoesisGUI requires now activation with a [License Key](/Gui.Core/Licensing.md).
- Enhancement App Implemented *OpenUrl()* in AndroidDisplay.
- Enhancement Support for multi-touch in [Slider](/Gui.Core/_Slider.md).
- Fixed Bindings not working on *EasingFunctions*.
- Fixed *BounceEase* crashing with *Bounces=1*.
- Fixed Crash when adding non-UIElement visual as a layer to View root.
- Fixed Invalid projection matrix when calling *View.SetSize(0, 0)*.
- Fixed Crash unregistering *Rendering* event on shutdown ([#1662](https://www.noesisengine.com/bugs/view.php?id=1662)).

# Version 3.0.0b9

*Released 24 Apr 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Unity Platform android-x86 no longer supported.
- Enhancement [PPAA](/Gui.Core/AntialiasingTutorial.md): exposed *PPAAIn* and *PPAAOut* as XAML extensions ([#1638](https://www.noesisengine.com/bugs/view.php?id=1638)).
- Enhancement Improved performance for stroked paths.
- Enhancement System fonts loading faster in iOS.
- Enhancement Improvements to *Inspector*:

> - Better organization for performance counters.
> - Detect resource renames for reloading (to support Visual Studio).
> - Added buttons for showing glyph and ramp atlases.
> - FontFamily showing source URI.
> - Avoid showing duplicated attached properties.
> - Correct selection of [TextBlock](/Gui.Core/_TextBlock.md) with [Inlines](/Gui.Core/_Inline.md).
> - Persist project path across sessions.
> - Previous value preserved when editing properties.

- Fixed MemoryAccessViolation on XAML reloading ([#1659](https://www.noesisengine.com/bugs/view.php?id=1659))

# Version 3.0.0b8

*Released 16 Apr 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Improvements to *Inspector*:

> - Views identified by an index and shown as 0: MainWindow.xaml
> - Added buttons to show *Glyph* and *Gradient* internal textures.
> - Reorganized render stats.
> - Remove adorners when *Inspector* disconnects.
> - Reset *Inspector* toolbar buttons when target is disconnected.

- Enhancement XamlPlayer exposing *Content.xaml* to *Inspector* to allow easy remote modifications.
- Enhancement C# Added *DisableInspector* function.
- Fixed [DropShadowEffect](/Gui.Core/_DropShadowEffect.md) ignoring alpha channel of *Color* property (as in WPF).
- Fixed Disabled LCD rendering during offscreen generation.
- Fixed Emoji rendering issue ([#1657](https://www.noesisengine.com/bugs/view.php?id=1657)).
- Fixed Unity Noesis\_View\_Update(...) Hard Locks Unity ([#1653](https://www.noesisengine.com/bugs/view.php?id=1653)).
- Fixed Unity Font preview crashing when launching Unity with empty scene.

# Version 3.0.0b7

*Released 13 Apr 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Added placeholder texts to *Login* sample.
- Enhancement Improved [Providers](/Gui.Core/ProvidersTutorial.md) tutorial with Hot-Reloading section.
- Enhancement Added support for new behaviors namespace

> - xmlns:b="http://schemas.microsoft.com/xaml/behaviors"

- Enhancement Inspector Avoid passing mouse events to the application while using mouse selection.
- Fixed [Grid](/Gui.Core/_Grid.md) layout failing with span elements sometimes.
- Fixed Incorrect frame interpolation with *Duration* greater than last frame time.
- Fixed Emojis opacity support ([#1651](https://www.noesisengine.com/bugs/view.php?id=1651)).
- Fixed *PlaySound* renamed to *PlayAudio* to avoid conflicts with Win32 API ([#1637](https://www.noesisengine.com/bugs/view.php?id=1637)).
- Fixed [Window](/App.ApplicationLauncher/_Window.md) using *SizeToContent* not centering content when display couldn't resize.

# Version 3.0.0b6

*Released 7 Apr 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Fixed Some interactivity classes not working when setting properties after being attached.
- Fixed Added missing Window events to C# ([#1474](https://www.noesisengine.com/bugs/view.php?id=1474)).
- Fixed C# Missing glyphs after reloading assemblies.

# Version 3.0.0b5

*Released 2 Apr 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature Added [Reloaded](/Gui.Core/EventsTutorial.md#lifetime-events) event for hot-reloading scenarios.
- Enhancement Performance and robustness improvements to XAML hot-reloading.
- Enhancement Avoid initial animations for [ToggleButton](/Gui.Core/_ToggleButton.md), [TreeView](/Gui.Core/_TreeView.md) and [Expander](/Gui.Core/_Expander.md) in Noesis Theme.
- Enhancement Improved performance of inherited properties.
- Fixed Crash finding system fonts in macOS.
- Fixed Data binding overwriting bound properties with default values ([#1645](https://www.noesisengine.com/bugs/view.php?id=1645)).
- Fixed C# [ResourceDictionary](/Gui.Core/_ResourceDictionary.md) Keys enumeration causing crash.
- Fixed C# Missing types when loading additional assemblies.
- Fixed C# Dispatcher operation not delivering exceptions to *UnhandledException* handler.

# Version 3.0.0b4

*Released 26 Mar 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Added a [debug theme](/Gui.Core/StylingTutorial.md#default-styles) (magenta) for default styles.
- Enhancement Improved atlas usage when using Emojis.
- Enhancement System fonts loading performance improvements.
- Enhancement Support for UI scale in Inspector (command-line --scale X).
- Enhancement App Added default font fallbacks for Emojis and Asian scripts.
- Fixed [TreeViewItem](/Gui.Core/_TreeViewItem.md) incorrectly using DataContext as item for the *SelectedItem* property.
- Fixed Effects incorrectly sampling border.
- Fixed C# Calling base.Measure|ArrangeOverride() was always returning zero.
- Fixed Implemented [Window](/App.ApplicationLauncher/_Window.md) *SizeToContent* property ([#1631](https://www.noesisengine.com/bugs/view.php?id=1631)).
- Fixed Emojis rendering not working with a few fonts, like Twemoji ([#1632](https://www.noesisengine.com/bugs/view.php?id=1632)).
- Fixed [TextBox](/Gui.Core/_TextBox.md) caret sometimes disappearing or placed over the characters.
- Fixed Caret remains visible after setting *IsReadOnly* to true in a [TextBox](/Gui.Core/_TextBox.md).
- Fixed [ToolBar](/Gui.Core/_ToolBar.md) overflow panel remains open when overflow items are removed.

# Version 3.0.0b3

*Released 19 Mar 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Improvements and fixes for *Inspector*.
- Fixed Implemented item Move() for [ItemContainerGenerator](/Gui.Core/_ItemContainerGenerator.md) and [Panel](/Gui.Core/_Panel.md) ([#1550](https://www.noesisengine.com/bugs/view.php?id=1550)).
- Fixed Assert when connecting element to a different view ([#1639](https://www.noesisengine.com/bugs/view.php?id=1639)).
- Fixed Error spam clearing collections with *DataContext* bindings ([#1572](https://www.noesisengine.com/bugs/view.php?id=1572)).
- Fixed Unity Different .asset files when importing on mac vs windows ([#1636](https://www.noesisengine.com/bugs/view.php?id=1636)).

# Version 3.0.0b2

*Released 16 Mar 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature Support for Unity 2019.3
- Feature Unity High Definition Render Pipeline (HDRP) supported.
- Feature Unity Support for Hot Reloading in Play Mode (disabled by default in global settings).
- Fixed Unity Standalone builds not working.
- Fixed [Application](/App.ApplicationLauncher/_Application.md) resource dictionaries should seal values.

# Version 3.0.0b1

*Released 11 Mar 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Website [XamlToy](https://xamltoy.noesisengine.com) is our new place to try NoesisGUI online using *WebGL*.
- Feature [Inspector](/Gui.Core/InspectorTutorial.md) is a new tool for profiling and analyzing applications using NoesisGUI. It remotely connects to the application and allows inspecting each element, profiling perfomance, hot-reloading of asssets, access to the console and much more things.

  ![Changelog_v30_0.jpg](/Changelog_v30_0/jpg.md)
- Feature New Noesis **Theme** supporting Dark/Light and Accent color variations. All controls have been adjusted to have a more modern aspect by default. There is also a new Gallery application showcasing the new control styles.

  ![Changelog_v30_1.png](/Changelog_v30_1/png.md)
- Feature New [plugin](https://github.com/Noesis/Lottie-Noesis) for **Adobe After Effects** ([preview](https://www.noesisengine.com/xamltoy/e4c6986363164dabcb6e0ea8d8d96265)) to export Lottie animations to XAML.

  ![Changelog_v30_2.png](/Changelog_v30_2/png.md)
- Feature Hot reloading of assets. Providers expose a delegate to inform about content changes.
- Feature [BlurEffect](/Gui.Core/_BlurEffect.md) ([preview](https://www.noesisengine.com/xamltoy/26ac351d3d40525f7e4ed14f6aa3e9f4)) and [DropShadowEffect](/Gui.Core/_DropShadowEffect.md) ([preview](https://www.noesisengine.com/xamltoy/012449ce12e6c2ad5cfa09020add4791)) implemented ([#1526](https://www.noesisengine.com/bugs/view.php?id=1526), [#878](https://www.noesisengine.com/bugs/view.php?id=878)).
- Feature Implemented [PathGeometry](/Gui.Core/_PathGeometry.md) ([preview](https://www.noesisengine.com/xamltoy/637ecb0c5f601da643bdaf9e855b46f8)) allowing rich shape animations.
- Feature Added *TrimStart*, *TrimEnd* and *TrimOffset* extensions to trim geometry [Path](/Gui.Core/_Path.md) like Adobe After Effect ([preview](https://www.noesisengine.com/xamltoy/6acdc882e5c540f15a7857a884e06a42)).
- Feature [3D Transforms](/Gui.Core/Transform3DTutorial.md). We have deprecated UIElement.Projection in favor of UIElement.Transform3D. This new property allows real 3D transformations ([preview](https://www.noesisengine.com/xamltoy/8ab948fb3b5a3edaaee5bb6cd7017a8b)). [CompositeTransform3D](/Gui.Core/_CompositeTransform3D.md) and [MatrixTransform3D](/Gui.Core/_MatrixTransform3D.md) can be asigned to this property. Camera projections only happen now at root by setting a matrix in the view using SetProjectionMatrix ([#1465](https://www.noesisengine.com/bugs/view.php?id=1465)).
- Feature Support for VR rendering. *Render* function in IView now receives an extra eye projection matrix.
- Feature [MultiBinding](/Gui.Core/_MultiBinding.md) implemented.
- Feature New text rendering algorithm using SDF (Signed Distance Fields) ([preview](https://www.noesisengine.com/xamltoy/ea9e784e9f6ce5787f2b8c8b8666da25)). Improved rendering quality, specially in 3D scenarios. Font hinting have been internally disabled. Performance of text rendering improved to be faster and consume less memory. Emojis no longer requiere a RGBA8 texture. Everything is rendered using A8.
- Feature Support for subpixel font rendering (LCD) is back. For now only implemented in our reference D3D11 renderer. There is a new view flag to activate it, RenderFlags\_LCD.
- Feature Added [CollectionSortBehavior](/App.Interactivity/_CollectionSortBehavior.md) and [CollectionFilterBehavior](/App.Interactivity/_CollectionFilterBehavior.md) to XAML Behaviors.
- Feature Implemented StringFormat for [ContentControl](/Gui.Core/_ContentControl.md) and [HeaderedContentControl](/Gui.Core/_HeaderedContentControl.md) ([#1263](https://www.noesisengine.com/bugs/view.php?id=1263)).
- Enhancement Path rendering have been optimized to consume less memory.
- Enhancement EASTL dependency removed. We have optimized all our architecture with custom containers. Memory performance vastly improved. Code bloating reduced by using less C++ features.
- Enhancement Visual Studio .natvis for Noesis added.
- Enhancement Performance of view Update and Rendering improved.
- Enhancement Improved the antialiasing look of our PPAA algorithm.
- Enhancement Placeholder text extension for [TextBox](/Gui.Core/_TextBox.md), [PasswordBox](/Gui.Core/_PasswordBox.md) and [ComboBox](/Gui.Core/_ComboBox.md) styles.
- Enhancement Removed final keyword from interactivity classes so they can be extended.
- Enhancement [DependencyObject](/Gui.DependencySystem/_DependencyObject.md) *SetValue* for strings optimized to avoid allocations.
- Enhancement New function [FrameworkElement](/Gui.Core/_FrameworkElement.md).ApplyTemplate().
- Enhancement New functions *SetFontFallbacks* and *SetFontDefaultProperties* added to IntegrationAPI.
- API Breaking Changes:

> - *NsRegisterComponent* renamed to Noesis::RegisterComponent
> - *TypeId* metadata deprecated from reflection macros. Now, it is passed in the macro itself.
>
>   ```
>   NS_IMPLEMENT_REFLECTION_(Buttons::MainWindow, "Buttons.MainWindow")
>   ```
> - Removed *'f'* suffix from math classes (e.g. *Vector3f* renamed to *Vector3*).
> - Containers like *NsVector* and *NsHashMap* renamed to *Vector* and *HashMap*.
> - *NsString* renamed to *String*.
> - Access to [ResourceDictionary](/Gui.Core/_ResourceDictionary.md) values using const char\* keys instead of obsolete *IResourceKey*.
> - Removed *NeedsOffscreen* from IRenderer. Now *RenderOffscreen* returns a boolean.
> - Removed *SetIsPPAAEnabled* and *GetIsPPAAEnabled* from IView. PPAA is now part of *RenderFlags* enumeration.
> - Noesis::GUI::Init() no longer receiving parameters, only the license-key.
>
>   ```
>   Noesis::GUI::SetLogHandler(Loghandler);
>   Noesis::GUI::SetErrorHandler(ErrorHandler);
>   Noesis::GUI::SetMemoryCallbacks(MemoryCallbacks);
>   Noesis::GUI::Init(NS_LICENSE_NAME, NS_LICENSE_KEY);
>   ```
> - Core library no longer provides a default theme or default font. It must be set at initialization time using *SetApplicationResources*. Our application framework provides a default theme that is being used by all our examples.
> - Custom *RenderDevice* implementations need to be upgraded with new shader for rendering distance fields.
> - View::Update() may block if enqueing many frames without doing Renderer::UpdateRenderTree() in the render thread.
> - *SizeChangedEventArgs* exposes now newSize and oldSize.

- Fixed Hit-testing working correctly in all 3D scenarios.
- Fixed Templates shouldn't be set without a valid VisualTree.
- Fixed Unnecessary tessellations when changing items in [ToolBar](/Gui.Core/_ToolBar.md).
- Fixed [Binding](/Gui.Core/_Binding.md) with *FindAncestor* should search up the visual tree.
- Fixed Stack overflow bringing [TreeViewItem](/Gui.Core/_TreeViewItem.md) into view without *PART\_Header* template element.
- Fixed Duplicated reflection enum values for *Key* and *ModifierKeys*.
- Fixed Crash when using unknown *TargetName* in a trigger [Setter](/Gui.Core/_Setter.md).
- Fixed [FrameworkElement](/Gui.Core/_FrameworkElement.md) *FindResource* not searching in *BasedOn* styles.
- Fixed Focus visual layer not removed when focused element disabled or collapsed.
- Fixed [ScrollContentPresenter](/Gui.Core/_ScrollContentPresenter.md) registered against *ScrollChanged* event multiple times.
- Fixed [Path](/Gui.Core/_Path.md)'s geometry *FillRule* being ignored.
- Fixed [MultiDataTrigger](/Gui.Core/_MultiDataTrigger.md) incorrectly executed when all conditions except the last one matched during initialization.
- Fixed [Button](/Gui.Core/_Button.md) *IsPressed* being updated using *DescendantBounds* instead of *RenderSize* as in WPF.
- Fixed [ItemsControl](/Gui.Core/_ItemsControl.md) *ContainerFromElement* crashing for elements not inside the items control.
- Fixed Opacity group clipped when bigger than surface size.
- Fixed [ListView](/Gui.Controls/_ListView.md) not updating item text inherited properties.
- Fixed Crash setting a null LayoutTransform.
- Fixed Crash reloading managed assembly when destroying proxies ([#1577](https://www.noesisengine.com/bugs/view.php?id=1577)).
- Fixed *IsFocusEngagementEnabled* now indicates if [Control](/Gui.Core/_Control.md) supports focus engagement to match UWP.
- Fixed [ItemsControl](/Gui.Core/_ItemsControl.md) and derived no longer have *IsFocusEngagementEnabled* by default to match UWP.

# Previous Versions

## [Version 2.2](/Gui.Core/Changelog_v22.md)

## [Version 2.1](/Gui.Core/Changelog_v21.md)

## [Version 2.0](/Gui.Core/Changelog_v20.md)

## [Version 1.2](/Gui.Core/Changelog_v12.md)

## [Version 1.1](/Gui.Core/Changelog_v11.md)