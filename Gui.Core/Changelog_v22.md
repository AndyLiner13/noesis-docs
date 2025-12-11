Source: https://www.noesisengine.com/docs/Gui.Core.Changelog_v22.html

# Changelog

# Version 2.2.6

*Released 7 Jan 2020* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature Support for XCode 11
- Feature Exposed *CheckAccess* and *VerifyAccess* in [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md) ([#1470](https://www.noesisengine.com/bugs/view.php?id=1470)).
- Feature Added *Placeholder* text extension for [TextBlock](_TextBlock.md) and [PasswordBox](_PasswordBox.md) templates.
- Feature C# Implemented [Dispatcher](https://docs.microsoft.com/en-us/dotnet/api/system.windows.threading.dispatcher?view=netframework-4.8) and [ThreadSwitcher](https://devblogs.microsoft.com/oldnewthing/20190328-00/?p=102368) ([#1548](https://www.noesisengine.com/bugs/view.php?id=1548)).
- Feature Unity New Visual Studio [Project Template](Unity3DTutorial.md#blend).
- Enhancement No more binding errors when clearing or changing *ObservableCollection* ([#1572](https://www.noesisengine.com/bugs/view.php?id=1572)).
- Enhancement Unity Moved *Interactivity* folder out of *Samples*.
- Enhancement C# Touch events implemented.
- Fixed Crash using [InlineUIContainer](_InlineUIContainer.md) inside style ([#1594](https://www.noesisengine.com/bugs/view.php?id=1594)).
- Fixed Crash specifying unknown *TargetName* in Trigger Setter ([#1603](https://www.noesisengine.com/bugs/view.php?id=1603)).
- Fixed Crash destroying interactivity [EventTrigger](../App.Interactivity/_EventTrigger.md) with *SourceName*.
- Fixed Crash changing *IsDropDownOpen* while destroying [ComboBox](_ComboBox.md).
- Fixed [ComboBox](_ComboBox.md) closing dropdown when changing item collection.
- Fixed [ComboBox](_ComboBox.md) moving focus to dropdown or edit box when not focused.
- Fixed Layout freezing when changing over-element visibility ([#1599](https://www.noesisengine.com/bugs/view.php?id=1599), [#1600](https://www.noesisengine.com/bugs/view.php?id=1600)).
- Fixed NaN not handled correctly in bindings ([#1555](https://www.noesisengine.com/bugs/view.php?id=1555)).
- Fixed Changes to *Row* and *Column* in [Grid](_Grid.md) while measuring being ignored ([#1582](https://www.noesisengine.com/bugs/view.php?id=1582)).
- Fixed [GridViewColumnHeader](../Gui.Controls/_GridViewColumnHeader.md) *Click* event not being raised ([#937](https://www.noesisengine.com/bugs/view.php?id=937), [#1499](https://www.noesisengine.com/bugs/view.php?id=1499)).
- Fixed *GridViewColumn* bindings not working inside a template ([#1559](https://www.noesisengine.com/bugs/view.php?id=1559)).
- Fixed [Style](_Style.md) resource not applied to GridViewColumn's *DisplayMemberBinding* ([#1570](https://www.noesisengine.com/bugs/view.php?id=1570)).
- Fixed Directional navigation not working when intermediary UI element getting collapsed ([#1604](https://www.noesisengine.com/bugs/view.php?id=1604)).
- Fixed [Separator](_Separator.md) control not rendering ([#1602](https://www.noesisengine.com/bugs/view.php?id=1602)).
- Fixed Command converter not supporting prefixes in xaml ([#1561](https://www.noesisengine.com/bugs/view.php?id=1561)).
- Fixed Opacity groups disappearing when overlapping bottom screen edge ([#1565](https://www.noesisengine.com/bugs/view.php?id=1565) [#1574](https://www.noesisengine.com/bugs/view.php?id=1574)).
- Fixed [StoryboardCompletedTrigger](../App.Interactivity/_StoryboardCompletedTrigger.md) not working when used inside template ([#1576](https://www.noesisengine.com/bugs/view.php?id=1576)).
- Fixed [ControlStoryboardAction](../App.Interactivity/_ControlStoryboardAction.md) cannot use [Storyboard](../Gui.Animation/_Storyboard.md) defined in application resources ([#1575](https://www.noesisengine.com/bugs/view.php?id=1575)).
- Fixed Unity Exception creating multiple [TextureSource](_TextureSource.md) ([#1607](https://www.noesisengine.com/bugs/view.php?id=1607)).
- Fixed Unity Eliminated GC allocs when gamepad not mapped ([#1587](https://www.noesisengine.com/bugs/view.php?id=1587))
- Fixed Unity Scrolling on touchpad not working ([#1347](https://www.noesisengine.com/bugs/view.php?id=1347)).
- Fixed C# Bad performance when lots of extends being kept alive.
- Fixed C# UICollection compatible with Xamarin.Mac 6.2.0.42.
- Fixed C# *SupportsFocusEngagement* not recognized in [Noesis.GUI.Extensions](https://www.nuget.org/packages/Noesis.GUI.Extensions/) ([#1560](https://www.noesisengine.com/bugs/view.php?id=1560)).
- Fixed C# *PasswordLength* extension property not working correctly in Blend.

# Version 2.2.5

*Released 27 Sept 2019* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature C# Support for linux-arm and linux-arm64.
- Enhancement C# Projects for linux samples using NETCore.
- Fixed C# Linux samples using EGL render context for ARM architectures.
- Fixed C# Native interop problems for XDisplay in 32 bit systems.
- Fixed C# Incorrect *Enumerator* implementation producing GC allocs.
- Fixed C# Searching for extend proxies producing GC allocs.
- Fixed C# Bad performance dealing with lots of extend proxies.
- Fixed C# DictionaryIndexer proxies not working.
- Fixed C# Crash using some classes without initializing Noesis ([#1538](https://www.noesisengine.com/bugs/view.php?id=1538)).
- Fixed Crash unregistering binding to destroyed [GridViewRowPresenter](../Gui.Controls/_GridViewRowPresenter.md).
- Fixed UI freeze when hiding and showing Popups.
- Fixed Crash destroying UI tree with a [ControlStoryboardAction](../App.Interactivity/_ControlStoryboardAction.md).
- Fixed Controllable storyboards removing animated values when restarted.
- Fixed Crash using interactivity [EventTrigger](../App.Interactivity/_EventTrigger.md) in a Storyboard resource.

# Version 2.2.4

*Released 23 Aug 2019* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature Support for Unity 2019.2.
- Feature Support for XCode 10.3 (iOS Deployment Target is now to 8.0+).
- Feature Support for GCC 8.
- Feature Raspberry Pi 4 officially supported.
- Feature Implemented [GamepadTrigger](../App.Interactivity/_GamepadTrigger.md) to specify gamepad input in Blend.
- Enhancement Unity Added note to [Blend tutorial](BlendTutorial.unity.md#blend-project) conflicts with Visual Studio project name.
- Enhancement Added *Thickness* constructor with 2 arguments ([#1492](https://www.noesisengine.com/bugs/view.php?id=1492)).
- Enhancement Implemented Copy/Paste event handling.
- Enhancement Zoom from mouse wheel added to [TranslateZoomRotateBehavior](../App.Interactivity/_TranslateZoomRotateBehavior.md) ([#1486](https://www.noesisengine.com/bugs/view.php?id=1486)).
- Enhancement Improved [documentation](MarkupExtensions.md#staticextension) about x:Static extension ([#1353](https://www.noesisengine.com/bugs/view.php?id=1353)).
- Enhancement Added support in x:Static extension for *RoutedEvents* defined in classes.
- Enhancement [ContentPresenter](_ContentPresenter.md) checking if content already connected to another visual parent.
- Enhancement Better error message when using a non-null default value in collections.
- Enhancement Added support for overriding how C# [Application](../App.ApplicationLauncher/_Application.md) logs messages.
- Enhancement TouchUp promotion to *Mouse* now includes an extra *MouseMove* (as in WPF).
- Fixed Out of range assert in *VGLTextLayout* HitTestPoint.
- Fixed Assert when closing a [MenuItem](_MenuItem.md).
- Fixed [ContentControl](_ContentControl.md) content object not released after Content property nulled ([#1495](https://www.noesisengine.com/bugs/view.php?id=1495)).
- Fixed Weird selectable rectangle rendered in [ListView](../Gui.Controls/_ListView.md) headers ([#1502](https://www.noesisengine.com/bugs/view.php?id=1502)).
- Fixed [ToolTip](_ToolTip.md) not disappearing when the mouse leaving hosting window ([#1511](https://www.noesisengine.com/bugs/view.php?id=1511)).
- Fixed [MouseDragElementBehavior](../App.Interactivity/_MouseDragElementBehavior.md) not working in parents with [TranslateZoomRotateBehavior](../App.Interactivity/_TranslateZoomRotateBehavior.md) ([#1487](https://www.noesisengine.com/bugs/view.php?id=1487)).
- Fixed Crash on *DynamicResource* with a null key ([#1515](https://www.noesisengine.com/bugs/view.php?id=1515)).
- Fixed Binding nested dictionaries not working ([#1501](https://www.noesisengine.com/bugs/view.php?id=1501)).
- Fixed ColumnDefinition *MinWidth* and *MaxHeight* incorrectly accepting NaN values ([#1516](https://www.noesisengine.com/bugs/view.php?id=1516)).
- Fixed TSF candidate window shown even if focus is not in a [TextBox](_TextBox.md) ([#1514](https://www.noesisengine.com/bugs/view.php?id=1514)).
- Fixed Removed unnecessary TSF document disable code when *HideKeyboard*.
- Fixed Unloaded event raised after element is disconnected from the *View* as it occurs in WPF.
- Fixed Crash destroying [Visual](_Visual.md) with [UIElementCollection](_UIElementCollection.md) dependency property with children.
- Fixed Crash destroying [UIElementCollection](_UIElementCollection.md) or [VisualCollection](_VisualCollection.md) parent before collection.
- Fixed Resource lookup not searching in all *BasedOn* style chain.
- Fixed Infinite layout loop when using same [Visual](_Visual.md) as Content in 2 [ContentPresenters](_ContentPresenter.md) ([#1529](https://www.noesisengine.com/bugs/view.php?id=1529)).
- Fixed Partially resolved [Binding](_Binding.md) path incorrectly notifying of read-only error.
- Fixed Access violation exception when clicking in a [ListBox](_ListBox.md) item ([#1528](https://www.noesisengine.com/bugs/view.php?id=1528)).
- Fixed [Storyboards](../Gui.Animation/_Storyboard.md) fired with *Begin()* version should be controllable.
- Fixed [ControlStoryboardAction](../App.Interactivity/_ControlStoryboardAction.md) inside template incorrectly referencing cloned storyboard.
- Fixed [ControlStoryboardAction](../App.Interactivity/_ControlStoryboardAction.md) not working properly when used inside templates.
- Fixed [ConditionBehavior](../App.Interactivity/_ConditionBehavior.md) inside template ignored for [PropertyChangedTrigger](../App.Interactivity/_PropertyChangedTrigger.md) and [DataTrigger](../App.Interactivity/_DataTrigger.md).
- Fixed [DataTrigger](_DataTrigger.md) not working when trigger value is null.
- Fixed Crash when *FocusVisualStyle* control was incorrectly focused.
- Fixed Crash clearing *InlineCollection* that contains InlineUIContainer ([#1542](https://www.noesisengine.com/bugs/view.php?id=1542)).
- Fixed StackPanel ScrollData not going through custom allocator ([#1541](https://www.noesisengine.com/bugs/view.php?id=1541)).
- Fixed Crash when mouse capture changed while raising *MouseLeave* events ([#1518](https://www.noesisengine.com/bugs/view.php?id=1518)).
- Fixed Missing namespace in macro NS\_IMPLEMENT\_INLINE\_REFLECTION\_ENUM ([#1422](https://www.noesisengine.com/bugs/view.php?id=1422)).
- Fixed Cannot stop manipulation inertia in [ScrollViewer](_ScrollViewer.md) ([#866](https://www.noesisengine.com/bugs/view.php?id=866), [#1405](https://www.noesisengine.com/bugs/view.php?id=1405), [#1072](https://www.noesisengine.com/bugs/view.php?id=1072)).
- Fixed Can't get *Touch* captured element ([#1489](https://www.noesisengine.com/bugs/view.php?id=1489)).
- Fixed LostTouchCapture not raised after manipulations are completed ([#1488](https://www.noesisengine.com/bugs/view.php?id=1488)).
- Fixed Wrong *GetTouchPosition* result in *GotTouchCapture* callback ([#885](https://www.noesisengine.com/bugs/view.php?id=885)).
- Fixed C# Exposed *TouchDevice* and *Captured element* ([#1489](https://www.noesisengine.com/bugs/view.php?id=1489)).
- Fixed Unity Packages folder incorrectly being preprocessed ([#1508](https://www.noesisengine.com/bugs/view.php?id=1508)).
- Fixed Unity XAML freezes Unity on Begin MonoManager *ReloadAssembly* ([#1388](https://www.noesisengine.com/bugs/view.php?id=1388)).
- Fixed Unity Event handlers not be called during *ReloadAssembly* ([#1491](https://www.noesisengine.com/bugs/view.php?id=1491)).
- Fixed Unity Button *Click* event not raised when pressing gamepad *Accept* ([#1524](https://www.noesisengine.com/bugs/view.php?id=1524)).
- Fixed Unity Using the delegate version of VisualTree.HitTest crashes Unity ([#1527](https://www.noesisengine.com/bugs/view.php?id=1527)).
- Fixed Unity System fonts not working in iOS 9 and lower ([#1520](https://www.noesisengine.com/bugs/view.php?id=1520)).

# Version 2.2.3

*Released 10 Jun 2019* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement C# Exposed *MainWindow* in [Application](../App.ApplicationLauncher/_Application.md).
- Enhancement C# Exposed *Rendering* event in [Window](../App.ApplicationLauncher/_Window.md).
- Enhancement C# Added support for fullscreen to *XDisplay*.
- Enhancement C# Embedded providers constructed now with *Assembly* and *Namespace*.
- Enhancement C# Fallback embedded providers no longer overridable.
- Enhancement C# Removed dependency to OpenGL.Net NuGet.
- Enhancement Added IView.Scroll(x, y, value) overloaded method.
- Enhancement Binding logs removed in release builds.
- Enhancement Improved [Drag & Drop behaviors](https://github.com/Noesis/Tutorials/blob/master/Samples/Inventory/C%2B%2B/Src/DragItemBehavior.h) in Inventory sample.
- Fixed Can't write more than one character in an editable [ComboBox](_ComboBox.md) ([#1477](https://www.noesisengine.com/bugs/view.php?id=1477)).
- Fixed Double clicking on [TreeViewItem](_TreeViewItem.md) collapses root node ([#1466](https://www.noesisengine.com/bugs/view.php?id=1466)).
- Fixed [TextBlock](_TextBlock.md) *LineStackingStrategy* property value not inherited ([#1460](https://www.noesisengine.com/bugs/view.php?id=1460)).
- Fixed Crash closing [ToolTip](_ToolTip.md) with bindings.
- Fixed [Selector](_Selector.md) resetting *SelectedIndex* and *SelectedItem* bound properties on *DataContext* changes.
- Fixed [BindingOperations](_BindingOperations.md) *GetBindingExpression* working only for local values.
- Fixed Expressions recreated when invalidating dependency properties.
- Fixed Using *StaticResource* in [ChangePropertyAction](../App.Interactivity/_ChangePropertyAction.md) value not working.
- Fixed Crash closing the [Window](../App.ApplicationLauncher/_Window.md) ([#1424](https://www.noesisengine.com/bugs/view.php?id=1424)).
- Fixed C# Text input not working in *AppKitDisplay*, *UIKitDisplay* and *XDisplay*.
- Fixed C# Incorrectly using dynamic code in iOS.
- Fixed C# [GoToStateAction](../App.Interactivity/_GoToStateAction.md) not working ([#1464](https://www.noesisengine.com/bugs/view.php?id=1464)).
- Fixed Unity NoesisView icon not showing in inspector.
- Fixed Unity Fatal error in Xaml parser trying to create an [UIElementCollection](_UIElementCollection.md) ([#1461](https://www.noesisengine.com/bugs/view.php?id=1461)).
- Fixed Unity Noesis DLL crash on Alt-Tab ([#1459](https://www.noesisengine.com/bugs/view.php?id=1459)).
- Fixed Unity Upside down images on *OpacityMask* when *FlipY* was enabled ([#1462](https://www.noesisengine.com/bugs/view.php?id=1462)).

# Version 2.2.2

*Released 26 Apr 2019* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature Support for Unity 2019.1.
- Feature Support for Unreal Engine 4.22.
- Enhancement Unity Native allocated memory exposed in Noesis settings panel.
- Enhancement C# Removed unnecessary *TypeHandle* comparisons in proxies.
- Enhancement Improvements to performance and stability of *Metal* renderer.
- Fixed Unity Gamepad input using *GetAxisRaw* instead of *GetAxis*.
- Fixed Unity Noesis renders to wrong camera in multi-camera case ([#1427](https://www.noesisengine.com/bugs/view.php?id=1427)).
- Fixed *PointToScreen* not throwing error when element not connected to visual tree ([#1378](https://www.noesisengine.com/bugs/view.php?id=1378)).
- Fixed [ToolTipService](_ToolTipService.md) *SetToolTip* with null element crashing ([#1423](https://www.noesisengine.com/bugs/view.php?id=1423)).
- Fixed Resources DataContext not behaving as in WPF ([#1004](https://www.noesisengine.com/bugs/view.php?id=1004)).
- Fixed [ToolBarOverflowPanel](_ToolBarOverflowPanel.md) incorrectly doing layout sometimes.
- Fixed Routed commands cannot be defined in XAML ([#1122](https://www.noesisengine.com/bugs/view.php?id=1122)).
- Fixed Unity Editor crashing on [TextBox](_TextBox.md) *Focus()* ([#1447](https://www.noesisengine.com/bugs/view.php?id=1447)).
- Fixed C# DataBinding to *Uri* properties not working ([#1449](https://www.noesisengine.com/bugs/view.php?id=1449)).
- Fixed C# [BitmapImage](_BitmapImage.md) support for spaces in path broken in 2.2.1 ([#1455](https://www.noesisengine.com/bugs/view.php?id=1455)).
- Fixed C# [BitmapImage](_BitmapImage.md) strips leading "/" in paths on Linux ([#1456](https://www.noesisengine.com/bugs/view.php?id=1456)).
- Fixed LoadXAML crashing with *DataTemplate* as root element ([#1439](https://www.noesisengine.com/bugs/view.php?id=1439)).
- Fixed [ContextMenu](_ContextMenu.md) and [ToolTip](_ToolTip.md) stays unclosed when window deactivated ([#1438](https://www.noesisengine.com/bugs/view.php?id=1438)).
- Fixed [ToolTip](_ToolTip.md) *InitialShowDelay* incorrectly reset when mouse moved over element.
- Fixed Several bugs related to opacity and projection ([#1120](https://www.noesisengine.com/bugs/view.php?id=1120), [#1321](https://www.noesisengine.com/bugs/view.php?id=1321), [#1373](https://www.noesisengine.com/bugs/view.php?id=1373), [#1374](https://www.noesisengine.com/bugs/view.php?id=1374)).
- Fixed [ListView](../Gui.Controls/_ListView.md) without *ListView.View* section not displaying items ([#493](https://www.noesisengine.com/bugs/view.php?id=493)).
- Fixed Changes to [GridViewColumnHeader](../Gui.Controls/_GridViewColumnHeader.md) header not updated ([#1420](https://www.noesisengine.com/bugs/view.php?id=1420)).
- Fixed [GridView](../Gui.Controls/_GridView.md) header properties ignored ([#1420](https://www.noesisengine.com/bugs/view.php?id=1420)).
- Fixed [PasswordBox](_PasswordBox.md) not showing caret when placed inside a [ScrollViewer](_ScrollViewer.md).

# Version 2.2.1

- Feature Unity Implemented support for [Scriptable Render Pipeline](https://docs.unity3d.com/Manual/ScriptableRenderPipeline.html) ([#1372](https://www.noesisengine.com/bugs/view.php?id=1372) [#1386](https://www.noesisengine.com/bugs/view.php?id=1386)).
- Enhancement Unity Package [installing](Unity3DTutorial.md#examples) Blend solution for included samples.
- Enhancement Unity '*Enable Gamepad*' property added to View component. Disabled by default.
- Enhancement Unity Added support for gamepad *Scroll* and *HScroll* input events.
- Enhancement Unity Samples [configured](https://github.com/Noesis/Tutorials/blob/master/Samples/QuestLog/Unity/ProjectSettings/InputManager.asset) to support Xbox controller.
- Enhancement C# Added support for [pack uris](https://github.com/Noesis/Tutorials/blob/master/Samples/QuestLog/Unity/Assets/NoesisGUI/Samples/QuestLog/ViewModel.cs#L45-L47) in code-behind. Required for viewing images at edit-time in Blend.
- Enhancement *Scroll* and *HScroll* View functions are now frame-rate independent.
- Enhancement App Implemented auto repeat for gamepad buttons.
- Enhancement App Right stick mapped to *View* scroll functions.
- Fixed C# *UICollection* enumerator incorrectly throwing on *Dispose*.
- Fixed C# Incorrect *MouseButtonState* enum values ([#1434](https://www.noesisengine.com/bugs/view.php?id=1434)).
- Fixed Unity Editor freezing in rare cases when entering play mode ([#1442](https://www.noesisengine.com/bugs/view.php?id=1442)).
- Fixed Crash closing scene with popups opened ([#1428](https://www.noesisengine.com/bugs/view.php?id=1428), [#1429](https://www.noesisengine.com/bugs/view.php?id=1429)).
- Fixed [Preview]MouseDoubleClick event not notifying registered handlers.
- Fixed Incorrect collapsed state in [Expander](_Expander.md) template for NocturnalStyle theme ([#1432](https://www.noesisengine.com/bugs/view.php?id=1432)).
- Fixed [TextBox](_TextBox.md) and [PasswordBox](_PasswordBox.md) not showing caret after *Deactivate* ([#1431](https://www.noesisengine.com/bugs/view.php?id=1431)).
- Fixed *Visual* descendant bounds not correctly calculated.
- Fixed *ImageBrush* displaced when using geometry bounds with offset.
- Fixed Better performance in tiled architectures when using multicamera layered rendering ([#1427](https://www.noesisengine.com/bugs/view.php?id=1427)).
- Fixed Input events consumed by camera depth order ([#1433](https://www.noesisengine.com/bugs/view.php?id=1433)).

# Version 2.2.0

- Enhancement New document: [NoesisGUI in comparison with WPF/UWP](WPFComparison.md).
- Enhancement Fixed imprecisions in [KeyboardNavigation](_KeyboardNavigation.md).
- Enhancement Support for system fonts inside '/Library/Fonts' for macOS.
- Fixed Crash destroying [KeyTrigger](../App.Interactivity/_KeyTrigger.md).
- Fixed AlternationIndex not correctly updated when items added or removed.

# Version 2.2.0rc1

- Enhancement Support for connecting XInput controllers in any port.
- Enhancement [ScrollViewer](_ScrollViewer.md) inside [TextBox](_TextBox.md), [PasswordBox](_PasswordBox.md) and [ComboBox](_ComboBox.md) no longer *Focusable* in our default theme.
- Fixed Key modifiers not accurate when clicking on inactivate window ([#1418](https://www.noesisengine.com/bugs/view.php?id=1418)).
- Fixed [ScrollViewer](_ScrollViewer.md) not overriding *IsTabStop* to false as in WPF.
- Fixed C# EmbeddedFontProvider failing in Android for fonts placed inside folders.
- Fixed Clicking on [TextBox](_TextBox.md) not opening virtual keyboard when received focus from gamepad.
- Fixed Weird focusing on [TabControl](_TabControl.md) ([#1121](https://www.noesisengine.com/bugs/view.php?id=1121)).
- Fixed Improved [TabControl](_TabControl.md) gamepad navigation.
- Fixed [ScrollViewer](_ScrollViewer.md) not getting focus when clicked.

# Version 2.2.0b10

- Enhancement C++ GetName and GetOwnerType removed from ICommand.
- Enhancement C# Improvements to Drag and Drop API.
- Enhancement Improvements to [DataBinding](DataBindingTutorial.md), [CustomControl](CustomControlTutorial.md) and [Commands](CommandsTutorial.md) tutorials.

# Version 2.2.0b9

- Enhancement C++ SDK Blend projects are now included in samples solution.
- Enhancement Added new Noesis.GUI.Extensions NuGet package to use in WPF/Blend projects.

# Version 2.2.0b8

- Enhancement Improved implementation of dynamic buffers in Metal renderer.
- Enhancement Metal.framework is now loaded dynamically ([#1083](https://www.noesisengine.com/bugs/view.php?id=1083)).
- Enhancement Glyph cache no longer regenerated when changing PPAA settings.
- Enhancement Improvements to [First contact with Blend](BlendTutorial.unity.md) Unity tutorial.
- Fixed Win7 incompatibility in Win32Display when using XInput ([#1414](https://www.noesisengine.com/bugs/view.php?id=1414)).
- Fixed Unity Compatibility with Unity LTS (2017.4)

# Version 2.2.0b7

- Nintendo Switch C++ New platform supported.
- Enhancement App C# [Application](../App.ApplicationLauncher/_Application.md) and [Window](../App.ApplicationLauncher/_Window.md) moved inside NoesisApp namespace ([#1326](https://www.noesisengine.com/bugs/view.php?id=1326)).
- Enhancement C# *ContentPropertyAttribute* moved inside Noesis namespace ([#1327](https://www.noesisengine.com/bugs/view.php?id=1327)).
- Enhancement Incorrect assert when returning Size.Empty from C# in Measure/Arrange ([#1413](https://www.noesisengine.com/bugs/view.php?id=1413)).
- Enhancement Order of *DoubleClick* events matching WPF.
- Fixed Crash with empty run at the end of normal runs ([#1407](https://www.noesisengine.com/bugs/view.php?id=1407)).
- Fixed [VirtualizingStackPanel](_VirtualizingStackPanel.md) crash when using [Style](_Style.md) to set scroll properties.

# Version 2.2.0b6

- WebGL Unity New platform supported.
- Enhancement Unity New XAML importer, faster and more robust ([#1369](https://www.noesisengine.com/bugs/view.php?id=1369) [#1366](https://www.noesisengine.com/bugs/view.php?id=1366) [#1394](https://www.noesisengine.com/bugs/view.php?id=1394) [#1393](https://www.noesisengine.com/bugs/view.php?id=1393)).
- Enhancement Unity XAML and Fonts assets stored as text.
- Enhancement Unity Added [Interactivity](../App.Interactivity/Behaviors.md) package. PlaySoundAction using Unity clips.
- Enhancement Unity Dependencies to [UserControls](_UserControl.md) automatically generated.
- Enhancement Unity Implemented previews and thumbnails for fonts.
- Enhancement Unity IME implemented in Unity ([#1243](https://www.noesisengine.com/bugs/view.php?id=1243) [#1264](https://www.noesisengine.com/bugs/view.php?id=1264) [#1213](https://www.noesisengine.com/bugs/view.php?id=1213)).
- Enhancement Unity Textures marked with label 'Noesis' converted to premultiplied-alpha.
- Enhancement Unity Added a panel for realtime stats in play mode.
- Enhancement Unity Support for system fonts. Improved memory usage of fonts.
- Enhancement Unity Cursors added to settings panel.
- Enhancement Unity Support for rendering UI only when changed ([#589](https://www.noesisengine.com/bugs/view.php?id=589) [#740](https://www.noesisengine.com/bugs/view.php?id=740)).
- Enhancement Unity New property to select RenderTexture target.
- Enhancement Correctly implemented *HitTest* with filter and result callbacks matching WPF.
- Enhancement Improvements to *GetXamlDependencies* supporting more scenarios and [UserControls](_UserControl.md).
- Enhancement Xbox One renderer improved using Fast Semantics.
- Enhancement New Font matching algorithm same as WPF.
- Enhancement C# Changes to error management:

> - No C# exceptions thrown for errors generated in C++. Errors are sent to the log.
> - New *Noesis.Error.SetUnhandledCallback()* to handle exceptions occurring in C# callbacks.

- Enhancement C# Added support for [PropertyMetadata](../Gui.DependencySystem/_PropertyMetadata.md) coerce callbacks.
- Enhancement [PropertyMetadata](../Gui.DependencySystem/_PropertyMetadata.md) constructors and derived classes like WPF ([#1355](https://www.noesisengine.com/bugs/view.php?id=1355)).
- Enhancement Implemented [AlternationConverter](_AlternationConverter.md).
- Enhancement [MarkupExtension](_MarkupExtension.md) *ProvideValue* argument is now ValueTargetProvider\*.
- Fixed Windows 7 incompatibility introduced in previous beta.
- Fixed Error parsing FillRule="EvenOdd ([#1384](https://www.noesisengine.com/bugs/view.php?id=1384)).
- Fixed [ContentPresenter](_ContentPresenter.md) placed as root of template can't resolve bindings ([#1335](https://www.noesisengine.com/bugs/view.php?id=1335)).
- Fixed Setting fixed scrollbar thumb size doesn't work ([#1375](https://www.noesisengine.com/bugs/view.php?id=1375)).
- Fixed *StringFormat* working with NaN and Infinity.
- Fixed Mouse right click on empty screen crashing.
- Fixed Incorrect font rendering for faces with USE\_TYPO\_METRICS os2 flag ([#1370](https://www.noesisengine.com/bugs/view.php?id=1370))
- Fixed [TextBox](_TextBox.md) caret and selection not updated when changing *Text* property.
- Fixed [BindingExpression](_BindingExpression.md) *UpdateTarget()* not working when used inside *PropertyChangedCallback*.
- Fixed Chained removed elements in [Panel](_Panel.md) crashing ([#1391](https://www.noesisengine.com/bugs/view.php?id=1391)).
- Fixed Incorrect [Border](_Border.md) geometry for stroke thickness greater than available size.
- Fixed [TabControl](_TabControl.md) changing *ViewModel* selected tab when *ItemsSource* reset.
- Fixed [MenuItem](_MenuItem.md) crashing when template not including items host.
- Fixed Crash arranging [TabControl](_TabControl.md) with collapsed tabs.
- Fixed Default style triggers registered twice when using BasedOn.
- Fixed Rare crash destroying faces in render thread.
- Fixed Bug in [StreamGeometry](_StreamGeometry.md) parser ([#1359](https://www.noesisengine.com/bugs/view.php?id=1359)).
- Fixed Incorrect number of *MouseButtonDown* events generated on double clicks ([#1310](https://www.noesisengine.com/bugs/view.php?id=1310)).
- Fixed Rare crash destroying bindings of template elements.

# Version 2.2.0b5

- Feature Implemented [Binding](_Binding.md) *Delay* property ([#1367](https://www.noesisengine.com/bugs/view.php?id=1367)).
- Feature Implemented *AlternationCount* property for [ItemsControl](_ItemsControl.md).
- Enhancement Support for custom numeric formats in [StringFormat](DataBindingTutorial.md#standard-numeric-format-strings) ([#877](https://www.noesisengine.com/bugs/view.php?id=877) [#996](https://www.noesisengine.com/bugs/view.php?id=996) [#1368](https://www.noesisengine.com/bugs/view.php?id=1368)).
- Enhancement Identifiers for float and double changed to "Single" and "Double" to match WPF.
- Enhancement Storyboard playing API behaving like WPF ([#1182](https://www.noesisengine.com/bugs/view.php?id=1182)).
- Enhancement [TextBox](_TextBox.md) events *TextChanged* and *SelectionChanged* behaving like WPF.
- Enhancement Reflection metadata optimized for size in MSVC (binaries decreased by 10%).
- Enhancement App Android apps were not resuming. Improvements to Activity Lifecycle handling.
- Enhancement App Implemented support for multisampling in Android.
- Enhancement App Improved uploading geometry performance in *GLRenderDevice*.
- Enhancement App GL\_EXT\_disjoint\_timer\_query implemented in *GLRenderContext*.
- Enhancement App Color buffer clearing avoided whenever possible.
- Enhancement App Support for GL core profile implemented in Linux.
- Enhancement C# [Geometry](_Geometry.md) *Parse* function exposed ([#1356](https://www.noesisengine.com/bugs/view.php?id=1356)).
- Enhancement C# *Point*, *Size* and *Rect* exposed with same interface as WPF ([#1052](https://www.noesisengine.com/bugs/view.php?id=1052)).
- Enhancement C# Added WPF *Vector* and *Matrix* types.
- Enhancement C# Exposed *XamlReader* class to parse XAMLs from text ([#1039](https://www.noesisengine.com/bugs/view.php?id=1039)).
- Enhancement C# Crashes during reloading of managed assemblies.
- Enhancement C# [Grid](_Grid.md) and [UniformGrid](_UniformGrid.md) properties exposed as int matching WPF.
- Enhancement C# *StreamGeometryContext* API matching WPF ([#833](https://www.noesisengine.com/bugs/view.php?id=833)).
- Fixed [Grid](_Grid.md) layout not always correct when using Min/Max limits in columns or rows.
- Fixed *StreamGeometryContext* requires *Close* or *Dispose* to flush commands matching WPF ([#1148](https://www.noesisengine.com/bugs/view.php?id=1148)).
- Fixed *ContextMenuOpening* event not sent for disabled Buttons ([#1382](https://www.noesisengine.com/bugs/view.php?id=1382)).
- Fixed [TextBlock](_TextBlock.md) TextTrimming="CharacterEllipsis very often is faulty ([#1275](https://www.noesisengine.com/bugs/view.php?id=1275)).
- Fixed [TextBlock](_TextBlock.md) measure failing in rare cases ([#1249](https://www.noesisengine.com/bugs/view.php?id=1249)).
- Fixed Wrong binding values when [ItemsControl](_ItemsControl.md) container disconnected ([#1317](https://www.noesisengine.com/bugs/view.php?id=1317)).
- Fixed Focus lost when focused element collapsed or disabled.
- Fixed Cycle directional keyboard navigation not working correctly.
- Fixed Mouse over element not updated when collapsed or disabled.
- Fixed MouseWheel incorrectly handled with nested [ScrollViewer](_ScrollViewer.md).
- Fixed [StyleInteraction](../App.Interactivity/_StyleInteraction.md) triggers not working in *ItemTemplates*.
- Fixed Focus shouldn't change while *View* is deactivated.
- Fixed App [TargetedTriggerAction](../App.Interactivity/_TargetedTriggerAction.md) incorrectly using *Target* when *TargetName* not found.
- Fixed C# [VisualTreeHelper](_VisualTreeHelper.md) methods should receive a [DependencyObject](../Gui.DependencySystem/_DependencyObject.md) ([#1043](https://www.noesisengine.com/bugs/view.php?id=1043)).
- Fixed C# [GridLength](_GridLength.md) struct not exposed ([#739](https://www.noesisengine.com/bugs/view.php?id=739)).
- Fixed C# Strange values calling *SetCurrentValue* with floats on double properties ([#1163](https://www.noesisengine.com/bugs/view.php?id=1163)).
- Fixed C# Exceptions in converters thrown at confusing times ([#1329](https://www.noesisengine.com/bugs/view.php?id=1329)).
- Fixed C# Binding context unavailable inside nested scopes ([#1323](https://www.noesisengine.com/bugs/view.php?id=1323)).
- Fixed C# [ItemCollection](_ItemCollection.md) should implement *IEnumerable* ([#1044](https://www.noesisengine.com/bugs/view.php?id=1044)).
- Fixed C# Exception "Native type is not registered" getting [ToolTip](_ToolTip.md)'s Parent ([#1143](https://www.noesisengine.com/bugs/view.php?id=1143)).
- Fixed C# Crash removing *SelectedItem* from string collection bound to [ListBox](_ListBox.md) ([#1371](https://www.noesisengine.com/bugs/view.php?id=1371)).

# Version 2.2.0b4

- Android arm64 New platform supported.
- Enhancement System fonts implemented for iOS and Android.
- Enhancement Exposed *CanHorizontallyScroll* and similar [ScrollContentPresenter](_ScrollContentPresenter.md) properties to XAML ([#1281](https://www.noesisengine.com/bugs/view.php?id=1281)).
- Enhancement *PPAAMode* property added to selectively disable *PPAA*.
- Enhancement Improved error message when animating non defined properties.
- Enhancement C# *IsDisposed* added to *BaseComponent*.
- Fixed C# Crash destroying [UIElement](_UIElement.md) with event handlers.
- Fixed C# Wrong event handler type registered for *SizeChanged* event.
- Fixed C# Missing *InvokeHandler* method in *ManipulationCompletedEventArgs*.
- Fixed C# *MeasureOverride* and *ArrangeOverride* not invoking base class.
- Fixed C# Custom *INotifyCollectionChanged* not working as *ItemsSource*.
- Fixed OpenGL black screen workaround for macOS 10.14 and Xcode 10.
- Fixed Mouse [Left|Right] button event dispatching non WPF compliant.
- Fixed [TabPanel](_TabPanel.md) invoking *Arrange* on collapsed children tabs.
- Fixed Elements left in layout queues after being destroyed.
- Fixed Crash accessing *Target* of [TargetedTriggerAction](../App.Interactivity/_TargetedTriggerAction.md) after destroyed.
- Fixed Routed event class handlers for base classes not invoked.
- Fixed [ComboBox](_ComboBox.md) selecting wrong item when drop down needs scroll.
- Fixed *StaysOpen* set to *False* not keeping popup opened when interacting.
- Fixed Controls in [Expander](_Expander.md) *Header* not responding ([#1165](https://www.noesisengine.com/bugs/view.php?id=1165)).
- Fixed Incorrect layout of [Grid](_Grid.md) ([#1350](https://www.noesisengine.com/bugs/view.php?id=1350)).
- Fixed [ContentPresenter](_ContentPresenter.md) failing to show data bound *Content* ([#1344](https://www.noesisengine.com/bugs/view.php?id=1344)).
- Fixed Window resize not working for Metal in macOS.
- Fixed Rare crash releasing fonts during shutdown.

# Version 2.2.0b3

- Enhancement Improved glyph cache usage for text under zoom animation.
- Enhancement App Improved detection of XInput controllers to avoid wasting CPU time.
- Enhancement App Audio and IME working in macOS.
- Enhancement App Implemented Metal renderer in macOS.
- Enhancement Added support for system fonts in macOS.
- Enhancement C++ documentation commenting about the option of using *BaseRefCounted* objects in the stack.
- Enhancement *RoutingStrategy* enumeration matching WPF: Tunnel(0), Bubble(1), Direct(2).
- Enhancement [CheckBox](_CheckBox.md) and [RadioButton](_RadioButton.md) default templates now use a [Grid](_Grid.md) to layout like in WPF.
- Enhancement GPU vertex streaming functions using SIMD.
- Fixed Inherited properties not propagating to children not connected to *View*.
- Fixed Attached properties not reporting XAML dependencies correctly.
- Fixed Incorrect color channel order in [CachedBitmap](_BitmapSource.md).
- Fixed TrueType Collections (.ttc) not working.
- Fixed Wrong [BulletDecorator](_BulletDecorator.md) layout compared to WPF.
- Fixed Multi-line text resetting scroll offset when typing text.
- Fixed *ChangePropertyAction* not working when defined inside a [Style](_Style.md).
- Fixed Rare crash in *Event* handler.
- Fixed Clipping paths no longer generating PPAA borders.
- Fixed Old view model setters being called setting *DataContext* to null.
- Fixed Bindings inside template definitions incorrectly registering against changed events.
- Fixed Reduced binding logging verbosity.
- Fixed [DataTemplate](_DataTemplate.md) lookup not working for boxed items.
- Fixed [TimerTrigger](../App.Interactivity/_TimerTrigger.md) crash trying to access already destroyed *View*.

# Version 2.2.0b2

- Enhancement App Buffer management improved in GL renderer. Performance is much better now in WebGL.
- Enhancement App Added mouse wheel support to *XDisplay*.
- Enhancement App Added IME support to *XDisplay*.
- Enhancement New tutorial about [Drag-and-Drop](DragDrop.md).
- Enhancement *GetXamlDependencies()* was not reporting fallback fonts. Dependencies are now given using a callback.
- Enhancement Added compatibility to GCC 7.
- Enhancement System fonts implemented in Linux.
- Enhancement Minor tweaks to scrollbar and progressbar in default theme.
- Enhancement Support for null items in [ItemsControl](_ItemsControl.md).
- Enhancement Batching improvements when using masks.
- Fixed Crash in reflection when setting string properties to null.
- Fixed *FindFirst/FindNext* not working correctly in Linux (and potentially in Windows 32 bits).
- Fixed [ScrollContentPresenter](_ScrollContentPresenter.md) *MakeVisible* changing scroll even if element was visible.
- Fixed [StackPanel](_StackPanel.md) *MakeVisible* failing when having different item sizes.
- Fixed *GetHashCode()* for pointers not compiling in *Emscripten*.
- Fixed [ItemsControl](_ItemsControl.md) comparing items using pointers instead of *Equals*.
- Fixed App Fixed buffer overflow crash in audio.

# Version 2.2.0b1

- WebGL C++ New platform supported.
- Feature Interactivity ([Behaviors](../App.Interactivity/_Behavior.md), [Triggers](../App.Interactivity/_EventTrigger.md) and [Actions](../App.Interactivity/_TriggerAction.md)) architecture implemented. More details in the new [tutorial](../App.Interactivity/Behaviors.md).
- Feature Implemented *Drag & Drop* architecture. Added *Inventory* sample.
- Feature Implemented support for *FontFamily* fallbacks.

  ```
  <TextBlock
      HorizontalAlignment="Center" VerticalAlignment="Center"
      FontFamily="Fonts/#LCDMono2, #Roboto, #Segoe UI Emoji"
      Foreground="Black" FontSize="30">
  </TextBlock>
  ```
- Feature Support for *Microsoft Color Fonts* ([CPAL/COLR](https://docs.microsoft.com/en-us/windows/desktop/directwrite/color-fonts)). Emojis! 😊

  ```
  <TextBlock Foreground="Black" FontFamily="Fonts/#Segoe UI Emoji">
    <Run FontSize="10">😃🐻🍔⚽💡🤷😍🔥👀</Run>
  </TextBlock>
  ```
- Feature Implemented [InlineUIContainer](_InlineUIContainer.md).

  ```
  <TextBlock >
    <Run>
      A UIElement element may be embedded directly in flow content
      by enclosing it in an InlineUIContainer element
    </Run>
    <InlineUIContainer>
      <Image Source="Images/item.png" Stretch="None"/>
    </InlineUIContainer>
  </TextBlock>
  ```
- Enhancement New font metrics matching WPF. Text rendering may look different after this change.
- Enhancement View input methods returning true to indicate if event was handled.
- Enhancement *NoesisGUI SDK Browser*, a new welcome application for newcomers.
- Enhancement Implemented [Binding](_Binding.md) *TargetNullValue* property.
- Enhancement [BaseValueConverter](_BaseValueConverter.md) derived classes can use *StaticResources* in XAML to set own properties.
- Enhancement Warning messages in [VirtualizingPanel](_VirtualizingPanel.md) when virtualization cannot be activated.
- Enhancement *RenderDevice*: BGRA format deprecated in favor of RGBA to avoid using GL extension.
- Enhancement Improved GCC make flags to reduce binary sizes. LTO enabled in release configuration.
- Enhancement C++ *NsDynamicCast* renamed to *DynamicCast*. *NsStaticCast* removed.
- Enhancement [ItemsControl](_ItemsControl.md) *BringIntoView* renamed to *OnBringItemIntoView*.
- Enhancement PS4 Improvements to *RenderDevice* implementation. IME implemented in *App* framework.
- Enhancement Improved view stats. New counters added for flushes and uploaded geometry.
- Enhancement *FrameworkOptions* renamed to *FrameworkPropertyMetadata*. Added setters to all properties to match WPF.
- Enhancement Exposed scroll functions in [BaseTextBox](_BaseTextBox.md).
- Enhancement Implemented [TextBox](_TextBox.md) functions: *Select*, *Clear*, *GetCharacterIndexFromPoint*, *GetCharacterIndexFromLineIndex*, *GetLineIndexFromCharacterIndex*, *GetLineLength*, *GetFirstVisibleLineIndex*, *GetLastVisibleLineIndex* and *ScrollToLine*.
- Enhancement Implemented all tab placements for [TabControl](_TabControl.md).
- Enhancement Mouse capture related properties and events updated according to WPF order.
- Enhancement Callbacks for opening URLs and for playing audio added to *IntegrationAPI* header.
- Enhancement Support for injecting custom profiler defining *NS\_PROFILE\_CPU* macro.
- Enhancement Exposed [FrameworkElement](_FrameworkElement.md) *InputScope* to specify the kind of input from On-Screen Keyboards.
- Enhancement Added *HideCaret* to [TextBox](_TextBox.md) and [PasswordBox](_PasswordBox.md) to disable caret when required.
- Enhancement *Open* and *Hide* Software Keyboard callbacks unified.
- Enhancement Improvements (around 15%) in render performance by optimizing internal tree.
- Enhancement Cursor callback now receives the source view.
- Enhancement New view functions to handle timers.
- Enhancement *IList* and *IDictionary* interfaces simplified.
- Enhancement *Collection<T>* and *ObservableCollection<T>* are now clean implementations that match WPF.
- Enhancement Added *Uri* type, used to scan XAML dependencies.
- Enhancement Implemented *GUI::GetXamlDependencies()* to find all dependent resources.
- Enhancement Improvements to memory allocations when updating text controls.
- Enhancement *TessellationQuality* enumeration deprecated. View accepts now a float indicating the maximum pixel error.
- Enhancement Glyphs rendered with triangles use *PPAA* if enabled.
- Enhancement Support for [TextBlock](_TextBlock.md) *LineHeight* and *LineStackingStrategy*.
- Enhancement Improvements to [ResourceDictionary](_ResourceDictionary.md) when changing *Source*.
- Enhancement App Support for audio implemented.
- Enhancement App Support for gamepad implemented in *Win32Display* (using XInput).
- Enhancement App *--runInBackground* command line to disable pausing the application when in background.
- Fixed Rare crash when animating opacity groups.
- Fixed Ghost lines when rendering [VisualBrush](_VisualBrush.md).
- Fixed [TextBox](_TextBox.md) scroll bars incorrectly showing beam cursor.
- Fixed Changes to [ScrollViewer](_ScrollViewer.md) *HorizontalScrollBarVisibility* and *VerticalScrollBarVisibility* not affecting measure.
- Fixed [TextBox](_TextBox.md) not updating *HorizontalScrollBarVisibility* when *TextWrapping* changed.
- Fixed *TextTrimming* ellipses not stroked.
- Fixed '\r' counted as a letter during text formatting.
- Fixed [DataTrigger](_DataTrigger.md) failing when trigger and binding value were the same.
- Fixed Memory corruption in [DataTrigger](_DataTrigger.md) with self binding.
- Fixed Trigger animations using frozen resources not properly removed.
- Fixed [UIElement](_UIElement.md) *IsKeyboardFocused* and *IsKeyboardFocusWithin* returning incorrect values on uninitialized objects.
- Fixed Memory leak in delegate implementation.
- Fixed Glyph rendering could show glitches sometimes.
- Fixed [ContextMenu](_ContextMenu.md) not closing properly when using complex templates.
- Fixed Cannot show [ContextMenu](_ContextMenu.md) programmatically defined in *Resources*.
- Fixed Added copy-paste context menu for [TextBox](_TextBox.md).
- Fixed [ListView](../Gui.Controls/_ListView.md) layout problems when showing horizontal scrollbar.
- Fixed [TextBox](_TextBox.md) ignoring alignment with empty text.
- Fixed Inherited properties not updated when control removed from tree.
- Fixed [Selector](_Selector.md) not destroying items when using *ObservableCollection.Clear*.
- Fixed [ScrollViewer](_ScrollViewer.md) *ScrollChanged* arguments not calculated correctly with *Infinite* viewport.
- Fixed [ResourceDictionary](_ResourceDictionary.md) not searching merged dictionaries in the correct order.
- Fixed C# [ResourceDictionary](_ResourceDictionary.md) not exposing *IDictionary*.
- Fixed Focus engagement affecting controls that don't need it.
- Fixed *TwoWay* bindings not updating converter when changing target value.
- Fixed *Width* and *Height* constraints incorrectly clipping panels.
- Fixed Incorrect line scroll in [VirtualizingStackPanel](_VirtualizingStackPanel.md) when virtualization disabled.
- Fixed *Nullable* properties incorrectly binding *TwoWay* bindings.
- Fixed [ToolTip](_ToolTip.md) not hidden after focusing new element.
- Fixed *Infinite* loop in view *Layout* algorithm.
- Fixed [PasswordBox](_PasswordBox.md) *PasswordChar* not allowing Unicode chars.
- Fixed [PasswordBox](_PasswordBox.md) *GotFocus* not respecting SelectAll.
- Fixed Nested *OpacityMask* incorrectly displayed.
- Fixed Self binding not using converter with null *DataContext*.
- Fixed *DataContext* in [ContentPresenter](_ContentPresenter.md) ignoring null *Content*.
- Fixed *PropertyPath* not supporting '/' (and many other characters) as part of the indexer key.
- Fixed Binding *FallbackValue* can't be set using *StaticResource* in XAML.
- Fixed Binding *FallbackValue* can't be set to {x:Null} in XAML.
- Fixed *TargetType* and *DataType* using prefixes failing without x:Type extension.
- Fixed [DataTrigger](_DataTrigger.md) not working when condition value is null.
- Fixed Dropdown [Popup](_Popup.md) remains visible while scrolling parent.
- Fixed [ToolTip](_ToolTip.md) incorrectly added as logical or visual child.
- Fixed Sometimes [MenuItem](_MenuItem.md) *IsPressed* was not updated.
- Fixed [MenuItem](_MenuItem.md) without *Header* not closed when clicked.
- Fixed Keyboard keeps referencing focused element when removed from tree.
- Fixed [TreeViewItem](_TreeViewItem.md) *BringIntoView* not behaving as in WPF.

# Previous Versions

## [Version 2.1](Changelog_v21.md)

## [Version 2.0](Changelog_v20.md)

## [Version 1.2](Changelog_v12.md)

## [Version 1.1](Changelog_v11.md)