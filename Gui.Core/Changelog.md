Source: https://www.noesisengine.com/docs/Gui.Core.Changelog.html

# NoesisGUI 3.2 Release Notes

![Changelog_v32_8.png](https://www.noesisengine.com/docs/Changelog_v32_8.png)

# What's New?

- [New Text Shaping Algorithm](#featuretextshaping)
- [Improved Vector Graphics](#featurevectorgraphics)
- [Rive: Interactive Vector Animations](#featurerive)
- [Stereo Rendering](#featurestereorendering)
- [World Space UI](#featureworldspaceui)
- [Visual Studio Code Extension](#featurevscode)

# Version 3.2.10

*Released 20th Oct 2025* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Fixed Class-specific bindings not working on custom view models ([#3248](https://www.noesisengine.com/bugs/view.php?id=3248)).
- Fixed Crash using invalid property in [DataTemplate](_DataTemplate.md) trigger (#BS1327, #BS1328, #BS1329).
- Fixed Circular reference in [ResourceDictionary](_ResourceDictionary.md) causing stack overflow ([#4369](https://www.noesisengine.com/bugs/view.php?id=4369)).
- Fixed Concatenating two 'pack://' URIs producing invalid URI.
- Fixed Crash rendering more than 255 batches ([#4404](https://www.noesisengine.com/bugs/view.php?id=4404) [#4426](https://www.noesisengine.com/bugs/view.php?id=4426) [#4419](https://www.noesisengine.com/bugs/view.php?id=4419)).
- Fixed Crash processing a [NullExtension](_NullExtension.md) without active property (#BS1473-#BS1497).
- Fixed View calling renderer *ResolveRenderTarget* without matching *SetRenderTarget*.
- Fixed [VisualBrush](_VisualBrush.md) sometimes rendering black.
- Fixed Unity Offscreen renderer skipped, causing crashes ([#4404](https://www.noesisengine.com/bugs/view.php?id=4404) [#4410](https://www.noesisengine.com/bugs/view.php?id=4410)).
- Fixed Unity *Xaml.Dependencies* broken ([#4411](https://www.noesisengine.com/bugs/view.php?id=4411)).
- Fixed Unity Add explicit attachments in render graph (URP).
- Fixed Unity Prevent potential double stencil clear (HDRP).
- Fixed Unreal Skip clearing stencil buffer for offscreen render targets.

# Version 3.2.9

*Released 3rd Oct 2025* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature 🎮 Added support for Nintendo Switch 2.
- Feature Implemented [VirtualizingWrapPanel](_VirtualizingWrapPanel.md) ([#2346](https://www.noesisengine.com/bugs/view.php?id=2346)).
- Feature Support for building AOT projects with .NET 8+.
- Enhancement Improve draw batching performance using SIMD.
- Enhancement Add [Mesh](_Mesh.md) element for rendering [MeshData](_MeshData.md).
- Enhancement Support *XamlReader.Load* from Stream ([#1471](https://www.noesisengine.com/bugs/view.php?id=1471)).
- Enhancement Speed up [DataTrigger](_DataTrigger.md) initialization by 20% ([#4218](https://www.noesisengine.com/bugs/view.php?id=4218)).
- Enhancement Guarantee [UpdateTexture](RenderDeviceNotes.md#noesisgui-3-2) never called during render pass ([#3981](https://www.noesisengine.com/bugs/view.php?id=3981)).
- Enhancement Unity Import XAMLs asynchronously.
- Enhancement Unity Improve asset and global resource import times ([#3997](https://www.noesisengine.com/bugs/view.php?id=3997)).
- Fixed Resolve relative Uris ([#4091](https://www.noesisengine.com/bugs/view.php?id=4091)).
- Fixed Remove duplicate Expat symbols ([#4306](https://www.noesisengine.com/bugs/view.php?id=4306), [#3998](https://www.noesisengine.com/bugs/view.php?id=3998)).
- Fixed Format small numbers with negative exponential in 'F' mode.
- Fixed Internal compiler errors in VS2017 ([#4329](https://www.noesisengine.com/bugs/view.php?id=4329)).
- Fixed Optimize [CollectionSortBehavior](../App.Interactivity/_CollectionSortBehavior.md) using move operations ([#4197](https://www.noesisengine.com/bugs/view.php?id=4197)).
- Fixed Update [VirtualizingStackPanel](_VirtualizingStackPanel.md) cached item sizes on remove/move.
- Fixed Incorrect World UI culling ([#4269](https://www.noesisengine.com/bugs/view.php?id=4269)).
- Fixed PPAA artifacts.
- Fixed Artifacts rendering decorations ([#4222](https://www.noesisengine.com/bugs/view.php?id=4222), [#4314](https://www.noesisengine.com/bugs/view.php?id=4314)).
- Fixed Focus leaving [TabItem](_TabItem.md) header unexpectedly.
- Fixed [ContentPresenter](_ContentPresenter.md) template recreated unnecessarily on *Content* change.
- Fixed [TextBox](_TextBox.md) caret invisible when focused on load.
- Fixed Crash on shutdown if extended object already disposed.
- Fixed Glitches with nested [VisualBrushes](_VisualBrush.md) ([#4237](https://www.noesisengine.com/bugs/view.php?id=4237)).
- Fixed Wrong *LayoutTransform* size with *Skew* or *Rotate*.
- Fixed [ToolTip](_ToolTip.md) shown incorrectly when switching with BetweenShowDelay=0.
- Fixed [ImageBrush](_ImageBrush.md) using [DynamicTextureSource](_DynamicTextureSource.md) not rendering ([#4238](https://www.noesisengine.com/bugs/view.php?id=4238)).
- Fixed FileSystemWatcher canceling completion routine and timer on destroy.
- Fixed Artifacts resizing *Views*.
- Fixed Video in *Manual* mode not playing when *Source* set via binding ([#4240](https://www.noesisengine.com/bugs/view.php?id=4240)).
- Fixed Crash using [TextBox](_TextBox.md) *GetRangeBounds* when focused.
- Fixed [ContentPresenter](_ContentPresenter.md) context not updating after measure ([#4386](https://www.noesisengine.com/bugs/view.php?id=4386)).
- Fixed *TargetNullValue* ignored if binding required conversion.
- Fixed UpdateTexture not enqueuing changes in Metal renderer.
- Fixed Unity Crash destroying [TimerTrigger](../App.Interactivity/_TimerTrigger.md) when switching scenes.
- Fixed Unity Nothing renders in Vulkan on Linux ([#4244](https://www.noesisengine.com/bugs/view.php?id=4244)).
- Fixed Unity EventManager handlers not cleaned on domain unload ([#2359](https://www.noesisengine.com/bugs/view.php?id=2359)).
- Fixed Unity *NoesisView.IsEyeTexture* per-frame allocation ([#4234](https://www.noesisengine.com/bugs/view.php?id=4234)).
- Fixed Unity *IMultiValueConverter* ignored if also implements *IValueConverter* ([#1886](https://www.noesisengine.com/bugs/view.php?id=1886)).
- Fixed Unreal Crashes in macOS ([#3981](https://www.noesisengine.com/bugs/view.php?id=3981)).
- Fixed Unreal Uninitialized *PreviousCount* check fails ([#4268](https://www.noesisengine.com/bugs/view.php?id=4268)).
- Fixed Unreal Handle DPI Scale setting ([#4309](https://www.noesisengine.com/bugs/view.php?id=4309)).
- Fixed Unreal Wrong comparison recreating stencil buffer every frame.
- Fixed Unreal Wrong NS\_ASSERT\_UNREACHABLE in MediaEvent handler.
- Fixed Unreal Caching Pipeline State Objects (PSOs) ([#4196](https://www.noesisengine.com/bugs/view.php?id=4196)).
- Fixed Unreal Memoryless DepthStencil targets require *StoreAction=DontStore*.
- Fixed Unreal Missing *IRenderer::Shutdown* call in thumbnail renderer (memory leak).
- Fixed Unreal Noesis Enums unusable as XAML bindings ([#4379](https://www.noesisengine.com/bugs/view.php?id=4379)).
- Fixed LangServer Crash from material uniform expression caches.
- Fixed LangServer Crash when XAML tag ends with multibyte char.

# Version 3.2.8

*Released 6th Jun 2025* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Unreal Added support for UE 5.6.
- Enhancement Unreal Context menu added for textures to apply [premultiply-alpha](UnrealTutorial.md#textures).
- Enhancement Unity Added support for Unity 6.1 (Built-in, URP, HDRP).
- Enhancement Unity [First Steps tutorial](Unity3DTutorial.md) thoroughly reviewed.
- Enhancement Unity Added [Widget3D](https://github.com/Noesis/Tutorials/tree/master/Samples/Widget3D) sample to package.
- Enhancement LangServer Added snippet for root [ResourceDictionary](_ResourceDictionary.md).
- Enhancement LangServer Autocompletion shows properties below classes.
- Enhancement Significant performance improvements when removing/destroying elements from the Visual Tree.
- Enhancement Major performance gains across rendering and geometry systems.
- Enhancement Added support for Android NDK r28.
- Enhancement Added support for 16 KB page sizes on Android.
- Enhancement Virtualization cache added to [VirtualizingStackPanel](_VirtualizingStackPanel.md) (disabled by default).
- Enhancement Dispatcher checks disabled when NS\_MULTITHREADING=0 ([#2665](https://www.noesisengine.com/bugs/view.php?id=2665)).
- Enhancement Rive runtime updated to e96b58d (May 8th '25).
- Enhancement Major rendering speedups for Rive files.
- Enhancement Reduced draw calls when using *Transform3D*.
- Enhancement Delegate performance improved by avoiding virtual calls on hot paths.
- Enhancement Lambdas by reference now supported in *Delegates* ([#1141](https://www.noesisengine.com/bugs/view.php?id=1141), [#1081](https://www.noesisengine.com/bugs/view.php?id=1081)).
- Enhancement Improved [PPAA antialiasing](AntialiasingTutorial.md#per-primitive-antialiasing) quality.
- Feature Added [GeometryGroup](_GeometryGroup.md) ([#1777](https://www.noesisengine.com/bugs/view.php?id=1777), [#1948](https://www.noesisengine.com/bugs/view.php?id=1948)).
- Feature Implemented [FrameworkElement](_FrameworkElement.md) *SetResourceReference* ([#3991](https://www.noesisengine.com/bugs/view.php?id=3991)).
- Feature App Added [BoxShadow](ExtensionsTutorial.md#boxshadow) for analytic blurred rectangles.
- Fixed App Incorrect '*Activated*' event order in EmscriptenDisplay ([#3968](https://www.noesisengine.com/bugs/view.php?id=3968)).
- Fixed [CollectionFilterBehavior](../App.Interactivity/_CollectionFilterBehavior.md) predicate reuse issue.
- Fixed Crash when closing [Menu](_Menu.md) after template reload.
- Fixed [Popup](_Popup.md) not capturing mouse when *StaysOpen* was false.
- Fixed [Popup](_Popup.md) invalidating *Binding* after source destruction.
- Fixed Dropdown in [ComboBox](_ComboBox.md) misbehaving when larger than space ([#2825](https://www.noesisengine.com/bugs/view.php?id=2825)).
- Fixed [MenuItems](_MenuItem.md) not hiding submenus on mouse leave outside [Menu](_Menu.md) / [ContextMenu](_ContextMenu.md).
- Fixed [DataTrigger](_DataTrigger.md) triggering on *Collapsed* elements ([#3928](https://www.noesisengine.com/bugs/view.php?id=3928)).
- Fixed Crash rendering text with [VisualBrush](_VisualBrush.md) without source.
- Fixed Crash when using a [VisualBrush](_VisualBrush.md) in text.
- Fixed Crash updating [ToolTip](_ToolTip.md) from removed template.
- Fixed InlineCollection changes cause text to disappear ([#3954](https://www.noesisengine.com/bugs/view.php?id=3954)).
- Fixed [TextBlock](_TextBlock.md) hit testing issue when *IsEnabled* is false ([#3969](https://www.noesisengine.com/bugs/view.php?id=3969)).
- Fixed Setters not affecting [TextBox](_TextBox.md) in template after typing.
- Fixed Crash with Placement=Custom in [Popup](_Popup.md) or [ToolTip](_ToolTip.md).
- Fixed Visual cuts when applying gaussian effects to large elements.
- Fixed Font matching bug in *MatchFont* with multiple styles.
- Fixed Crash setting [InlineUIContainer](_InlineUIContainer.md) child to null.
- Fixed Crash in *GetCachedGlyph* ([#3995](https://www.noesisengine.com/bugs/view.php?id=3995)).
- Fixed Infinite loop with offset quad curves ([#4002](https://www.noesisengine.com/bugs/view.php?id=4002)).
- Fixed Infinite loop using [DataTemplate](_DataTemplate.md) within its own tree.
- Fixed Word wrapping in Korean now supported ([#4007](https://www.noesisengine.com/bugs/view.php?id=4007)).
- Fixed Potential infinite loops on hot-reload ([#4010](https://www.noesisengine.com/bugs/view.php?id=4010)).
- Fixed Unnecessary static resource key changes on hot-reload.
- Fixed Rare crash when renaming XAML during hot-reload ([#4200](https://www.noesisengine.com/bugs/view.php?id=4200)).
- Fixed Crash removing item from [ToolBar](_ToolBar.md) panel.
- Fixed Crash updating animation with no keyframes.
- Fixed Strokes and emoji rendering incorrectly together ([#4056](https://www.noesisengine.com/bugs/view.php?id=4056)).
- Fixed Miter limit rendering mismatch with Rive ([#3956](https://www.noesisengine.com/bugs/view.php?id=3956)).
- Fixed Multiline [TextBox](_TextBox.md) mishandling rn line endings ([#4126](https://www.noesisengine.com/bugs/view.php?id=4126)).
- Fixed Division by zero in *RayThroughBounds* ([#4131](https://www.noesisengine.com/bugs/view.php?id=4131)).
- Fixed Random circles in [Path](_Path.md) with curves and *StrokeDashArray* ([#3911](https://www.noesisengine.com/bugs/view.php?id=3911)).
- Fixed Underline misbehavior with justified text ([#3990](https://www.noesisengine.com/bugs/view.php?id=3990)).
- Fixed Implemented missing *TextDecorations* (Baseline, Strikeout, Overline) ([#4057](https://www.noesisengine.com/bugs/view.php?id=4057)).
- Fixed Android compilation issue with latest NDK ([#3930](https://www.noesisengine.com/bugs/view.php?id=3930)).
- Fixed Crash removing element before delayed *Binding* is applied ([#4097](https://www.noesisengine.com/bugs/view.php?id=4097)).
- Fixed [PathFigure](_PathFigure.md) not updating on *Segments* change ([#4073](https://www.noesisengine.com/bugs/view.php?id=4073)).
- Fixed Duplicate entries in [ItemsControl](_ItemsControl.md) after tree reattachment ([#4160](https://www.noesisengine.com/bugs/view.php?id=4160)).
- Fixed Tab navigation error from last element with no *TabIndex* ([#3587](https://www.noesisengine.com/bugs/view.php?id=3587)).
- Fixed Crash destroying *TimeManager* with active animations.
- Fixed Missing URI normalization during hot-reload ([#3765](https://www.noesisengine.com/bugs/view.php?id=3765)).
- Fixed [TextBox](_TextBox.md) allows pasting beyond *MaxLength*.
- Fixed Android crash updating *View* ([#3784](https://www.noesisengine.com/bugs/view.php?id=3784)).
- Fixed Crash in *BringIndexIntoView* during item changes ([#3907](https://www.noesisengine.com/bugs/view.php?id=3907)).
- Fixed Artifacts animating with non-uniform scales ([#4199](https://www.noesisengine.com/bugs/view.php?id=4199)).
- Fixed [BaseGridViewRowPresenter](../Gui.Controls/_BaseGridViewRowPresenter.md) creating crashing *ItemsPanel*.
- Fixed Support for accessing nested Rive inputs ([#4055](https://www.noesisengine.com/bugs/view.php?id=4055)).
- Fixed Crash when *UpdateLayout* was called while updating animations.
- Fixed Unreal Clicks not working in screen space widget components ([#3979](https://www.noesisengine.com/bugs/view.php?id=3979)).
- Fixed Unreal Added support for WinGDK and XB1 ([#3996](https://www.noesisengine.com/bugs/view.php?id=3996)).
- Fixed Unreal Missing WorldUI xaml in packaged builds ([#4112](https://www.noesisengine.com/bugs/view.php?id=4112)).
- Fixed Unreal Removed *IView::Deactivate/Activate* calls from *UNoesisInstance* ([#3908](https://www.noesisengine.com/bugs/view.php?id=3908)).
- Fixed Unreal Crash editing texture from *OnObjectPropertyChanged* ([#3702](https://www.noesisengine.com/bugs/view.php?id=3702)).
- Fixed C# Native converters like [BooleanToVisibilityConverter](_BooleanToVisibilityConverter.md) unsupported.
- Fixed Unity ";Component" [Image](_Image.md) paths not found ([#3960](https://www.noesisengine.com/bugs/view.php?id=3960)).
- Fixed Unity [AdornerLayer](_AdornerLayer.md) not exposed for [AdornerDecorator](_AdornerDecorator.md) and [ScrollContentPresenter](_ScrollContentPresenter.md).
- Fixed Unity Sprites not batching inside atlas.
- Fixed Unity HDRP samples need Custom Pass Volume ([#3909](https://www.noesisengine.com/bugs/view.php?id=3909)).
- Fixed Unity GamepadContext1..4 unmappable in Unity view ([#3966](https://www.noesisengine.com/bugs/view.php?id=3966)).
- Fixed Unity Crash on script recompile + play mode ([#4157](https://www.noesisengine.com/bugs/view.php?id=4157)).
- Fixed Unity Added support for URP compatibility mode ([#3851](https://www.noesisengine.com/bugs/view.php?id=3851)).
- Fixed Unity Heap allocation per frame when overriding base methods ([#3970](https://www.noesisengine.com/bugs/view.php?id=3970)).
- Fixed Unity Heap allocation per frame on LayoutUpdated registration ([#3053](https://www.noesisengine.com/bugs/view.php?id=3053)).
- Fixed Unity Mouse click issues in *InputSystem* (latest Unity).

# Version 3.2.7

*Released 21 Jan 2025* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Added support for UE 5.5 ([#3832](https://www.noesisengine.com/bugs/view.php?id=3832)).
- Enhancement Performance improvements getting values from dependency properties.
- Enhancement Performance improvements to [TextBlock](_TextBlock.md) layout regeneration.
- Enhancement Performance improvements to dynamic casts.
- Enhancement Improve compiler messages for delegates when lambda arguments don't match.
- Enhancement LangServer Support for [SolidColorBrush](_SolidColorBrush.md) in *CapabilityColor*.
- Enhancement LangServer Support for *ContentPropertyMetaData* in *CapabilityColor*.
- Fixed Crash setting a non compatible value in a Trigger.
- Fixed [ItemContainerGenerator](_ItemContainerGenerator.md) with unrealized containers fails to *Move* elements sometimes.
- Fixed Division by zero with TickFrequency=0 in [Slider](_Slider.md).
- Fixed Hit-test not working with orthographic cameras ([#3733](https://www.noesisengine.com/bugs/view.php?id=3733)).
- Fixed D3D12 debug layer error caused by split barriers ([#3499](https://www.noesisengine.com/bugs/view.php?id=3499)).
- Fixed Crash loading an element with a [ContextMenu](_ContextMenu.md) with IsOpen=True.
- Fixed Division by zero when [ItemsControl](_ItemsControl.md) viewport is infinity.
- Fixed OneWay binding in [ToggleButton](_ToggleButton.md) stops working after click ([#2434](https://www.noesisengine.com/bugs/view.php?id=2434), [#3009](https://www.noesisengine.com/bugs/view.php?id=3009), [#3429](https://www.noesisengine.com/bugs/view.php?id=3429)).
- Fixed VGL incorrectly assuming batch hashes were non-colliding ([#3826](https://www.noesisengine.com/bugs/view.php?id=3826)).
- Fixed [TextBlock](_TextBlock.md) not invalidated when an inline image is set ([#3846](https://www.noesisengine.com/bugs/view.php?id=3846)).
- Fixed Hot reloading does not work inside [TabControl](_TabControl.md) *ContentTemplate* ([#3853](https://www.noesisengine.com/bugs/view.php?id=3853)).
- Fixed *Collection<T>* and *ObservableCollection<T>* missing type name for each T.
- Fixed Issues with Emscriptem-3.1.73+.
- Fixed GCC compiler fixes ([#3581](https://www.noesisengine.com/bugs/view.php?id=3581)).
- Fixed Some warnings when compiling with Noesis in latest NDK ([#3856](https://www.noesisengine.com/bugs/view.php?id=3856)).
- Fixed C# Wrong signatures in some *RenderDevice* exported functions.
- Fixed C# Missing *SinglePassStereo* member in Batch struct.
- Fixed Unity Vulkan crash wrapping [TextureSource](_TextureSource.md) ([#3795](https://www.noesisengine.com/bugs/view.php?id=3795)).
- Fixed Unreal Wrong type used in *Enum* reflection code.
- Fixed Unreal Incorrectly clipping when mixing Noesis with UMG.
- Fixed Unreal Reusing last texture in *SetPatternMaterialParameters* ([#3858](https://www.noesisengine.com/bugs/view.php?id=3858)).
- Fixed App [Window](../App.ApplicationLauncher/_Window.md) not always clearing with the background color.
- Fixed App Memory issues in Wasm samples ([#3649](https://www.noesisengine.com/bugs/view.php?id=3649)).
- Fixed LangServer Crashing when a [ResourceDictionary](_ResourceDictionary.md) with *MergedDictionaries* set to a type which doesn't exist.
- Fixed LangServer Completion fails when XAML contains an expression with an embedded expression as it's parameter.
- Fixed LangServer Crashes when completing a resource key where a resource with no valid type exists.

# Version 3.2.6

*Released 22 Nov 2024* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Support binding to the *Source* property of a [RiveControl](../App.RiveBase/_RiveControl.md).
- Enhancement Rive runtime updated to Nov 13th'24.
- Enhancement Unity Unity 6 / URP - RenderGraph Support ([#3771](https://www.noesisengine.com/bugs/view.php?id=3771)).
- Enhancement Unreal Add support to bind *MediaSource* files from the ViewModel.
- Fixed Clipping problems after changes in UpdateRender order.
- Fixed [ComboBox](_ComboBox.md) can show multiple items selected at the same time ([#3334](https://www.noesisengine.com/bugs/view.php?id=3334)).
- Fixed *GetLocalValue* not returning correct value for properties with a read-only callback.
- Fixed Division by zero crash in [ItemsControl](_ItemsControl.md).
- Fixed Crash registering system font.
- Fixed Crash when rendering fonts with commands from empty glyphs ([#3808](https://www.noesisengine.com/bugs/view.php?id=3808)).
- Fixed Crash accessing destroyed [MenuItem](_MenuItem.md) when closing a [ContextMenu](_ContextMenu.md) ([#3763](https://www.noesisengine.com/bugs/view.php?id=3763)).
- Fixed Crash invalidating inherited properties ([#3770](https://www.noesisengine.com/bugs/view.php?id=3770), [#3775](https://www.noesisengine.com/bugs/view.php?id=3775), [#3791](https://www.noesisengine.com/bugs/view.php?id=3791), [#3792](https://www.noesisengine.com/bugs/view.php?id=3792)).
- Fixed Crash accessing null Keyboard handling *LostKeyboardFocus* event ([#3773](https://www.noesisengine.com/bugs/view.php?id=3773)).
- Fixed Asserts destroying some [Popup](_Popup.md) and [TextBlock](_TextBlock.md) elements ([#3783](https://www.noesisengine.com/bugs/view.php?id=3783)).
- Fixed Crash calling *ToString* if [ContentControl](_ContentControl.md) Content was pointing to the control itself.
- Fixed OneWayToSource binding to [ContextMenu](_ContextMenu.md) IsOpen causes [AdornerDecorator](_AdornerDecorator.md) errors and stop working ([#3798](https://www.noesisengine.com/bugs/view.php?id=3798)).
- Fixed C++ Data/ThemePreview sample not loading correctly on XamlPlayer ([#3658](https://www.noesisengine.com/bugs/view.php?id=3658)).
- Fixed C++ The Display Scale is not applied correctly ([#3789](https://www.noesisengine.com/bugs/view.php?id=3789)).
- Fixed Unity Crash destroying Keyboard ([#3773](https://www.noesisengine.com/bugs/view.php?id=3773)).
- Fixed Unreal Crash due to stale pointer to *FMaterialRenderProxy* in *FNoesisMaterial* ([#3373](https://www.noesisengine.com/bugs/view.php?id=3373)).
- Fixed Unreal Wrong use of ANSICHAR instead of UTF8CHAR overrides of functions.

# Version 3.2.5

*Released 28 Oct 2024* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Improved performance when playing lots of animations.
- Enhancement Reduced memory allocations by 25% in complex scenarios.
- Enhancement Added support for holes in paths during *HitTest*.
- Enhancement Implemented default style for [Window](../App.ApplicationLauncher/_Window.md) ([#3661](https://www.noesisengine.com/bugs/view.php?id=3661)).
- Feature Implemented *GUI::RegisterDefaultStyles*.
- Feature [VS Code extension](https://marketplace.visualstudio.com/items?itemName=NoesisTechnologies.noesisgui-tools) improvements:
  - Completion of Bindings ([#3178](https://www.noesisengine.com/bugs/view.php?id=3178)).
  - Completion of properties which target element names ([#3178](https://www.noesisengine.com/bugs/view.php?id=3178)).
  - Completion of TargetType, AncestorType, and DataType properties ([#3178](https://www.noesisengine.com/bugs/view.php?id=3178)).
  - Added Multi-client support.
  - Color decorator support for *Setter* values.
  - Getting into a bad connection state when switching between servers.
  - GPU memory leak in D3D11 embedded LangServer ([#3540](https://www.noesisengine.com/bugs/view.php?id=3540)).
- Fixed Missing deactivated event when closing *Win32* window.
- Fixed Emoji color incorrectly transferred to subsequent glyphs.
- Fixed Memory leak setting *FocusedElement* in the focus scope.
- Fixed Crash in [LineDecoratorBehavior](../App.Interactivity/_LineDecorationBehavior.md) when adorned [TextBlock](_TextBlock.md) not yet arranged.
- Fixed Crash when setting dash array with negative values ([#3467](https://www.noesisengine.com/bugs/view.php?id=3467)).
- Fixed Shape render not updated when changing *Stretch* property.
- Fixed ItemsControl.Items property not bound as in WPF ([#3448](https://www.noesisengine.com/bugs/view.php?id=3448)).
- Fixed Issue registering system fonts with common prefix ([#3492](https://www.noesisengine.com/bugs/view.php?id=3492)).
- Fixed Trimming artifacts in paths with local matrix set.
- Fixed [ListBox](_ListBox.md) items can be selected by receiving a *MouseUp* without a *MouseDown*.
- Fixed Support for [LocExtension](../App.ApplicationLauncher/_LocExtension.md) in *Setter* Values ([#3635](https://www.noesisengine.com/bugs/view.php?id=3635)).
- Fixed Crash opening a virtualized [ComboBox](_ComboBox.md) ([#3676](https://www.noesisengine.com/bugs/view.php?id=3676)).
- Fixed [ToolTips](_ToolTip.md) not working inside text inlines.
- Fixed [Slider](_Slider.md) *Ticks* property does not support dragging and snapping ([#3703](https://www.noesisengine.com/bugs/view.php?id=3703)).
- Fixed Crash resizing window after switching tabs ([#3600](https://www.noesisengine.com/bugs/view.php?id=3600)).
- Fixed Crash using non-updated proxies in render thread ([#3657](https://www.noesisengine.com/bugs/view.php?id=3657), [#3686](https://www.noesisengine.com/bugs/view.php?id=3686)).
- Fixed Memory leak setting DataContext=this and using a [ContentPresenter](_ContentPresenter.md) as root of the template.
- Fixed [MultiTrigger](_MultiTrigger.md) failing when several conditions use the same property.
- Fixed Frequent crashes when using [BackgroundEffectBehavior](../App.Interactivity/_BackgroundEffectBehavior.md) ([#3723](https://www.noesisengine.com/bugs/view.php?id=3723), [#3521](https://www.noesisengine.com/bugs/view.php?id=3521), [#3473](https://www.noesisengine.com/bugs/view.php?id=3473), [#3470](https://www.noesisengine.com/bugs/view.php?id=3470)).
- Fixed [Panel](_Panel.md) with DirectionalNavigation=None incorrectly receiving focus.
- Fixed Scroll position changing after focus was lost and returned ([#2717](https://www.noesisengine.com/bugs/view.php?id=2717)).
- Fixed View update enters infinite loop when adding to a [Panel](_Panel.md) the same element twice ([#3742](https://www.noesisengine.com/bugs/view.php?id=3742)).
- Fixed Crash measuring unconnected [Grid](_Grid.md) with a *SharedSizeGroup* ([#3741](https://www.noesisengine.com/bugs/view.php?id=3741)).
- Fixed [Slider](_Slider.md) with not positive min value slightly fluctuates after decreasing min value ([#3663](https://www.noesisengine.com/bugs/view.php?id=3663)).
- Fixed [Visual](_Visual.md) child of adorner is not rendered ([#3549](https://www.noesisengine.com/bugs/view.php?id=3549)).
- Fixed Extend [GamepadTrigger](../App.Interactivity/_GamepadTrigger.md) to include option to handle events ([#2577](https://www.noesisengine.com/bugs/view.php?id=2577)).
- Fixed Expose connected Visual in *IScrollInfo* to support custom *ScrollInfoAdapter* ([#3599](https://www.noesisengine.com/bugs/view.php?id=3599)).
- Fixed Unreal Improvements to input and focus handling ([#3457](https://www.noesisengine.com/bugs/view.php?id=3457)).
- Fixed Unreal Issue with wrong capitalization of bindings in non-editor builds.
- Fixed Unity Crash with corrupted font streams after playing ([#3472](https://www.noesisengine.com/bugs/view.php?id=3472), [#3554](https://www.noesisengine.com/bugs/view.php?id=3554)).
- Fixed Unity Elements with IsHitTestVisible=False are blocking interaction with the 3D world ([#3734](https://www.noesisengine.com/bugs/view.php?id=3734), [#3476](https://www.noesisengine.com/bugs/view.php?id=3476)).
- Fixed Unity Added "Clear Stencil" property to View ([#3665](https://www.noesisengine.com/bugs/view.php?id=3665)).
- Fixed C# [GoToStateAction](../App.Interactivity/_GoToStateAction.md) creating circular references and leaks.
- Fixed C# *FontWeight* broken after upgrading to 3.2.4 ([#3483](https://www.noesisengine.com/bugs/view.php?id=3483)).
- Fixed C# Could not load file or assembly 'SystemFonts' ([#3605](https://www.noesisengine.com/bugs/view.php?id=3605)).
- Fixed C# Samples showing invalid license message at start.
- Fixed C# StencilMode enum is incomplete ([#3564](https://www.noesisengine.com/bugs/view.php?id=3564)).
- Fixed C# Matrix not invertible issue ([#3607](https://www.noesisengine.com/bugs/view.php?id=3607)).

# Version 3.2.4

*Released 20 Jun 2024* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature Licenses are no longer necessary for [evaluations](Licensing.md#evaluation) lasting up to 10 minutes per session.
- Feature Implemented support for [Variable Fonts](TextTutorial.md#variable-fonts).
- Feature Support [VisualBrush](_VisualBrush.md) as an *OpacityMask* ([#2330](https://www.noesisengine.com/bugs/view.php?id=2330), [#1316](https://www.noesisengine.com/bugs/view.php?id=1316), [#711](https://www.noesisengine.com/bugs/view.php?id=711), [#650](https://www.noesisengine.com/bugs/view.php?id=650)).
- Enhancement Added support for Unity 2023.1+.
- Enhancement Added support for UE 5.4 ([#3244](https://www.noesisengine.com/bugs/view.php?id=3244)).
- Enhancement Added support for Android NDK r26d.
- Enhancement Added support for Emscripten 3.1.61 ([#3278](https://www.noesisengine.com/bugs/view.php?id=3278)).
- Enhancement Optimized page allocations in all GPU renderers.
- Enhancement PSO optimizations in Vulkan renderer ([#3296](https://www.noesisengine.com/bugs/view.php?id=3296)).
- Enhancement Split barriers used in D3D12 renderer.
- Enhancement *Converter* and *ConverterParameter* properties added to [LocExtension](../App.ApplicationLauncher/_LocExtension.md) ([#3210](https://www.noesisengine.com/bugs/view.php?id=3210)).
- Enhancement LangServer Added support [StaticResource](_StaticResourceExtension.md) and [DynamicResource](_DynamicResourceExtension.md) ([#3178](https://www.noesisengine.com/bugs/view.php?id=3178)).
- Fixed [LocExtension](../App.ApplicationLauncher/_LocExtension.md) only supported in [FrameworkElement](_FrameworkElement.md) element properties ([#2847](https://www.noesisengine.com/bugs/view.php?id=2847)).
- Fixed Crash using *ImageSourceConverter* from a binding ([#3136](https://www.noesisengine.com/bugs/view.php?id=3136)).
- Fixed Low performance when using [BackgroundEffectBehavior](../App.Interactivity/_BackgroundEffectBehavior.md) on many elements ([#3161](https://www.noesisengine.com/bugs/view.php?id=3161)).
- Fixed *Unloaded* event not invoked for inlines added through code ([#2915](https://www.noesisengine.com/bugs/view.php?id=2915)).
- Fixed [ListBox](_ListBox.md) and [ListView](../Gui.Controls/_ListView.md) not receiving mouse events when hovering outside the items.
- Fixed Boxing init crashing when multithreading disabled.
- Fixed Crash using [VisualBrush](_VisualBrush.md) inside 3D transformed elements.
- Fixed Incorrect bounds for horizontal and vertical line paths.
- Fixed Cannot set *RenderTransform* to a *MatrixTransform* from code ([#3090](https://www.noesisengine.com/bugs/view.php?id=3090)).
- Fixed Crash in [RiveControl](../App.RiveBase/_RiveControl.md) when changing *Source* dynamically.
- Fixed Added define to allow using the original *Rive* asset names ([#3235](https://www.noesisengine.com/bugs/view.php?id=3235)).
- Fixed Crash in [TabControl](_TabControl.md) related to key handling ([#3239](https://www.noesisengine.com/bugs/view.php?id=3239)).
- Fixed Crash using *DrawGeometry* with null geometry ([#3249](https://www.noesisengine.com/bugs/view.php?id=3249)).
- Fixed Value returned by *IValueConverter* not converted to target type ([#1376](https://www.noesisengine.com/bugs/view.php?id=1376)).
- Fixed Error unbinding buffer in GL renderer.
- Fixed Directional navigation not working as expected in RTL scenarios.
- Fixed Shift tab navigation moving focus to parent control instead of children.
- Fixed Binding *StringFormat* does not support brace escaping ([#3275](https://www.noesisengine.com/bugs/view.php?id=3275)).
- Fixed Crash filling effect pyramid ([#3245](https://www.noesisengine.com/bugs/view.php?id=3245)).
- Fixed [ToolTip](_ToolTip.md) is not affected by *WorldSpaceUI* scale ([#2721](https://www.noesisengine.com/bugs/view.php?id=2721)).
- Fixed *Width="Auto"* not working in [Expander](_Expander.md) when [UniformGrid](_UniformGrid.md) is a child ([#3247](https://www.noesisengine.com/bugs/view.php?id=3247)).
- Fixed Offscreen jittering ([#3277](https://www.noesisengine.com/bugs/view.php?id=3277)).
- Fixed Can't set *MinHeight* thumb of [ScrollBar](_ScrollBar.md) ([#3224](https://www.noesisengine.com/bugs/view.php?id=3224)).
- Fixed *CharacterSpacing* *Text* property is not inherited ([#3301](https://www.noesisengine.com/bugs/view.php?id=3301)).
- Fixed XAML parser reporting incorrect (line,column) for errors inside markups.
- Fixed XYFocus was taking over expected directional navigation when defined in a parent control.
- Fixed [AdornerLayer](_AdornerLayer.md) incorrectly applying transform 3D to itself.
- Fixed Division by zero in [Grid](_Grid.md) with 0\* column and span elements.
- Fixed [RangeBase](_RangeBase.md) can assert sometimes initializing *Minimum*, *Maximum* and *Value* properties.
- Fixed XDisplay bug invoking *Xutf8LookupString* ([#3327](https://www.noesisengine.com/bugs/view.php?id=3327)).
- Fixed Error rendering minimized windows in GL ([#3295](https://www.noesisengine.com/bugs/view.php?id=3295)).
- Fixed KeyConverter does not support Oem keys.
- Fixed [TreeView](_TreeView.md) not updating *IsSelectionActive* property.
- Fixed Added validation to *AccelerationRatio* and *DecelerationRatio* properties of [Timeline](../Gui.Animation/_Timeline.md).
- Fixed Support defining enum values in dictionaries ([#2452](https://www.noesisengine.com/bugs/view.php?id=2452)).
- Fixed Can't disable [ToolTip](_ToolTip.md) animation ([#1142](https://www.noesisengine.com/bugs/view.php?id=1142)).
- Fixed Width of element inside [VirtualizingStackPanel](_VirtualizingStackPanel.md) not updated correctly ([#2700](https://www.noesisengine.com/bugs/view.php?id=2700)).
- Fixed Occasional crash inside *MultiDelegate* *Remove* and *Invoke* ([#3087](https://www.noesisengine.com/bugs/view.php?id=3087)).
- Fixed Crash when re-evaluating style triggers while *View* being destroyed ([#3349](https://www.noesisengine.com/bugs/view.php?id=3349)).
- Fixed [TextBlock](_TextBlock.md) is limited to a text length of 65536 glyphs ([#3253](https://www.noesisengine.com/bugs/view.php?id=3253) [#3132](https://www.noesisengine.com/bugs/view.php?id=3132)).
- Fixed Incorrect behavior of inline text when using special characters ([#3166](https://www.noesisengine.com/bugs/view.php?id=3166)).
- Fixed *DeleteSampler* assert in GL renderer ([#3294](https://www.noesisengine.com/bugs/view.php?id=3294)).
- Fixed Text Display breaks in Xbox Series ([#3336](https://www.noesisengine.com/bugs/view.php?id=3336) [#3351](https://www.noesisengine.com/bugs/view.php?id=3351)).
- Fixed Makefile fails on Linux due to backslashes in paths ([#3241](https://www.noesisengine.com/bugs/view.php?id=3241)).
- Fixed Crash accessing *Keyboard* on disconnected [TabItem](_TabItem.md) ([#3097](https://www.noesisengine.com/bugs/view.php?id=3097)).
- Fixed [TextBox](_TextBox.md) caret incorrectly rendered in world space UI ([#3407](https://www.noesisengine.com/bugs/view.php?id=3407)).
- Fixed [GamepadTrigger](../App.Interactivity/_GamepadTrigger.md) not passing event args as parameter to *InvokeActions*.
- Fixed Incorrect rendering using negative strokes.
- Fixed Unreal WorldUI components fail to render if separate *Translucency* not enabled ([#3050](https://www.noesisengine.com/bugs/view.php?id=3050)).
- Fixed Unreal Stereo WorldUI improvements.
- Fixed Unreal Streamable texture support ([#2908](https://www.noesisengine.com/bugs/view.php?id=2908), [#3057](https://www.noesisengine.com/bugs/view.php?id=3057)).
- Fixed Unreal Prevent textures from being deleted before *InitShaderResourceTexture* executes on the rendering thread.
- Fixed Unreal Fixed crash initializing the *RenderDevice* when the app cannot render.
- Fixed Unreal *NoesisGrabBackgroundImage* optimized and clearing surface alpha not longer needed ([#3214](https://www.noesisengine.com/bugs/view.php?id=3214)).
- Fixed Unreal High render target memory size with many small widgets ([#3302](https://www.noesisengine.com/bugs/view.php?id=3302)).
- Fixed Unity *KeyDown* and *PreviewKeyDown* not firing for *KeyCode* Tilde '~' ([#3279](https://www.noesisengine.com/bugs/view.php?id=3279)).
- Fixed Unity Crashing due to *CapabilityCompletion* caching types for use with collection properties ([#3095](https://www.noesisengine.com/bugs/view.php?id=3095)).
- Fixed Unity Log unregistering after exiting Play Mode in Editor.
- Fixed Unity Native type 'BaseObject' is not registered ([#2638](https://www.noesisengine.com/bugs/view.php?id=2638)).
- Fixed Unity Loading files using "*pack://application:,,,*" is broken ([#3304](https://www.noesisengine.com/bugs/view.php?id=3304), [#3320](https://www.noesisengine.com/bugs/view.php?id=3320)).
- Fixed Unity Opacity issues in Nintendo Switch.
- Fixed Unity Crash on PS5 when exceeding the internal buffer used for GPU commands ([#3282](https://www.noesisengine.com/bugs/view.php?id=3282)).
- Fixed Unity Crash on assembly reload when overriding DP metadata ([#3243](https://www.noesisengine.com/bugs/view.php?id=3243)).
- Fixed Unity Added support for private text content to *TouchScreenKeyboard* ([#3263](https://www.noesisengine.com/bugs/view.php?id=3263)).
- Fixed Unity Crashes when exception was thrown while creating managed instances ([#3243](https://www.noesisengine.com/bugs/view.php?id=3243)).
- Fixed Unity Binding errors during first time ([#3154](https://www.noesisengine.com/bugs/view.php?id=3154)).
- Fixed C# Cannot convert a string to *Noesis.Size* using *TypeConverter* ([#3091](https://www.noesisengine.com/bugs/view.php?id=3091)).
- Fixed C# Added missing flags to DeviceCaps.
- Fixed C# Error in WPF [LocExtension](../App.ApplicationLauncher/_LocExtension.md) during template load ([#3128](https://www.noesisengine.com/bugs/view.php?id=3128)).
- Fixed C# Parsing special character '°' with *XamlReader* fails ([#3311](https://www.noesisengine.com/bugs/view.php?id=3311)).

# Version 3.2.3

*Released 9 Feb 2024* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Implemented support for [Custom Language Servers](LanguageServer.md#custom-language-server).
- Enhancement Added XAML Preview support to Unity and Unreal in [Language Server](LanguageServer.md).
- Enhancement Support for *Assembly* and *Scheme* [providers](ProvidersTutorial.md#scheme-assemby-providers).
- Enhancement Added internal fallback font ([#2412](https://www.noesisengine.com/bugs/view.php?id=2412)).
- Enhancement Added support for *TwoWay* bindings in Rive inputs ([#2654](https://www.noesisengine.com/bugs/view.php?id=2654)).
- Enhancement Better *Line-breaking* algorithm with Japanese starter (CJ) chars.
- Enhancement Added *Template* support to [LocExtension](../App.ApplicationLauncher/_LocExtension.md) ([#2710](https://www.noesisengine.com/bugs/view.php?id=2710)).
- Enhancement Implemented [LineDecorationBehavior](../App.Interactivity/_LineDecorationBehavior.md) extension for [TextBlock](_TextBlock.md) ([#2658](https://www.noesisengine.com/bugs/view.php?id=2658)).
- Enhancement Reflection improvements to *Point* and *Rect* ([#2729](https://www.noesisengine.com/bugs/view.php?id=2729)).
- Enhancement Implemented suport for *Images* and *Texts* in [RiveControl](../App.RiveBase/_RiveControl.md) ([#2562](https://www.noesisengine.com/bugs/view.php?id=2562) [#2563](https://www.noesisengine.com/bugs/view.php?id=2563) [#2709](https://www.noesisengine.com/bugs/view.php?id=2709) [#2708](https://www.noesisengine.com/bugs/view.php?id=2708)).
- Enhancement Added support for [XY Focus Navigation](ExtensionsTutorial.md#xy-focus-navigation) ([#2406](https://www.noesisengine.com/bugs/view.php?id=2406)).
- Enhancement Significant performance improvements to [Delegates](CppArchitectureGuide.md#delegates).
- Enhancement Improvements to float round-trip conversions.
- Enhancement Performance improvements when using reflection to register types.
- Enhancement Added support for interacting with [Rive text](../App.RiveBase/_RiveRun.md) ([#2709](https://www.noesisengine.com/bugs/view.php?id=2709)).
- Enhancement Implemented [InvokeCommandAction](../App.Interactivity/_InvokeCommandAction.md) parameter passing ([#2723](https://www.noesisengine.com/bugs/view.php?id=2723)).
- Enhancement Unity Added *DefaultExecutionOrder* to *NoesisWorldUI* ([#2586](https://www.noesisengine.com/bugs/view.php?id=2586)).
- Enhancement Unity *NoesisWorldUI* not recreating state on GameObject.Enable/Disable ([#2935](https://www.noesisengine.com/bugs/view.php?id=2935)).
- Enhancement Unity Improvements to Mouse tracking in VR ([#2837](https://www.noesisengine.com/bugs/view.php?id=2837)).
- Enhancement Unreal Added support for gamma correction.
- Enhancement Unreal Added support for *TargetType* to RichText Style tags ([#3068](https://www.noesisengine.com/bugs/view.php?id=3068) [#3051](https://www.noesisengine.com/bugs/view.php?id=3051) [#3048](https://www.noesisengine.com/bugs/view.php?id=3048)).
- Enhancement Unreal Added the ability to extend *RichText* tags using a callback ([#3067](https://www.noesisengine.com/bugs/view.php?id=3067) [#3001](https://www.noesisengine.com/bugs/view.php?id=3001)).
- Enhancement Unreal Added *NoesisNotifyMapPropertyChanged*.
- Enhancement App Implemented support for capturing with [RenderDoc](https://renderdoc.org/) using F10.
- Fixed [ContextMenu](_ContextMenu.md) calling *CanExecute* on menu items before connecting to the tree.
- Fixed Crash in GL renderer when *ARB\_uniform\_buffer\_object* not available ([#2728](https://www.noesisengine.com/bugs/view.php?id=2728)).
- Fixed [Run](_Run.md) background not rendered when *Foreground* is transparent.
- Fixed Crash when disconnecting a [Visual](_Visual.md) with null children.
- Fixed Wrong viewport set when using horizontal [VirtualizingStackPanel](_VirtualizingStackPanel.md).
- Fixed [InlineUIContainer](_InlineUIContainer.md) child stays connected to the view when removed from container.
- Fixed Read access violation in *D3D12RenderDevice::UploadUniforms* ([#2924](https://www.noesisengine.com/bugs/view.php?id=2924)).
- Fixed Incorrect tiling of [ImageBrushes](_ImageBrush.md) with *Stretch=None* when using DPI scale.
- Fixed Warning that variable 'cursor' in *QueryCursorEventArgs* is uninitialized ([#2979](https://www.noesisengine.com/bugs/view.php?id=2979)).
- Fixed Selected item in [ComboBox](_ComboBox.md) not updating display text when content changes ([#2985](https://www.noesisengine.com/bugs/view.php?id=2985)).
- Fixed Crash calling *GetRangeBounds* in [TextBox](_TextBox.md) with debug pink template ([#2980](https://www.noesisengine.com/bugs/view.php?id=2980)).
- Fixed Crash when destroying a binding set in a *DataContext* property.
- Fixed *EnumConverters* are now case-insensitive ([#3006](https://www.noesisengine.com/bugs/view.php?id=3006)).
- Fixed Using Opacity > 1 burns colors to white ([#2756](https://www.noesisengine.com/bugs/view.php?id=2756)).
- Fixed Allocating too much memory for system fonts ([#2946](https://www.noesisengine.com/bugs/view.php?id=2946)).
- Fixed '-Wno-maybe-uninitialized' is no longer needed when compiling with GCC ([#3007](https://www.noesisengine.com/bugs/view.php?id=3007)).
- Fixed Text extensions can't be used on *Inline* elements.
- Fixed Namespace processing in [Language Server](LanguageServer.md) ([#2773](https://www.noesisengine.com/bugs/view.php?id=2773)).
- Fixed AGC renderer crashing on Asian languages ([#2738](https://www.noesisengine.com/bugs/view.php?id=2738)).
- Fixed Event raising incorrect errors when trying to remove non-existent handler ([#3033](https://www.noesisengine.com/bugs/view.php?id=3033)).
- Fixed Crash when using complex [Path](_Path.md) tags ([#2706](https://www.noesisengine.com/bugs/view.php?id=2706)).
- Fixed Crash when having a [Popup](_Popup.md) with *IsOpen=True* in a template ([#2849](https://www.noesisengine.com/bugs/view.php?id=2849)).
- Fixed [TextBox](_TextBox.md) using graphemes to handle caret index and selection ([#2748](https://www.noesisengine.com/bugs/view.php?id=2748)).
- Fixed Empty [InlineUIContainer](_InlineUIContainer.md) not being correctly represented in [FormattedText](_FormattedText.md) ([#2856](https://www.noesisengine.com/bugs/view.php?id=2856)).
- Fixed Offscreen text blurriness ([#2965](https://www.noesisengine.com/bugs/view.php?id=2965)).
- Fixed Crash when [ToolTip](_ToolTip.md) gets destroyed while closing it ([#2840](https://www.noesisengine.com/bugs/view.php?id=2840)).
- Fixed Crash when some event handlers are kept alive during shutdown ([#2840](https://www.noesisengine.com/bugs/view.php?id=2840)).
- Fixed Crash when [Trigger](_Trigger.md) destroyed while invoking actions.
- Fixed Crash accessing offscreen textures when using multiple views.
- Fixed Unreal FreeType compilation issues in PS5 ([#2735](https://www.noesisengine.com/bugs/view.php?id=2735) [#2573](https://www.noesisengine.com/bugs/view.php?id=2573) [#2585](https://www.noesisengine.com/bugs/view.php?id=2585) [#3016](https://www.noesisengine.com/bugs/view.php?id=3016) [#3042](https://www.noesisengine.com/bugs/view.php?id=3042)).
- Fixed Unreal Mouse enhanced input actions not triggering ([#2703](https://www.noesisengine.com/bugs/view.php?id=2703)).
- Fixed Unreal Race condition involving *GViewRect* and *GViewProjectionMatrix*.
- Fixed Unreal Crash when importing XAML files ([#2789](https://www.noesisengine.com/bugs/view.php?id=2789)).
- Fixed Unreal Invalid metadata default value type using Unreal materials.
- Fixed Unreal Renderer crash when resizing the level viewport ([#3041](https://www.noesisengine.com/bugs/view.php?id=3041)).
- Fixed Unreal Crash when resizing the Viewport with the D3D11 render back ([#2918](https://www.noesisengine.com/bugs/view.php?id=2918)).
- Fixed Unreal Unreal 5.3 Plugin fails to build on macOS ([#3016](https://www.noesisengine.com/bugs/view.php?id=3016)).
- Fixed Unreal Unreal crashes when trying to use the Unreal 5.3 plugin on macOS ([#3017](https://www.noesisengine.com/bugs/view.php?id=3017)).
- Fixed Unreal Documentation referencing deprecated *PlayerMappableInputConfig* for 5.3 ([#2919](https://www.noesisengine.com/bugs/view.php?id=2919)).
- Fixed Unreal Crash with empty XAMLs.
- Fixed Unity Issues with *MouseOver* Raycast ([#2837](https://www.noesisengine.com/bugs/view.php?id=2837)).
- Fixed Unity Wrapped textures missing transition barriers ([#2800](https://www.noesisengine.com/bugs/view.php?id=2800)).
- Fixed Unity Crash when using [ImageBrush](_ImageBrush.md) RenderTexture with D3D12 ([#2776](https://www.noesisengine.com/bugs/view.php?id=2776)).
- Fixed Unity Crash while quitting app ([#2872](https://www.noesisengine.com/bugs/view.php?id=2872)).
- Fixed Unity Ambiguous symbol when compiling Interaction.cpp in Unity builds ([#2999](https://www.noesisengine.com/bugs/view.php?id=2999)).
- Fixed Unity World UI responding to mouse events when cursor hidden and locked ([#2936](https://www.noesisengine.com/bugs/view.php?id=2936)).
- Fixed C# Crash using the *BindingCollection* of a [MultiBinding](_MultiBinding.md) ([#2693](https://www.noesisengine.com/bugs/view.php?id=2693)).
- Fixed C# Noesis.GUI NuGet missing a natives folder for osx-arm64 ([#2722](https://www.noesisengine.com/bugs/view.php?id=2722)).
- Fixed C# InvalidOperationException when using *Type* properties in C# ([#3040](https://www.noesisengine.com/bugs/view.php?id=3040)).
- Fixed C# Incorrect *Matrix.HasInverse* implementation ([#3063](https://www.noesisengine.com/bugs/view.php?id=3063)).

# Version 3.2.2

*Released 29 Sept 2023* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Implemented [Shader Compiler](ApplicationTutorial.md#shader-compiler) in the [App Framework](ApplicationTutorial.md).
- Enhancement New [BrushShaders](https://github.com/Noesis/Tutorials/tree/master/Samples/BrushShaders) example.
- Enhancement Implemented [FocusManager](_FocusManager.md) ([#811](https://www.noesisengine.com/bugs/view.php?id=811), [#1982](https://www.noesisengine.com/bugs/view.php?id=1982)).
- Enhancement macOS deployment target raised to 10.13.
- Enhancement iOS/tvOS deployment target raised to 11.0.
- Enhancement Implemented a SVG parser (*SVG.h*). Used by *XamlPlayer* for now.
- Enhancement Added support for .svg files to *XamlPlayer*.
- Enhancement New offscreen algorithm with more quality when using opacities or effects in 3D.
- Enhancement Improvements on [VisualBrush](_VisualBrush.md) atlas allocations when sharing source visual.
- Enhancement C++ Added *TranslatePoint* method to [UIElement](_UIElement.md) in C++ ([#2668](https://www.noesisengine.com/bugs/view.php?id=2668))
- Enhancement C++ [Uri](../Gui.Providers/_Uri.md) performance and conformance improvements.
- Enhancement Unity Added support for VR in URP versions previous to 14.0.
- Enhancement Unity Added support for PS5 NGGC (Next Gen Graphics Context).
- Enhancement Unreal Added support for UE 5.3 ([#2678](https://www.noesisengine.com/bugs/view.php?id=2678)).
- Enhancement Unreal Allow sampling of *SceneTextures* in *PostProcess* materials used in XAMLs.
- Enhancement Unreal Added support for *MediaTextures* ([#2648](https://www.noesisengine.com/bugs/view.php?id=2648)).
- Enhancement Unreal PixelDepthBias added to *NoesisView*.
- Fixed Wrong *Arc* command's *SweepDirection* in *PathFigureCollection* converter ([#2661](https://www.noesisengine.com/bugs/view.php?id=2661)).
- Fixed [ComboBox](_ComboBox.md) dropdown not updating its position when moving the control in 3D ([#2570](https://www.noesisengine.com/bugs/view.php?id=2570)).
- Fixed Bindings don't work in [ToolTip](_ToolTip.md) after opening it a second time ([#1977](https://www.noesisengine.com/bugs/view.php?id=1977)).
- Fixed [ComboBox](_ComboBox.md) drop down entries in wrong world space position ([#2570](https://www.noesisengine.com/bugs/view.php?id=2570)).
- Fixed Incorrectly breaking glyphs belonging to the same grapheme ([#2604](https://www.noesisengine.com/bugs/view.php?id=2604)).
- Fixed Incorrect nested *OpacityMask* results ([#2594](https://www.noesisengine.com/bugs/view.php?id=2594)).
- Fixed Improve error message when binding read-only property ([#2602](https://www.noesisengine.com/bugs/view.php?id=2602)).
- Fixed Crash when setting *Stretch* to *Fill* on [Path](_Path.md) with [BackgroundEffectBehavior](../App.Interactivity/_BackgroundEffectBehavior.md) ([#2608](https://www.noesisengine.com/bugs/view.php?id=2608)).
- Fixed Issues with [ScrollViewer](_ScrollViewer.md) and keyboard focus ([#2597](https://www.noesisengine.com/bugs/view.php?id=2597)).
- Fixed Directional focus can't be moved to controls inside [ItemsControl](_ItemsControl.md) items ([#2599](https://www.noesisengine.com/bugs/view.php?id=2599)).
- Fixed Button logic handling *Enter* key has some problems ([#2605](https://www.noesisengine.com/bugs/view.php?id=2605)).
- Fixed Crash when using dash patterns with total zero length.
- Fixed Miter join ignored sometimes.
- Fixed Added *ResolvedSource* property to [BindingExpression](_BindingExpression.md).
- Fixed Dashed segments using *StartLineCap* and *EndLineCap* for first and last segment.
- Fixed Crash clicking an element with a wrong gesture set in XAML.
- Fixed Crash compiling VR shaders ([#2600](https://www.noesisengine.com/bugs/view.php?id=2600)).
- Fixed Improve [PropertyPath](_PropertyPath.md) error messages for boxed values ([#2627](https://www.noesisengine.com/bugs/view.php?id=2627)).
- Fixed Missing converter for PathFigureCollection ([#2647](https://www.noesisengine.com/bugs/view.php?id=2647)).
- Fixed Unnecessary offset in [BackgroundEffectBehavior](../App.Interactivity/_BackgroundEffectBehavior.md) ([#2578](https://www.noesisengine.com/bugs/view.php?id=2578)).
- Fixed [MenuItem](_MenuItem.md) *IsChecked* binding not working properly ([#2656](https://www.noesisengine.com/bugs/view.php?id=2656)).
- Fixed Cannot bind to the properties of a [TimeSpan](../Gui.Animation/_TimeSpan.md) ([#2657](https://www.noesisengine.com/bugs/view.php?id=2657)).
- Fixed Crashes on some AMD graphics cards ([#2659](https://www.noesisengine.com/bugs/view.php?id=2659)).
- Fixed NVN renderer issue with sync objects being moved in memory.
- Fixed Gamepad *Cancel* not bubbling up sometimes when a control had focus.
- Fixed Occasional crash when XAML reloads ([#2672](https://www.noesisengine.com/bugs/view.php?id=2672)).
- Fixed Crash parsing invalid XAML ([#2624](https://www.noesisengine.com/bugs/view.php?id=2624)).
- Fixed Crash on keyboard input ([#2682](https://www.noesisengine.com/bugs/view.php?id=2682)).
- Fixed Improved handling of VR shaders in GL renderer ([#2659](https://www.noesisengine.com/bugs/view.php?id=2659) [#2673](https://www.noesisengine.com/bugs/view.php?id=2673)).
- Fixed [LocExtension](../App.ApplicationLauncher/_LocExtension.md) not working at design time in Blend.
- Fixed [BrushShader](_BrushShader.md) textures not processed with unset constant buffer ([#2538](https://www.noesisengine.com/bugs/view.php?id=2538)).
- Fixed Compile errors with Visual Studio 2022 v17.7.0 ([#2663](https://www.noesisengine.com/bugs/view.php?id=2663)).
- Fixed Crash in XAML parser setting a reflection property on non-compatible type ([#2695](https://www.noesisengine.com/bugs/view.php?id=2695)).
- Fixed [ControlStoryboardAction](../App.Interactivity/_ControlStoryboardAction.md) inside [ControlTemplates](_ControlTemplate.md) only works for one instance ([#2653](https://www.noesisengine.com/bugs/view.php?id=2653)).
- Fixed [Storyboard](../Gui.Animation/_Storyboard.md) *Completed* event triggered for all instances of a template ([#2052](https://www.noesisengine.com/bugs/view.php?id=2052), [#2634](https://www.noesisengine.com/bugs/view.php?id=2634)).
- Fixed Stack overflow setting *DataContext* in the constructor of a template element ([#2527](https://www.noesisengine.com/bugs/view.php?id=2527)).
- Fixed Crash inspecting element with a templated parent binding in a style ([#2620](https://www.noesisengine.com/bugs/view.php?id=2620)).
- Fixed Cannot bind to the Properties of a [TimeSpan](../Gui.Animation/_TimeSpan.md) ([#2657](https://www.noesisengine.com/bugs/view.php?id=2657)).
- Fixed BeginInvoke() not working for [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md) inherited class ([#2522](https://www.noesisengine.com/bugs/view.php?id=2522))
- Fixed Unity [EventTrigger](_EventTrigger.md) failing with *NullReferenceException* when event not found ([#2671](https://www.noesisengine.com/bugs/view.php?id=2671)).
- Fixed Unity Static values 'UnsetValue' and 'DoNothing' stay disposed after assembly reload.
- Fixed Unity Exception in *Extend* when using signed enum values ([#2616](https://www.noesisengine.com/bugs/view.php?id=2616)).
- Fixed Unity [BackgroundEffectBehavior](../App.Interactivity/_BackgroundEffectBehavior.md) being invalidated per frame ([#2615](https://www.noesisengine.com/bugs/view.php?id=2615)).
- Fixed Unity Sprite atlas size variants not supported ([#2591](https://www.noesisengine.com/bugs/view.php?id=2591)).
- Fixed Unity Crash during assembly reload ([#2625](https://www.noesisengine.com/bugs/view.php?id=2625)).
- Fixed Unity [TextBox](_TextBox.md) and [PasswordBox](_PasswordBox.md) not receiving focus in WebGL ([#2609](https://www.noesisengine.com/bugs/view.php?id=2609)).
- Fixed Unity DllNotFoundException for standalone builds on macOS ([#2666](https://www.noesisengine.com/bugs/view.php?id=2666)).
- Fixed Unity Crash closing macOS standalone in development builds.
- Fixed Unity Compiler error when builtin VR module not enabled.
- Fixed Unity Performance improvements of [VisualTreeHelper](_VisualTreeHelper.md) *HitTest* version with callbacks ([#2677](https://www.noesisengine.com/bugs/view.php?id=2677)).
- Fixed Unreal Crash when using WorldUI component and plugin content not present ([#2592](https://www.noesisengine.com/bugs/view.php?id=2592)).
- Fixed Unreal Noesis::Ptr types not supported as a *Key* value for *TMap* ([#2607](https://www.noesisengine.com/bugs/view.php?id=2607)).
- Fixed Unreal Set with *NotifyChanged* node not working with *Text* properties ([#2613](https://www.noesisengine.com/bugs/view.php?id=2613)).
- Fixed Unreal ViewUniformBuffer being destroyed while still in use.
- Fixed Unreal Delegate *UFunction* causing trouble with garbage collection.
- Fixed Unreal Crash when multiple delegates are used ([#2649](https://www.noesisengine.com/bugs/view.php?id=2649)).
- Fixed Unreal Different Colors in Unreal World UI ([#2642](https://www.noesisengine.com/bugs/view.php?id=2642)).
- Fixed Unreal Crash when *ViewportClient* is null ([#2640](https://www.noesisengine.com/bugs/view.php?id=2640)).
- Fixed Unreal Crash in *NativePaint* when stopping PIE ([#2606](https://www.noesisengine.com/bugs/view.php?id=2606)).
- Fixed Unreal Crash when editing a material while using WorldUI.
- Fixed Unreal Invalid *UMaterialInterface* pointers in *NoesisTypeClasses* ([#2641](https://www.noesisengine.com/bugs/view.php?id=2641)).
- Fixed Unreal Crash when a material was referenced in the application resources ([#2651](https://www.noesisengine.com/bugs/view.php?id=2651)).
- Fixed Unreal Crash when refreshing a *NoesisView* preview.
- Fixed Unreal Memory leak in *NoesisRenderDevice* ([#2699](https://www.noesisengine.com/bugs/view.php?id=2699)).
- Fixed Unreal Crash when closing the application with Alt+F4 ([#2701](https://www.noesisengine.com/bugs/view.php?id=2701)).

# Version 3.2.1

*Released 9 May 2023* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature Visual Studio 2022 Project Templates for [Unity](https://marketplace.visualstudio.com/items?itemName=NoesisTechnologies.noesistemplates2022) and [C#](https://marketplace.visualstudio.com/items?itemName=NoesisTechnologies.NoesisCSharpProjectTemplates) ([#2584](https://www.noesisengine.com/bugs/view.php?id=2584) [#2524](https://www.noesisengine.com/bugs/view.php?id=2524) [#2221](https://www.noesisengine.com/bugs/view.php?id=2221)).
- Enhancement Updated to latest Sony SDKs ([#2541](https://www.noesisengine.com/bugs/view.php?id=2541)).
- Enhancement New [Linear Rendering](LinearRenderingTutorial.md) tutorial.
- Enhancement Improved the positioning of XAML document errors.
- Enhancement Added support for sys:Byte and sys:SByte.
- Enhancement Added *R*, *G*, *B*, *A*, *ScR*, *ScG*, *ScB*, *ScA* properties to *Color*.
- Enhancement Support for *Color*, *Thickness* and *CornerRadius* in dictionaries.
- Enhancement XamlPlayer clearing errors when hot-reloading.
- Enhancement C# Updated ApplicationTutorial sample to new design.
- Enhancement Unity Implement support for Single-Pass stereo rendering on Android ([#2568](https://www.noesisengine.com/bugs/view.php?id=2568)).
- Enhancement Unity Vulkan interception fixed for Android.
- Enhancement Unreal Support for texture [Material parameters](UnrealTutorial.md#materials) ([#2547](https://www.noesisengine.com/bugs/view.php?id=2547)).
- Enhancement Unreal Added linear *Point4D* properties for vector [Material parameters](UnrealTutorial.md#materials).
- Enhancement Unreal Added support for *ETextFlowDirection* in DataContexts.
- Enhancement Unreal Expose delegates to [DataEventTriggers](../App.Interactivity/_DataEventTrigger.md) ([#2575](https://www.noesisengine.com/bugs/view.php?id=2575)).
- Enhancement Unreal EnhancedInput plugin enabled by default.
- Enhancement Unreal C# Added Arabic language to Localization sample.
- Enhancement LangServer Added color suggestions for *Color* properties ([#2556](https://www.noesisengine.com/bugs/view.php?id=2556)).
- Enhancement LangServer Implemented full support for color decorators on node attribute properties ([#2566](https://www.noesisengine.com/bugs/view.php?id=2566)).
- Enhancement LangServer Added support for *Nullable* types ([#2555](https://www.noesisengine.com/bugs/view.php?id=2555)).
- Enhancement LangServer Added bool completion entries for attribute properties ([#2555](https://www.noesisengine.com/bugs/view.php?id=2555)).
- Enhancement LangServer Added hardcoded snippets to completion request results ([#2561](https://www.noesisengine.com/bugs/view.php?id=2561)).
- Fixed Path hit test failing for almost straight curves.
- Fixed Horizontal or vertical lines not rendered by [RiveControl](../App.RiveBase/_RiveControl.md) ([#2540](https://www.noesisengine.com/bugs/view.php?id=2540)).
- Fixed Incorrect offscreen node rendering when using projection matrices.
- Fixed Crash accessing already destroyed proxies ([#2424](https://www.noesisengine.com/bugs/view.php?id=2424), [#2552](https://www.noesisengine.com/bugs/view.php?id=2552)).
- Fixed [ApplicationCommands](_ApplicationCommands.md) can be referenced only by name ([#2574](https://www.noesisengine.com/bugs/view.php?id=2574)).
- Fixed [KeyboardNavigation](_KeyboardNavigation.md) failing to focus "off-screen" controls inside a [ScrollViewers](_ScrollViewer.md) ([#2242](https://www.noesisengine.com/bugs/view.php?id=2242)).
- Fixed Focus can move out of a container with TabNavigation="Contained" ([#2474](https://www.noesisengine.com/bugs/view.php?id=2474)).
- Fixed [Selector](_Selector.md) only updates selection if the removed item is the first selected item ([#2582](https://www.noesisengine.com/bugs/view.php?id=2582)).
- Fixed Crash hot-reloading structs ([#2580](https://www.noesisengine.com/bugs/view.php?id=2580)).
- Fixed Support for gradient stops with offsets outside (0 - 1) range.
- Fixed Linking error for duplicated *HarfBuzz* Dependencies ([#2585](https://www.noesisengine.com/bugs/view.php?id=2585)).
- Fixed C# Embedded fonts not found ([#2545](https://www.noesisengine.com/bugs/view.php?id=2545)).
- Fixed C# *RenderContextMTL* failing to initialize on macOS ([#2581](https://www.noesisengine.com/bugs/view.php?id=2581)).
- Fixed C# View *SetManipulationDistanceThreshold* not exposed ([#2583](https://www.noesisengine.com/bugs/view.php?id=2583)).
- Fixed Unity WorldSpace UI inverted when using the fixed pipeline ([#2567](https://www.noesisengine.com/bugs/view.php?id=2567)).
- Fixed Unreal Build fixes for UE5.2.
- Fixed Unreal Use the viewport dimensions for the materials *SceneViews*.
- Fixed Unreal Avoid drawing *WorldUI* views for editor worlds.
- Fixed Unreal Set a *MinimumDesiredSize* so view can be used as a cursor.
- Fixed Unreal Avoid *SceneCapture* scenes when capturing the *BackgroundImage*.
- Fixed Unreal Font Fallbacks defined in settings not working ([#2550](https://www.noesisengine.com/bugs/view.php?id=2550)).
- Fixed Unreal Texture mipmaps ignored when rendering images ([#2576](https://www.noesisengine.com/bugs/view.php?id=2576)).
- Fixed LangServer Completion results being returned for empty documents ([#2554](https://www.noesisengine.com/bugs/view.php?id=2554)).

# Version 3.2.0

*Released 15 March 2023* - [Download](https://www.noesisengine.com/developers/downloads.php)

- This version is no longer compatible with 3.1 licenses.
- Enhancement Updated [Unity](Unity3DTutorial.md) and [Unreal](UnrealTutorial.md) tutorials.
- Enhancement Unreal Removed dependency to FreeType to get dependencies.
- Enhancement Unreal Improvements to World Space UI sample.
- Fixed Unity Importer Warnings ([#2536](https://www.noesisengine.com/bugs/view.php?id=2536)).
- Fixed Unity Circular Dependency in Create Menu ([#2537](https://www.noesisengine.com/bugs/view.php?id=2537)).

# Version 3.2.0rc1

*Released 13 March 2023* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Emscripten library updated to 3.1.8.
- Enhancement Unity Missing Noesis texture label is now detected at import time.
- Enhancement Unity Support for touch events with the new Input System.
- Enhancement Unity World Space no longer disabling PPAA, SubPixel or DPI scale.
- Fixed [ToolBar](_ToolBar.md) overflow is empty ([#2534](https://www.noesisengine.com/bugs/view.php?id=2534)).
- Fixed [ImageBrush](_ImageBrush.md) not taking into account image dpi scale.
- Fixed Missing [ImageSource](_ImageSource.md) converter in [CroppedBitmap](_CroppedBitmap.md) Source property.
- Fixed Unreal UI element remains hovered after the mouse leaves ([#2517](https://www.noesisengine.com/bugs/view.php?id=2517)).

# Version 3.2.0b7

*Released 10 March 2023* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Significant performance improvements in PPAA algorithm.
- Enhancement Unreal Input improvements with support for EnhancedInputActions.
- Enhancement Unreal Gamepad requires now to "Enable Actions" in Noesis View to work.
- Enhancement Unreal Improved detection for EnhancedInput and CommonUI plugins.
- Enhancement Unity PPAA, SubPixel and DPI scale disabled when using World Space.
- Enhancement Unity WorldSpace component moved from samples to runtime.
- Enhancement Unity WorldSpace dynamically adjusting ZIndex of elements.
- Fixed Unity Preview render errors when switching scenes on macOS.
- Fixed Unity Conditional compilation for XR under Universal pipeline.

# Version 3.2.0b6

*Released 6 March 2023* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Support for new renderer API in C#
- Enhancement SIMD performance improvements to path *Filler* and *Stroker*.
- Fixed Unity Uris starting with Packages/ not working.

# Version 3.2.0b5

*Released 1 March 2023* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Enhancement Precise scrolling deltas implemented in AppKitDisplay
- Enhancement Added support for Visual Studio 2022.
- Fixed Prevent namespace definitions from being checked for color info in LangServer
- Fixed Crash destroying Metal render context in M1 devices.
- Fixed Avoid raising binding converter errors when source is being destroyed.
- Fixed Avoid resolving bindings defined in setters until they are applied ([#2334](https://www.noesisengine.com/bugs/view.php?id=2334)).
- Fixed Unreal *EnhancedInputActionTrigger* fix.
- Fixed Unity Errors upgrading from beta versions.
- Fixed C# Null reference exceptions detaching behaviors

# Version 3.2.0b4

*Released 27 Feb 2023* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Fixed Unity HDRP compiler errors.
- Fixed Unity LangServer connection errors.
- Fixed Unity Editor glitches when rendering previews.
- Fixed Unity LangServer is now always connected and entering *Play* is not necessary.
- Fixed Unreal Rive assets not showing *Reimport* options.
- Enhancement Unreal Unity Updated [Tic-Tac-Toe](https://github.com/Noesis/Tutorials/tree/master/Samples/TicTacToe) sample to the new design.

# Version 3.2.0b3

*Released 20 Feb 2023* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature Unreal Unity Implemented support for World Space UI.
- Feature Unreal Unity Implemented support for stereo rendering.
- Feature Unreal Unity Added support for Rive assets.
- Feature Unreal Unity Support for [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=NoesisTechnologies.noesisgui-tools) extension.
- Feature Unity Added support for Vulkan renderer.
- Feature Unity Implemented interactive XAML previews.
- Enhancement Unity Legacy Input System is no longer necessary.
- Enhancement Unreal Unity New [World Space UI](https://github.com/Noesis/Tutorials/tree/master/Samples/WorldSpaceUI) example.
- Enhancement Added support for [RiveControl](../App.RiveBase/_RiveControl.md) listeners ([#2504](https://www.noesisengine.com/bugs/view.php?id=2504)).
- Fixed Unity Filtering of log messages in the render thread ([#2509](https://www.noesisengine.com/bugs/view.php?id=2509)).
- Fixed Unreal Using a MaterialInstanceDynamic doesn't render anything ([#2510](https://www.noesisengine.com/bugs/view.php?id=2510)).
- Fixed Unreal Added *NoesisFindUObjectForComponent* ([#2282](https://www.noesisengine.com/bugs/view.php?id=2282)).
- Fixed Unreal MediaPlayer keeps playing when removed from the scene until it's garbage collected ([#2508](https://www.noesisengine.com/bugs/view.php?id=2508)).
- Fixed Unreal NoesisSlateElement isn't being reset in *TermInstance* ([#2481](https://www.noesisengine.com/bugs/view.php?id=2481)).
- Fixed Unreal NoesisBlueprintCompiler doesn't implement *GetBlueprintTypesForClass* ([#2488](https://www.noesisengine.com/bugs/view.php?id=2488)).
- Fixed *OnRender* clip geometries not using current transform to calculate bounds.
- Fixed Behaviors detached when associated object temporarily removed from visual tree ([#2498](https://www.noesisengine.com/bugs/view.php?id=2498)).
- Fixed NoesisViewEditor *OnPreviewGUI* null reference exception when no XAML selected ([#2496](https://www.noesisengine.com/bugs/view.php?id=2496)).
- Fixed Assert setting Header in [HeaderedItemsControl](_HeaderedItemsControl.md) with [DataTrigger](_DataTrigger.md) ([#2494](https://www.noesisengine.com/bugs/view.php?id=2494)).

# Version 3.2.0b2

*Released 2 Feb 2023* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature [Inspector](InspectorTutorial.md) and [VSCode](https://marketplace.visualstudio.com/items?itemName=NoesisTechnologies.noesisgui-tools) extension are now available for macOS ([#1894](https://www.noesisengine.com/bugs/view.php?id=1894)).
- Enhancement New [Tic-Tac-Toe](https://github.com/Noesis/Tutorials/tree/master/Samples/TicTacToe) example.
- Enhancement New [Localization](LocalizationTutorial.md) tutorial.
- Enhancement Implemented Pipeline library for D3D12 renderer.
- Enhancement Vulkan renderer improvements:
  - Added support for Android.
  - DescriptorSet bindings packed to avoid holes (better performance).
  - Descriptor cache was not correct and was causing glitches in a few drivers.
  - Incorrect layout transitions was causing full clears to our render targets.
  - Implemented Pipeline Derivatives.
  - Improved performance of offscreens having a *VkRenderPass* per tile.
- Enhancement [Uri](../Gui.Providers/_Uri.md) changes:
  - Added *GetScheme()* to return scheme part of the URI (pack, file, http...).
  - *IsAbsolute()* only returns true for URIs with a scheme, the rest are considered relative.
  - *GetPath()* does not return the scheme, only the path part.
- Fixed Path with Stretch=Fill not scaling correctly when available size is Infinity.
- Fixed HitTest failing for Bezier and Arc strokes ([#2060](https://www.noesisengine.com/bugs/view.php?id=2060), [#2468](https://www.noesisengine.com/bugs/view.php?id=2468)).
- Fixed Crash destroying template with *IsMouseOver* triggers ([#2475](https://www.noesisengine.com/bugs/view.php?id=2475)).
- Fixed Binding converter errors not showing binding information ([#2490](https://www.noesisengine.com/bugs/view.php?id=2490)).
- Fixed LayoutUpdated was incorrectly reentering *ProcessLayout* ([#2492](https://www.noesisengine.com/bugs/view.php?id=2492)).
- Fixed Crash in TSF when collapsing focused [TextBox](_TextBox.md) ([#2492](https://www.noesisengine.com/bugs/view.php?id=2492)).

# Version 3.2.0b1

*Released 15 Dec 2022* - [Download](https://www.noesisengine.com/developers/downloads.php)

- Feature Implemented a new *Text Shaping* algorithm ([#1788](https://www.noesisengine.com/bugs/view.php?id=1788) [#1412](https://www.noesisengine.com/bugs/view.php?id=1412) [#2091](https://www.noesisengine.com/bugs/view.php?id=2091)) which includes:

  - Complex scripts and right-to-left languages such as Arabic.
  - [Unicode Bidirectional Algorithm](BidiTutorial.md).
  - Emoji sequences.
  - OpenType features like [ligatures](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/advanced/opentype-font-features?view=netframeworkdesktop-4.8#ligatures), [positioning](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos#positioning-glyphs-with-opentype), and [GPOS](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos) kerning.
  - [Unicode Line Breaking Algorithm](http://www.unicode.org/reports/tr14/).![Changelog_v32_1.jpg](https://www.noesisengine.com/docs/Changelog_v32_1.jpg)

- Feature New Language Server and [Visual Studio Code extension](https://noesisengine.com/vscode).

  - Our language server implements the [Language Server Protocol](https://microsoft.github.io/language-server-protocol/), and uses the NoesisGUI library to provide features for XAML documents including code completion, error reporting, and render previews. For more info see our [Language Server tutorial](LanguageServer.md).![Changelog_v32_2.jpg](https://www.noesisengine.com/docs/Changelog_v32_2.jpg)

- Feature New [RiveControl](../App.RiveBase/_RiveControl.md) for rendering content created with [Rive](https://rive.app/). The Rive Editor brings familiar design and animation tools to create interactive content for your apps and games. We also created an example on [GitHub](https://github.com/Noesis/Tutorials/tree/master/Samples/Rive/C%2B%2B) showcasing this integration.

  ![Changelog_v32_3.jpg](https://www.noesisengine.com/docs/Changelog_v32_3.jpg)
- Feature Implemented [BackgroundEffect](../App.Interactivity/_BackgroundEffectBehavior.md) behavior, which can be used to apply an [effect](ShadersTutorial.md), such as [blur](_BlurEffect.md), to all elements behind a panel. We designed it to allow effects to be applied to the UI and rendered scene together, in both Unreal and Unity. We have created an example on [GitHub](https://github.com/Noesis/Tutorials/tree/master/Samples/BackgroundBlur) showcasing this behavior.

  ![Changelog_v32_4.jpg](https://www.noesisengine.com/docs/Changelog_v32_4.jpg)

- Feature Support for [Single Pass Stereo Rendering](Transform3DTutorial.md#single-pass-stereo). UI elements are rendered simultaneously to the left and right eye buffers. This is more efficient for the CPU as both eye share the work required by traversing and culling the visual tree.

  - *IRenderer* provides a new *Render()* method for sending both stereo projection matrices to the GPU.![Changelog_v32_5.jpg](https://www.noesisengine.com/docs/Changelog_v32_5.jpg)

- Feature Added *World Space UI*. UI elements are integrated and occluded in the 3D-scene. This enables new world UI use-cases, and removes the need for render textures in most situations.

  - *RenderFlags\_DepthTesting* added to *IView* for enabling testing against the depth buffer.
  - Added *VisualTreeHelper::HitTest3D* method.
  - Added *Tracked Device* input events to *IView*.![Changelog_v32_6.jpg](https://www.noesisengine.com/docs/Changelog_v32_6.jpg)

- Feature Curves are now rendered and uploaded to the GPU with a much faster and more precise algorithm. This new technique also handles strokes with higher quality by using offset quadratics. All curves are now internally converted to quadratic Beziers ([#1522](https://www.noesisengine.com/bugs/view.php?id=1522)). *[Image from Baldur's Gate 3 - Larian Studios]*

  ![Changelog_v32_7.jpg](https://www.noesisengine.com/docs/Changelog_v32_7.jpg)
- Feature [Hot Reload](HotReloadTutorial.md) algorithm has been reimplemented. Edited XAML files are now parsed for changes, and those changes are sent to the running app. UI state is preserved, only controls and properties affected by changes are updated.
- Feature Vulkan reference device renderer implemented.
- Feature Font differentiation algorithm when matching family names implemented ([#1868](https://www.noesisengine.com/bugs/view.php?id=1868) [#1789](https://www.noesisengine.com/bugs/view.php?id=1789)).
- Feature Improved *Font Matching* algorithm to allow including the face name in the font family (eg: *FontFamily="Arial Regular"*).
- Feature [Typography](_Typography.md) class implemented ([#2397](https://www.noesisengine.com/bugs/view.php?id=2397)).

  ```
  <TextBlock FontFamily="Fonts/#Arial" Typography.CapitalSpacing="True">
    <Run Typography.Capitals="SmallCaps">Capitals</Run>
    2<Run Typography.Variants="Superscript">3</Run>
  </TextBlock>
  ```
- Feature Added *GetMemoryBase* to [Stream](ProvidersTutorial.md) class to support memory mapped files.
- Feature App *LocalXamlProvider* and *LocalTextureProvider* are now raising [Reloaded](ProvidersTutorial.md#hot-reload) events.
- Feature App All our examples are now compatible with *Hot Reload* by passing the [command line](HotReloadTutorial.md#hot-reload-in-sdk-samples) '--root data\_path'. This switch overrides the default embedded provider with a local provider.
- Feature App XamlPlayer improvements

  - Implemented Drag & Drop of image, font and *Rive* filenames.
  - *Hot Reload* implemented for any dropped content.
- Feature [RichText](../App.ApplicationLauncher/_RichText.md) is a new attached property for [TextBlock](_TextBlock.md) which formats *BBCode* into *Inlines*.
- Feature [LocExtension](../App.ApplicationLauncher/_LocExtension.md), a new markup extension for localization.
- Enhancement [Localization Sample](https://github.com/Noesis/Tutorials/tree/master/Samples/Localization) updated to use [RichText](../App.ApplicationLauncher/_RichText.md) and [LocExtension](../App.ApplicationLauncher/_LocExtension.md). Arabic language added.
- Enhancement [Application Tutorial Sample](https://github.com/Noesis/Tutorials/tree/master/Samples/ApplicationTutorial) updated to use [RichText](../App.ApplicationLauncher/_RichText.md).
- Enhancement [PasswordBox](_PasswordBox.md) showing the last typed character for <n> seconds ([#2356](https://www.noesisengine.com/bugs/view.php?id=2356)).
- Enhancement IntegrationAPI Added *GUI::DisableSocketInit* to avoid sockets initialization in *Profile* builds.
- Enhancement New [Events](EventsTutorial.md) and [Code-Behind](CodeBehindTutorial.md) tutorials.
- Enhancement New [NS\_CONNECT\_FIELD](CodeBehindTutorial.md#x-name-directive) macro for easier x:Name Code-behind connection.
- Fixed Artifacts rendering fonts with stroke or overlapping paths ([#2092](https://www.noesisengine.com/bugs/view.php?id=2092)).
- Fixed Wrong input and output tangents for paths with stroke ([#1404](https://www.noesisengine.com/bugs/view.php?id=1404)).
- Fixed *MergedDictionaries* changes not being notified.
- Enhancement API Breaking Changes:

  - If you are implementing a custom *RenderDevice*, please read our [RenderDevice API](RenderDeviceNotes.md) document.
  - Added support for setting *BlendingMode* in *DrawingContext*.

    ```
    context->PushBlendingMode(Noesis::BlendingMode_Screen);
    context->DrawGeometry(brush, pen, geometry);
    context->Pop();
    ```
  - Trimming properties *TrimStart*, *TrimEnd* and *TrimOffset* moved from [Pen](_Pen.md) to [Geometry](_Geometry.md).
  - Our XAML parser is now case sensitive ([#1742](https://www.noesisengine.com/bugs/view.php?id=1742)) as in WPF. This means, <button /> is no longer valid XAML.
  - IntegrationAPI Removed function overloads with *const char\**, now [Uri](../Gui.Providers/_Uri.md) must always be used.
  - Reflection for enums is now compatible with 64-bit values.
  - *FlipY* parameter used in *IRenderer::Render()* functions was incorrectly applied when using custom projection matrices.

# Previous Versions

## [Version 3.1](Changelog_v31.md)

## [Version 3.0](Changelog_v30.md)

## [Version 2.2](Changelog_v22.md)

## [Version 2.1](Changelog_v21.md)

## [Version 2.0](Changelog_v20.md)

## [Version 1.2](Changelog_v12.md)

## [Version 1.1](Changelog_v11.md)