Source: https://www.noesisengine.com/docs/Gui.Core.Changelog_v21.html

# NoesisGUI 2.1 Changelog

# Version 2.1.0

- Fixed Unhandled *MouseDoubleClick* wasn't generating *MouseDown* events.

# Version 2.1.0rc4

- Enhancement Added validation callbacks to *BorderThickness*, *Margin*, *Padding* and *CornerRadius*.
- Enhancement Unity *RenderTexture* no longer updating when mesh not visible.
- Enhancement Unity Updated support for gamepad.
- Fixed *IsHitTestVisible* being ignored with touch input.
- Fixed Binding a managed enum property to a string property displaying nothing.
- Fixed [RadioButton](_RadioButton.md) was incorrectly setting *IsChecked* local value on click.
- Fixed C# color conversion from/to linear was not following WPF algorithm.
- Fixed Crash when animation starting from constructor instead of *Initialized* event.
- Fixed Crash if no [Panel](_Panel.md) was set as root of *ItemsPanelTemplate*.
- Fixed Crash when code-behind class inheriting from wrong parent class.
- Fixed Unity removing */Library* folder no longer corrupts XAML assets db.

# Version 2.1.0rc3

- Enhancement New [Integration](SDKGuide.md) tutorial.
- Enhancement Added support for horizontal mouse wheel.
- Enhancement *IView::AxisY* and *IView::AxisX* renamed to *Scroll* and *HScroll* respectively.
- Enhancement [RepeatButton](_RepeatButton.md) default values for *Delay*, *Interval* and *ClickMode* matching WPF.
- Enhancement *UserControl* and *CustomControl* samples added to C# SDK.
- Enhancement Minor improvement to rotated text rendering.
- Enhancement Binding log messages improved.
- Enhancement C++ *FindResource(const char\*)* added to [FrameworkElement](_FrameworkElement.md).
- Enhancement C# Color matching WPF.
- Fixed Better support for degenerate matrices applied to visual elements.
- Fixed Focus is no longer moved to the first control after *View* first layout.
- Fixed C# proxies returning invalid pointer after being destroyed during *Shutdown*.
- Fixed Keyboard crashing when focused element changing in the middle of notification.
- Fixed *InputBindings* not using *CommandParameter* when command being invoked.
- Fixed [CheckBox](_CheckBox.md) default value for *KeyboardNavigation.AcceptsReturn* matching WPF.
- Fixed *KeyGestureConverter* failing for some keys.
- Fixed Directional navigation not working as expected sometimes.

# Version 2.1.0rc2

- Enhancement AppFramework DPI awareness in Win32 applications enabled.
- Enhancement [Blend](BlendTutorial.md), [XamlPlayer](FirstSteps.md) and [Performance](Optimizing.md) tutorials updated.
- Enhancement C++ *BlendTutorial* sample added.
- Fixed Problem with *NaN* comparisons in double dependency properties.
- Fixed Unity Support for all texture slots when rendering to texture.

# Version 2.1.0rc1

- Enhancement C++ *UserControl* and *CustomControl* samples added.
- Enhancement C# Improved callstack for errors when crossing between C++ and C#.
- Enhancement More improvements to Focus engagement.
- Fixed *TreeView.SelectedItem* was keeping references to removed item when using *ItemsSource*.
- Fixed Crash in *Mouse* when hovered element was destroyed.

# Version 2.1.0b17

- Enhancement [Styling tutorial](StylingTutorial.md) updated. Global dictionary now behaves exactly as *WPF* *Application.Resources*.
- Enhancement C++ *Commands* samples added.
- Enhancement Improvements to Focus engagement.
- Fixed *StaticResource* search failed on *Style.BasedOn* using the same type key.

# Version 2.1.0b16

- Enhancement Added gamepad input buttons to *Key* enumeration.
- Enhancement [Focus engagement](https://docs.microsoft.com/en-us/windows/uwp/design/devices/designing-for-tv#focus-engagement) implemented.
- Enhancement Half precision floats deprecated to avoid artifacts when rendering opacity groups.
- Fixed C# Enum CLR properties not working.
- Fixed *MouseUp* events had incorrect button state.
- Fixed Opacities not working in a few GL devices due to incorrect *glInvalidateFramebuffer* usage.
- Fixed Artifacts using [VisualBrush](_VisualBrush.md) with *PPA* enabled.

# Version 2.1.0b15

- Enhancement New [C++ Architecture Guide](CppArchitectureGuide.md).
- Enhancement C++ All samples located in *NoesisSDK/Data* reviewed and improved.
- Enhancement C++ Implemented automatic conversion to *T\** from *Ptr<>*.
- Enhancement C++ New *MakePtr* function as an alternative to the '*\*new*' idiom
- Enhancement AppFramework Android compatibility with application framework.
- Enhancement AppFramework Improved *HighResTimer* implementation to avoid float imprecisions.
- Enhancement AppFramework Message loop improvements to support *CADisplayLink* and *WebGL*.
- Enhancement AppFramework Touch keyboard implemented in iOS and Android.
- Enhancement Added *IView.AxisX()* to input horizontal scroll.
- Enhancement Improved color batching rendering debug mode.
- Enhancement New XamlPlayer look, more friendly in all platforms.
- Enhancement Improved the way touch *Manipulations* are updated, better refresh rate.
- Fixed *Selector.SelectedIndex* incorrectly allowing values < -1.
- Fixed Wrong default value of a *DependencyProperty* with type 'object'.
- Fixed [ContentPresenter](_ContentPresenter.md) not disconnecting template triggers when root was [TextBlock](_TextBlock.md).
- Fixed *Items* not disconnected from [ContentPresenter](_ContentPresenter.md) when directly connected without *DataTemplate*.
- Fixed [TabControl](_TabControl.md) can move now between tabs using *Ctrl+Tab*.
- Fixed [ComboBox](_ComboBox.md) and [Slider](_Slider.md) fully working with keyboard.
- Fixed *GetDefaultValueObject* in *PropertyMetadata* crashing for types with sizeof(T) > sizeof(void\*).
- Fixed Bindings failing when converter was initially required and not needed after source value change.
- Fixed Rendering artifacts with opacity groups and nested objects.

# Version 2.1.0b12

- Enhancement Many tutorials updated. Work in progress.
- Enhancement Touch identifiers are now sent as 64-bits integer to *Views*.
- Enhancement C++ *Data/* samples updated. Work in progress.
- Enhancement C++ AppFramework for *macOS* and *iOS* added to SDK.
- Enhancement Unity New sample 'TicTacToe' added to Unity package.
- Fixed *DynamicResource* was not searching in *Application.Resources* dictionary.
- Fixed C# Custom enums were not working.
- Fixed Freezable objects are now free-threaded when they are frozen.

# Version 2.1.0b10

- Feature C++ NoesisApp framework, a multiplatform open source library used for all our examples.
- Feature C++ All our Unity samples are now included in the C++ SDK and in [Github](https://github.com/Noesis/Tutorials/tree/master/Samples).
- Feature C++ A logging handler can be passed to Noesis::GUI::Init.
- Feature Unreal Engine is now a officially supported [plugin](https://github.com/Noesis/UE4Plugin). Added documentation for each [sample](https://github.com/Noesis/Tutorials/tree/master/Samples/Scoreboard/UE4) in [Github](https://github.com/Noesis/Tutorials/tree/master/Samples).
- Enhancement C++ Changed all custom basic types to standard ones (*uint32\_t* and friends).
- Enhancement C++ No longer using nested namespaces. Now all Noesis API is inside namespace Noesis.
- Enhancement [KeyBinding](_KeyBinding.md) exposing *Key* and *Modifiers* as bindable dependency properties.
- Enhancement Very long text lines are now clipped and sent to GPU more efficiently.
- Enhancement C++ Confusing *SetAntialiasingMode()* function in *IView* renamed to *SetIsPPAAEnabled()*.
- Enhancement C++ Added *Activate()* and *Deactivate()* to *IView*. *ResetInputState()* removed.
- Enhancement C++ Improvements to Integration API: *CreateVGContext()* no longer necessary. See integration sample.
- Enhancement C++ Support for enum class in reflection macros.
- Enhancement C++ Noesis.dll is now compatible with delayed loading.
- Enhancement C++ *Noesis::GUI::SetTheme()* is now named *SetApplicationResources()*. Behavior changed to mimic WPF.
- Enhancement Support for system fonts (Windows for now) <TextBlock FontFamily="Arial"/>.
- Enhancement *PropertyMetadata.PropertyChangedCallback* and *CoerceValueCallback* renamed to match WPF name.
- Enhancement PropertyMetadata override now correctly accumulates *PropertyChanged* delegates.
- Enhancement *DependencyProperty.ValidateValueCallback* renamed to match WPF name.
- Enhancement Error not shown if *Setter.TargetName*, *Trigger.SourceName* or *Condition.SourceName* used inside a Style.
- Enhancement Implemented [BaseTextBox](_BaseTextBox.md) *TextChanged* and *SelectionChanged* events.
- Enhancement *x:Class* type checks made less restrictive to continue loading the xaml.
- Enhancement Unity Binding warnings can be enabled in *NoesisSettings*.
- Enhancement Unity New *HelloWorld* sample.
- Fixed Incorrect *TextBox.SelectionStart* when selection was done from right to left.
- Fixed *SelectionChanged* event not raised on *ListBoxItem.IsSelected* modified.
- Fixed *BitmapImage.UriSource* property can't be set on xaml.
- Fixed Crash in *TimeManager::UnregisterTarget*.
- Fixed [Button](_Button.md) now overrides *AcceptsReturn* to raise *Click* event on return key pressed.
- Fixed Float rounding in layout generating unnecessary clipping.
- Fixed [TabControl](_TabControl.md) not displaying tab content if *SelectedIndex* was initially set.
- Fixed Crash when hovering over an element already destroyed.
- Fixed Horizontal scroll of [ListView](../Gui.Controls/_ListView.md) / [ListBox](_ListBox.md) not working.
- Fixed [ContentPresenter](_ContentPresenter.md) was not removing old parent in some cases.
- Fixed Unity Crash when rendering to texture using material without texture.
- Fixed Unity *NoesisEditor.OnSceneGUI* throwing errors when Main Camera gets disabled or is not present.

# Version 2.1.0b4

- Enhancement C++ *Nullables* can now be constructed from *nullptr*.
- Enhancement C++ Added *RaiseCanExecuteChanged* to *BaseCommand* class.
- Enhancement C++ *Count* property now available to be bound in *ObservableCollection*.
- Enhancement Unity Improved stability when reloading assemblies.
- Fixed Unity Package no longer raising errors first time it is installed.
- Fixed *UpdateLayout* not working when called from *Loaded* event handler.
- Fixed *OnCursorChanged* crashing when element already removed from View.
- Fixed *LoadComponent()* error message was not showing the correct uri.
- Fixed *IsSelected* not updated correctly when inserting items in a single selection list.
- Fixed [TextBox](_TextBox.md) internal text element shouldn't be affected by TextBlock styles.
- Fixed Template element *InputBindings* and *CommandBindings* not being cloned.
- Fixed Crash destroying Viewbox that was part of a template.

# Version 2.1.0b3

- Feature Unity 2017.1 and .NET 4.6 supported.
- Enhancement [DependencyObject](../Gui.DependencySystem/_DependencyObject.md) is now more efficient when reading and writing properties.
- Enhancement [Button](_Button.md) and [MenuItem](_MenuItem.md) *IsEnabled* property updated when command *CanExecuteChanged* raised.
- Enhancement Reduced the number of uncached file accesses to *TrueType* files.
- Enhancement All platforms compiling with FAST\_MATH.
- Enhancement Many PlayStation 4 improvements and compatibility with latest SDK.
- Enhancement Unity *Reimport All* button now scans assets in proper order.
- Fixed Crash with binding set in non [FrameworkElement](_FrameworkElement.md) object.
- Fixed Elements invalidated during parent layout not correctly measured.
- Fixed *FillBehavior=Stop* ignored when beginning controllable storyboard.
- Fixed [ListBox](_ListBox.md) clipping not updated when using virtualization and changing size.
- Fixed Selection not updated when adding or removing items to source collection.
- Fixed Right clicking an item does not select it when [ContextMenu](_ContextMenu.md) is open.
- Fixed Mouse Down/Up events order now matches WPF order.
- Fixed *TextBlock.Run* not receiving *ViewModel* updates.
- Fixed [ComboBox](_ComboBox.md) appears with no selection even with *SelectedIndex* bound.
- Fixed [TextBlock](_TextBlock.md) and other classes didn't override *DefaultStyleKey* property.
- Fixed *EventTriggers* in theme style not working.
- Fixed Crash on [TextBlock](_TextBlock.md) mouse over when inlines dynamically added.
- Fixed Ribbon UI buttons not working first time selection is made.
- Fixed [UIElement](_UIElement.md) flag properties still with old values when *PropertyChangedCallback* invoked.
- Fixed *Nullable* properties not correctly animated.
- Fixed Unity Attempting to debug scripts causes Unity to become non-responsive.

# Version 2.1.0b2

- Enhancement Better error messages including XAML file and line.
- Fixed Inherited properties not invalidated when elements being removed from tree.
- Fixed Implicit style lookup was incorrect compared to WPF for non Control elements.
- Fixed [Trigger](_Trigger.md) actions in value providers invoked in inverse order of priority.
- Fixed Crash in binding with *RelativeSource* *FindAncestor* when type was not resolved.
- Fixed [Popup](_Popup.md) *Closed* event was raised twice for [ContextMenu](_ContextMenu.md).
- Fixed Some controls were not removing logical children when being destroyed.
- Fixed Crash calling already destroyed object during event delegate invocation.
- Fixed *ListBoxItem.IsSelected* not updating inside *SelectionChanged* event.
- Fixed *StringFormat* now supports non numerical types when binding.

# Version 2.1.0b1

- Enhancement Improvements to error handling in XAML parser.
- Fixed Virtualization was not using recycled containers correctly, and the whole visual tree was always being regenerated.
- Fixed C++ Added compatibility with *Fast* float point model.
- Fixed [ListView](../Gui.Controls/_ListView.md) style in Noesis theme was not allowing virtualization.
- Fixed Bindings not working sometimes in [TextBlock](_TextBlock.md) inlines when using DataContext as source.
- Fixed *Binding.ElementName* doesn't work in a DataTrigger/MultiDataTrigger if it refers to template child.
- Fixed Unable to register named [UserControl](_UserControl.md) in a template if using the same name for the root in the associated XAML.
- Fixed *Thickness* and *CornerRadius* converters can't convert from numeric values.
- Fixed Crash in *TimeManager* removing finished clock when target is already removed.
- Fixed [ListBox](_ListBox.md) moves items left when pressing buttons.