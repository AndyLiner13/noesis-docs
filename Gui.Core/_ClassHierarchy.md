Source: https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html

# Class Hierarchy

This section of the documentation contains details of the *API* that *NoesisGUI* provides. Supported classes are described with their *Methods*, *Properties* and *Events* in a language-independent way that matches the implementation for each available language like C++ or C#.

The *API* is grouped into two namespaces, *Noesis* with the core functionality of the framework and [NoesisApp](/Gui.Core/ApplicationTutorial.md) used by all our examples and tutorials. Most clients will only use the *Noesis* namespace and will take *NoesisApp* source code as a reference sample.

# Noesis Namespace

| Class | Description |
| --- | --- |
| [Adorner](/Gui.Core/_Adorner.md) | Abstract class that represents a [FrameworkElement](/Gui.Core/_FrameworkElement.md) that decorates another element. |
| [AdornerDecorator](/Gui.Core/_AdornerDecorator.md) | Provides an adorner layer for elements beneath it in the visual tree. |
| [AdornerLayer](/Gui.Core/_AdornerLayer.md) | Represents a surface for rendering adorners. An adorner layer is guaranteed to be at a higher Z-order than the elements being adorned, so adorners are always rendered on top of the adorned elements. |
| [AlternationConverter](/Gui.Core/_AlternationConverter.md) | Converts an integer to/from an object by applying the integer as an index to a list of objects. |
| [Animatable](/Gui.Core/_Animatable.md) | Abstract class that provides animation support. |
| [AnimationClock](/Gui.Animation/_AnimationClock.md) | Maintains the run-time state of an [AnimationTimeline](/Gui.Animation/_AnimationTimeline.md) and processes its output values. |
| [AnimationTimeline](/Gui.Animation/_AnimationTimeline.md) | Defines a segment of time over which output values are produced. These values are used to animate a target property. |
| [ApplicationCommands](/Gui.Core/_ApplicationCommands.md) | Provides a standard set of application related commands. |
| [ArcSegment](/Gui.Core/_ArcSegment.md) | Represents an elliptical arc between two points. |
| [BackEase](/Gui.Animation/_BackEase.md) | Represents an easing function that retracts the motion of an animation slightly before it begins to animate in the path indicated. |
| [BaseBinding](/Gui.Core/_BaseBinding.md) | Defines the common features for [Binding](/Gui.Core/_Binding.md). |
| [BaseBindingExpression](/Gui.Core/_BaseBindingExpression.md) | Represents the base class for all [Binding](/Gui.Core/_Binding.md) Expressions. |
| [BaseButton](/Gui.Core/_BaseButton.md) | Represents the base class for all button controls. |
| [BaseCommand](/Gui.Core/_BaseCommand.md) | Base class for commands. |
| [BaseDefinition](/Gui.Core/_BaseDefinition.md) | Defines the functionality required to support a shared-size group that is used by the ColumnDefinitionCollection and RowDefinitionCollection classes. |
| [BaseDictionary](/Gui.Core/_BaseDictionary.md) | Base class for dictionaries. |
| [BaseFreezableCollection](/Gui.Core/_BaseFreezableCollection.md) | Base class implementation for a [FreezableCollection](/Gui.Core/_FreezableCollection.md). |
| [BaseGridViewRowPresenter](/Gui.Controls/_BaseGridViewRowPresenter.md) | Represents the base class for classes that define the layout for a row of data where different data items are displayed in different columns. |
| [BaseKeyFrame](/Gui.Animation/_BaseKeyFrame.md) | Base class for KeyFrame classes |
| [BaseMenu](/Gui.Core/_BaseMenu.md) | Represents a control that defines choices for users to select. |
| [BaseMultiValueConverter](/Gui.Core/_BaseMultiValueConverter.md) | Base class for value converters used in MultiBindings. |
| [BaseSetter](/Gui.Core/_BaseSetter.md) | Represents the base class for value setters. |
| [BaseTextBox](/Gui.Core/_BaseTextBox.md) | An abstract base class that provides functionality for text editing controls. |
| [BaseTrigger](/Gui.Core/_BaseTrigger.md) | Represents the base class for specifying a conditional value within a [Style](/Gui.Core/_Style.md) object. |
| [BaseValueConverter](/Gui.Core/_BaseValueConverter.md) | Base class for value converters used in Bindings. |
| [BaseView](/Gui.Controls/_BaseView.md) | Represents the base class for views that define the appearance of data in a [ListView](/Gui.Controls/_ListView.md) control. |
| [BeginStoryboard](/Gui.Animation/_BeginStoryboard.md) | A trigger action that begins a [Storyboard](/Gui.Animation/_Storyboard.md) and distributes its animations to their targeted objects and properties. |
| [BezierSegment](/Gui.Core/_BezierSegment.md) | Represents a cubic Bezier curve drawn between two points. |
| [Binding](/Gui.Core/_Binding.md) | Provides high-level access to the definition of a binding, which connects the properties of binding target objects and any data source. |
| [BindingExpression](/Gui.Core/_BindingExpression.md) | Contains information about a single instance of a [Binding](/Gui.Core/_Binding.md). |
| [BindingOperations](/Gui.Core/_BindingOperations.md) | Provides static methods to manipulate bindings. |
| [BitmapImage](/Gui.Core/_BitmapImage.md) | Provides a [BitmapSource](/Gui.Core/_BitmapSource.md) created from an image file located at the specifed [Uri](/Gui.Providers/_Uri.md). |
| [BitmapSource](/Gui.Core/_BitmapSource.md) | Represents a single, constant set of pixels at a certain size and resolution. |
| [BlurEffect](/Gui.Core/_BlurEffect.md) | A bitmap effect that blurs the target texture. |
| [Bold](/Gui.Core/_Bold.md) | An inline-level flow content element which causes content to render with a *bold* font weight. |
| [BooleanAnimationBase](/Gui.Animation/_BooleanAnimationBase.md) | Abstract class that, when implemented, animates a *Boolean* value. |
| [BooleanAnimationUsingKeyFrames](/Gui.Animation/_BooleanAnimationUsingKeyFrames.md) | Animates the value of a *Boolean* property along a set of *KeyFrames*. |
| [BooleanKeyFrame](/Gui.Animation/_BooleanKeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [BooleanAnimationUsingKeyFrames](/Gui.Animation/_BooleanAnimationUsingKeyFrames.md). |
| [BooleanKeyFrameCollection](/Gui.Animation/_BooleanKeyFrameCollection.md) | Represents a collection of [BooleanKeyFrame](/Gui.Animation/_BooleanKeyFrame.md) objects. |
| [BooleanToVisibilityConverter](/Gui.Core/_BooleanToVisibilityConverter.md) | Represents the converter that converts *Boolean* values to and from *Visibility* enumeration values. |
| [Border](/Gui.Core/_Border.md) | Draws a border, background, or both around another element. |
| [BounceEase](/Gui.Animation/_BounceEase.md) | Represents an easing function that creates an animated bouncing effect. |
| [Brush](/Gui.Core/_Brush.md) | Defines objects used to paint graphical objects. Classes that derive from [Brush](/Gui.Core/_Brush.md) describe how the area is painted. |
| [BrushShader](/Gui.Core/_BrushShader.md) | Provides a custom brush by using a pixel shader. |
| [Brushes](/Gui.Core/_Brushes.md) | Declares a set of predefined [SolidColorBrush](/Gui.Core/_SolidColorBrush.md) objects. |
| [BulletDecorator](/Gui.Core/_BulletDecorator.md) | Represents a layout control that aligns a bullet and another visual object. |
| [Button](/Gui.Core/_Button.md) | Represents a push button which reacts to the *Click* event. |
| [Canvas](/Gui.Core/_Canvas.md) | Defines an area within which you can explicitly position child elements by using coordinates that are relative to the [Canvas](/Gui.Core/_Canvas.md) area. |
| [CheckBox](/Gui.Core/_CheckBox.md) | Represents a control that a user can select and clear. |
| [CircleEase](/Gui.Animation/_CircleEase.md) | Represents an easing function that creates an animation that accelerates and/or decelerates using a circular function. |
| [Clock](/Gui.Animation/_Clock.md) | Maintains run-time timing state for a [Timeline](/Gui.Animation/_Timeline.md). |
| [ClockGroup](/Gui.Animation/_ClockGroup.md) | An assemblage of [Clock](/Gui.Animation/_Clock.md) types with behavior based off of a [TimelineGroup](/Gui.Animation/_TimelineGroup.md). |
| [Collection](/Gui.Core/_Collection.md) | Represents a generic collection of objects that can be individually accessed by index. |
| [CollectionView](/Gui.Core/_CollectionView.md) | Represents a view for grouping, sorting, filtering, and navigating a data collection. |
| [CollectionViewSource](/Gui.Core/_CollectionViewSource.md) | Proxy of [CollectionView](/Gui.Core/_CollectionView.md) to be used from XAML files. |
| [ColorAnimation](/Gui.Animation/_ColorAnimation.md) | Animates the value of a *Color* property between two target values using linear interpolation over a specified *Duration*. |
| [ColorAnimationBase](/Gui.Animation/_ColorAnimationBase.md) | Abstract class that, when implemented, animates a *Color* value. |
| [ColorAnimationUsingKeyFrames](/Gui.Animation/_ColorAnimationUsingKeyFrames.md) | Animates the value of a *Color* property along a set of *KeyFrames*. |
| [ColorKeyFrame](/Gui.Animation/_ColorKeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [ColorAnimationUsingKeyFrames](/Gui.Animation/_ColorAnimationUsingKeyFrames.md). |
| [ColorKeyFrameCollection](/Gui.Animation/_ColorKeyFrameCollection.md) | Represents a collection of [ColorKeyFrame](/Gui.Animation/_ColorKeyFrame.md) objects. |
| [Colors](/Gui.Core/_Colors.md) | Implements a set of predefined colors. |
| [ColumnDefinition](/Gui.Core/_ColumnDefinition.md) | Defines column-specific properties that apply to [Grid](/Gui.Core/_Grid.md) elements. |
| [CombinedGeometry](/Gui.Core/_CombinedGeometry.md) | Represents a 2D geometric shape defined by the combination of two [Geometry](/Gui.Core/_Geometry.md) objects. |
| [ComboBox](/Gui.Core/_ComboBox.md) | Represents a selection control with a drop-down list that can be shown or hidden by clicking the arrow on the control. |
| [ComboBoxItem](/Gui.Core/_ComboBoxItem.md) | Implements a selectable item inside a [ComboBox](/Gui.Core/_ComboBox.md). |
| [CommandBinding](/Gui.Core/_CommandBinding.md) | Binds a [RoutedCommand](/Gui.Core/_RoutedCommand.md) to the event handlers that implement the command. |
| [CommandManager](/Gui.Core/_CommandManager.md) | Provides command related events and is responsible for managing routed commands execution. |
| [ComponentCommands](/Gui.Core/_ComponentCommands.md) | Provides a standard set of component related commands. |
| [CompositeTransform](/Gui.Core/_CompositeTransform.md) | This class lets you apply multiple different transforms to an object. |
| [CompositeTransform3D](/Gui.Core/_CompositeTransform3D.md) | Represents 3-D scale, rotation, and translate transforms to be applied to an element. |
| [Condition](/Gui.Core/_Condition.md) | Represents a condition for the [MultiTrigger](/Gui.Core/_MultiTrigger.md) and the [MultiDataTrigger](/Gui.Core/_MultiDataTrigger.md), which apply changes to property values based on a set of conditions. |
| [ContentControl](/Gui.Core/_ContentControl.md) | Represents a control with a single piece of content. |
| [ContentPresenter](/Gui.Core/_ContentPresenter.md) | Displays the content of [ContentControl](/Gui.Core/_ContentControl.md). |
| [ContextMenu](/Gui.Core/_ContextMenu.md) | Represents a pop-up menu that enables a control to expose functionality that is specific to the context of the control. |
| [ContextMenuService](/Gui.Core/_ContextMenuService.md) | Provides the system implementation for displaying a [ContextMenu](/Gui.Core/_ContextMenu.md). |
| [Control](/Gui.Core/_Control.md) | Represents the base class for all user interactive elements. |
| [ControlTemplate](/Gui.Core/_ControlTemplate.md) | Specifies the visual structure and behavioral aspects of a [Control](/Gui.Core/_Control.md) that can be shared across multiple instances of the control. |
| [ControllableStoryboardAction](/Gui.Animation/_ControllableStoryboardAction.md) | Manipulates a [Storyboard](/Gui.Animation/_Storyboard.md) that has been applied by a [BeginStoryboard](/Gui.Animation/_BeginStoryboard.md) action. |
| [CroppedBitmap](/Gui.Core/_CroppedBitmap.md) | Provides an image source that crops another [BitmapSource](/Gui.Core/_BitmapSource.md). |
| [CubicEase](/Gui.Animation/_CubicEase.md) | Represents an easing function that creates an animation that accelerates and/or decelerates using the formula f(t) = t3. |
| [Cursor](/Gui.Core/_Cursor.md) | Represents the image used for the mouse pointer. |
| [Cursors](/Gui.Core/_Cursors.md) | Defines a set of default cursors. |
| [DashStyle](/Gui.Core/_DashStyle.md) | Represents the sequence of dashes and gaps that will be applied by a [Pen](/Gui.Core/_Pen.md). |
| [DataObject](/Gui.Core/_DataObject.md) | Defines a format-independent mechanism for transferring data. |
| [DataTemplate](/Gui.Core/_DataTemplate.md) | Describes the visual structure of a data object. |
| [DataTemplateSelector](/Gui.Core/_DataTemplateSelector.md) | Provides a way to choose a [DataTemplate](/Gui.Core/_DataTemplate.md) based on the data object and the data-bound element. |
| [DataTrigger](/Gui.Core/_DataTrigger.md) | Represents a trigger that applies property values or performs actions when the bound data meets a specified condition. |
| [Decorator](/Gui.Core/_Decorator.md) | Provides a base class for elements that apply effects onto or around a single child element, such as [Border](/Gui.Core/_Border.md) or [Viewbox](/Gui.Core/_Viewbox.md). |
| [DependencyObject](/Gui.DependencySystem/_DependencyObject.md) | Represents an object that participates in the dependency property system. |
| [DependencyProperty](/Gui.DependencySystem/_DependencyProperty.md) | Represents a dependency property that is registered in the property system. Dependency properties provide support for value expressions, property invalidation and dependent-value coercion, default values, inheritance, data binding, animation, property change notification, and styling. |
| [DiscreteBooleanKeyFrame](/Gui.Animation/_DiscreteBooleanKeyFrame.md) | Animates from the *Boolean* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteColorKeyFrame](/Gui.Animation/_DiscreteColorKeyFrame.md) | Animates from the *Color* value of the previous key frame to its own *Value* using discrete interpolation. This class is used as part of a [ColorKeyFrameCollection](/Gui.Animation/_ColorKeyFrameCollection.md) in conjunction with a [ColorAnimationUsingKeyFrames](/Gui.Animation/_ColorAnimationUsingKeyFrames.md) to animate a Color property value along a set of key frames. |
| [DiscreteDoubleKeyFrame](/Gui.Animation/_DiscreteDoubleKeyFrame.md) | Animates from the *Single* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteInt16KeyFrame](/Gui.Animation/_DiscreteInt16KeyFrame.md) | Animates from the *Int16* value of the previous key frame to its own *Value* using discrete interpolation. This class is used as part of a [Int16KeyFrameCollection](/Gui.Animation/_Int16KeyFrameCollection.md) in conjunction with a [Int16AnimationUsingKeyFrames](/Gui.Animation/_Int16AnimationUsingKeyFrames.md) to animate a Int16 property value along a set of key frames. |
| [DiscreteInt32KeyFrame](/Gui.Animation/_DiscreteInt32KeyFrame.md) | Animates from the *Int32* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteInt64KeyFrame](/Gui.Animation/_DiscreteInt64KeyFrame.md) | Animates from the *Int64* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteMatrixKeyFrame](/Gui.Animation/_DiscreteMatrixKeyFrame.md) | Animates from the *Matrix* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteObjectKeyFrame](/Gui.Animation/_DiscreteObjectKeyFrame.md) | Animates from the *Object* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscretePoint3DKeyFrame](/Gui.Animation/_DiscretePoint3DKeyFrame.md) | Animates from the *Point3D* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscretePointKeyFrame](/Gui.Animation/_DiscretePointKeyFrame.md) | Animates from the *Point* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteRectKeyFrame](/Gui.Animation/_DiscreteRectKeyFrame.md) | Animates from the *Rect* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteSizeKeyFrame](/Gui.Animation/_DiscreteSizeKeyFrame.md) | Animates from the *Size* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteStringKeyFrame](/Gui.Animation/_DiscreteStringKeyFrame.md) | Animates from the *String* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteThicknessKeyFrame](/Gui.Animation/_DiscreteThicknessKeyFrame.md) | Animates from the *Thickness* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) | Represents an object with thread affinity. |
| [DockPanel](/Gui.Core/_DockPanel.md) | Defines an area where you can arrange child elements either horizontally or vertically, relative to each other. |
| [DoubleAnimation](/Gui.Animation/_DoubleAnimation.md) | Animates the value of a *Float* property between two target values using linear interpolation over a specified *Duration*. |
| [DoubleAnimationBase](/Gui.Animation/_DoubleAnimationBase.md) | Abstract class that, when implemented, animates a *Float* value. |
| [DoubleAnimationUsingKeyFrames](/Gui.Animation/_DoubleAnimationUsingKeyFrames.md) | Animates the value of a *Double* property along a set of *KeyFrames*. |
| [DoubleKeyFrame](/Gui.Animation/_DoubleKeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [DoubleAnimationUsingKeyFrames](/Gui.Animation/_DoubleAnimationUsingKeyFrames.md). |
| [DoubleKeyFrameCollection](/Gui.Animation/_DoubleKeyFrameCollection.md) | Represents a collection of [DoubleKeyFrame](/Gui.Animation/_DoubleKeyFrame.md) objects. |
| [DragDrop](/Gui.Core/_DragDrop.md) | Provides helper methods and fields for initiating drag-and-drop operations. |
| [DrawingContext](/Gui.Core/_DrawingContext.md) | Describes visual content using draw, push, and pop commands during [UIElement](/Gui.Core/_UIElement.md) *OnRender*. |
| [DropShadowEffect](/Gui.Core/_DropShadowEffect.md) | A bitmap effect that paints a drop shadow around the target texture. |
| [Duration](/Gui.Animation/_Duration.md) | Represents the duration of time that a [Timeline](/Gui.Animation/_Timeline.md) is active. |
| [DynamicResourceExtension](/Gui.Core/_DynamicResourceExtension.md) | Implements a markup extension that supports dynamic resource references made from XAML. |
| [DynamicTextureSource](/Gui.Core/_DynamicTextureSource.md) | Defines an [ImageSource](/Gui.Core/_ImageSource.md) implementation based on a dynamic texture. |
| [EasingColorKeyFrame](/Gui.Animation/_EasingColorKeyFrame.md) | A class that enables you to associate easing functions with a [ColorAnimationUsingKeyFrames](/Gui.Animation/_ColorAnimationUsingKeyFrames.md) key frame animation. |
| [EasingDoubleKeyFrame](/Gui.Animation/_EasingDoubleKeyFrame.md) | A class that enables you to associate easing functions with a [DoubleAnimationUsingKeyFrames](/Gui.Animation/_DoubleAnimationUsingKeyFrames.md) key frame animation. |
| [EasingFunctionBase](/Gui.Animation/_EasingFunctionBase.md) | Provides the base class for all the easing functions. You can create your own custom easing functions by inheriting from this class. |
| [EasingInt16KeyFrame](/Gui.Animation/_EasingInt16KeyFrame.md) | A class that enables you to associate easing functions with a [Int16AnimationUsingKeyFrames](/Gui.Animation/_Int16AnimationUsingKeyFrames.md) key frame animation. |
| [EasingInt32KeyFrame](/Gui.Animation/_EasingInt32KeyFrame.md) | A class that enables you to associate easing functions with a [Int32AnimationUsingKeyFrames](/Gui.Animation/_Int32AnimationUsingKeyFrames.md) key frame animation. |
| [EasingInt64KeyFrame](/Gui.Animation/_EasingInt64KeyFrame.md) | A class that enables you to associate easing functions with a [Int64AnimationUsingKeyFrames](/Gui.Animation/_Int64AnimationUsingKeyFrames.md) key frame animation. |
| [EasingPoint3DKeyFrame](/Gui.Animation/_EasingPoint3DKeyFrame.md) | A class that enables you to associate easing functions with a [Point3DAnimationUsingKeyFrames](/Gui.Animation/_Point3DAnimationUsingKeyFrames.md) key frame animation. |
| [EasingPointKeyFrame](/Gui.Animation/_EasingPointKeyFrame.md) | A class that enables you to associate easing functions with a [PointAnimationUsingKeyFrames](/Gui.Animation/_PointAnimationUsingKeyFrames.md) key frame animation. |
| [EasingRectKeyFrame](/Gui.Animation/_EasingRectKeyFrame.md) | A class that enables you to associate easing functions with a [RectAnimationUsingKeyFrames](/Gui.Animation/_RectAnimationUsingKeyFrames.md) key frame animation. |
| [EasingSizeKeyFrame](/Gui.Animation/_EasingSizeKeyFrame.md) | A class that enables you to associate easing functions with a [SizeAnimationUsingKeyFrames](/Gui.Animation/_SizeAnimationUsingKeyFrames.md) key frame animation. |
| [EasingThicknessKeyFrame](/Gui.Animation/_EasingThicknessKeyFrame.md) | A class that enables you to associate easing functions with a [ThicknessAnimationUsingKeyFrames](/Gui.Animation/_ThicknessAnimationUsingKeyFrames.md) key frame animation. |
| [Effect](/Gui.Core/_Effect.md) | Provides a custom bitmap effect. |
| [ElasticEase](/Gui.Animation/_ElasticEase.md) | Represents an easing function that creates an animation that resembles a spring oscillating back and forth until it comes to rest. |
| [Ellipse](/Gui.Core/_Ellipse.md) | Draws an ellipse. |
| [EllipseGeometry](/Gui.Core/_EllipseGeometry.md) | Represents the geometry of a circle or ellipse. |
| [EventTrigger](/Gui.Core/_EventTrigger.md) | Represents a trigger that applies a set of actions in response to an event. |
| [Expander](/Gui.Core/_Expander.md) | Represents a control that displays a header with a collapsible window to display content. |
| [ExponentialEase](/Gui.Animation/_ExponentialEase.md) | Represents an easing function that creates an animation that accelerates and/or decelerates using an exponential formula. |
| [Expression](/Gui.DependencySystem/_Expression.md) | Base implementation for all expressions. |
| [FocusManager](/Gui.Core/_FocusManager.md) | Provides a set of static methods, attached properties, and events for determining and setting focus scopes and for setting the focused element within the scope. |
| [FontFamily](/Gui.Core/_FontFamily.md) | Represents a family of related fonts. |
| [FormattedText](/Gui.Core/_FormattedText.md) | Provides low-level control for drawing text. |
| [FrameworkElement](/Gui.Core/_FrameworkElement.md) | Provides GUI framework-level features for user interface elements. |
| [FrameworkPropertyMetadata](/Gui.Core/_FrameworkPropertyMetadata.md) | Reports or applies metadata for a dependency property, specifically adding framework-specific property system characteristics. |
| [FrameworkTemplate](/Gui.Core/_FrameworkTemplate.md) | Enables the instantiation of a tree of elements for a template. |
| [Freezable](/Gui.DependencySystem/_Freezable.md) | Defines an object that has a modifiable state and a read-only (frozen) state. |
| [FreezableCollection](/Gui.Core/_FreezableCollection.md) | Represents a collection of [DependencyObject](/Gui.DependencySystem/_DependencyObject.md), [Freezable](/Gui.DependencySystem/_Freezable.md), or [Animatable](/Gui.Core/_Animatable.md) objects. [FreezableCollection](/Gui.Core/_FreezableCollection.md) is itself an [Animatable](/Gui.Core/_Animatable.md) type. |
| [Geometry](/Gui.Core/_Geometry.md) | Classes that derive from this abstract base class define geometric shapes. [Geometry](/Gui.Core/_Geometry.md) objects can be used for clipping, hit-testing, and rendering 2D graphic data. |
| [GeometryGroup](/Gui.Core/_GeometryGroup.md) | Represents a composite geometry, composed of other [Geometry](/Gui.Core/_Geometry.md) objects. |
| [GradientBrush](/Gui.Core/_GradientBrush.md) | Defines an abstract class that describes a gradient, composed of gradient stops. Classes that inherit from [GradientBrush](/Gui.Core/_GradientBrush.md) describe different ways of interpreting gradient stops. |
| [GradientStop](/Gui.Core/_GradientStop.md) | Describes the location and color of a transition point in a gradient. |
| [GradientStopCollection](/Gui.Core/_GradientStopCollection.md) | Represents a collection of [GradientStop](/Gui.Core/_GradientStop.md) objects that can be individually accessed by index. |
| [Grid](/Gui.Core/_Grid.md) | Defines a flexible grid area that consists of columns and rows. |
| [GridLength](/Gui.Core/_GridLength.md) | Represents the length of elements that explicitly support *Star* unit types. Elements such as [ColumnDefinition](/Gui.Core/_ColumnDefinition.md) and [RowDefinition](/Gui.Core/_RowDefinition.md) use this type to describe width and height in order to support variable distribution of available space. |
| [GridSplitter](/Gui.Core/_GridSplitter.md) | Represents the control that redistributes space between columns or rows of a [Grid](/Gui.Core/_Grid.md) control. |
| [GridView](/Gui.Controls/_GridView.md) | Represents a view mode that displays data items in columns for a [ListView](/Gui.Controls/_ListView.md) control. |
| [GridViewColumn](/Gui.Controls/_GridViewColumn.md) | Represents a column that displays data. |
| [GridViewColumnHeader](/Gui.Controls/_GridViewColumnHeader.md) | Represents a column header for a [GridViewColumn](/Gui.Controls/_GridViewColumn.md). |
| [GridViewHeaderRowPresenter](/Gui.Controls/_GridViewHeaderRowPresenter.md) | Represents an object that is used to define the layout of a row of column headers. |
| [GridViewRowPresenter](/Gui.Controls/_GridViewRowPresenter.md) | Represents an object that specifies the layout of a row of data. |
| [GroupBox](/Gui.Core/_GroupBox.md) | Represents a control that displays a frame around a group of controls with an optional caption. |
| [HeaderedContentControl](/Gui.Core/_HeaderedContentControl.md) | Provides the base implementation for all controls that contain single content and have a header. |
| [HeaderedItemsControl](/Gui.Core/_HeaderedItemsControl.md) | Represents a control that contains multiple items and has a header. |
| [HierarchicalDataTemplate](/Gui.Core/_HierarchicalDataTemplate.md) | Represents a [DataTemplate](/Gui.Core/_DataTemplate.md) that supports [HeaderedItemsControl](/Gui.Core/_HeaderedItemsControl.md), such as [TreeViewItem](/Gui.Core/_TreeViewItem.md) or [MenuItem](/Gui.Core/_MenuItem.md). |
| [Hyperlink](/Gui.Core/_Hyperlink.md) | An inline-level flow content element that hosts hyperlinks within flow content. |
| [ISealable](/Gui.DependencySystem/_ISealable.md) | This interface is shared across [Freezable](/Gui.DependencySystem/_Freezable.md), [Style](/Gui.Core/_Style.md) and Template. A sealed object is free-threaded. |
| [Image](/Gui.Core/_Image.md) | Represents a control that displays an image. |
| [ImageBrush](/Gui.Core/_ImageBrush.md) | Paints an area with an image. |
| [ImageSource](/Gui.Core/_ImageSource.md) | Represents an image object that has width and height. |
| [Inline](/Gui.Core/_Inline.md) | An abstract class that provides a base for all inline flow content elements. |
| [InlineUIContainer](/Gui.Core/_InlineUIContainer.md) | An inline-level flow content element which enables [UIElement](/Gui.Core/_UIElement.md) elements (i.e. a [Button](/Gui.Core/_Button.md)) to be embedded in flow content. |
| [InputBinding](/Gui.Core/_InputBinding.md) | Represents a binding between an [InputGesture](/Gui.Core/_InputGesture.md) and a command. |
| [InputGesture](/Gui.Core/_InputGesture.md) | Abstract class that describes input device gestures. |
| [Int16Animation](/Gui.Animation/_Int16Animation.md) | Animates the value of a *Int16* property between two 'target values' using linear interpolation over a specified *Duration*. |
| [Int16AnimationBase](/Gui.Animation/_Int16AnimationBase.md) | Abstract class that, when implemented, animates a *Int16* value. |
| [Int16AnimationUsingKeyFrames](/Gui.Animation/_Int16AnimationUsingKeyFrames.md) | Animates the value of a *Int16* property along a set of *KeyFrames*. |
| [Int16KeyFrame](/Gui.Animation/_Int16KeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [Int16AnimationUsingKeyFrames](/Gui.Animation/_Int16AnimationUsingKeyFrames.md). |
| [Int16KeyFrameCollection](/Gui.Animation/_Int16KeyFrameCollection.md) | Represents a collection of [Int16KeyFrame](/Gui.Animation/_Int16KeyFrame.md) objects. |
| [Int32Animation](/Gui.Animation/_Int32Animation.md) | Animates the value of a *Int32* property between two target values using linear interpolation over a specified *Duration*. |
| [Int32AnimationBase](/Gui.Animation/_Int32AnimationBase.md) | Abstract class that, when implemented, animates a *Int32* value. |
| [Int32AnimationUsingKeyFrames](/Gui.Animation/_Int32AnimationUsingKeyFrames.md) | Animates the value of a *Int32* property along a set of *KeyFrames*. |
| [Int32KeyFrame](/Gui.Animation/_Int32KeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [Int32AnimationUsingKeyFrames](/Gui.Animation/_Int32AnimationUsingKeyFrames.md). |
| [Int32KeyFrameCollection](/Gui.Animation/_Int32KeyFrameCollection.md) | Represents a collection of [Int32KeyFrame](/Gui.Animation/_Int32KeyFrame.md) objects. |
| [Int64Animation](/Gui.Animation/_Int64Animation.md) | Animates the value of a *Int64* property between two target values using linear interpolation over a specified *Duration*. |
| [Int64AnimationBase](/Gui.Animation/_Int64AnimationBase.md) | Abstract class that, when implemented, animates a *Int64* value. |
| [Int64AnimationUsingKeyFrames](/Gui.Animation/_Int64AnimationUsingKeyFrames.md) | Animates the value of a *Int64* property along a set of *KeyFrames*. |
| [Int64KeyFrame](/Gui.Animation/_Int64KeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [Int64AnimationUsingKeyFrames](/Gui.Animation/_Int64AnimationUsingKeyFrames.md). |
| [Int64KeyFrameCollection](/Gui.Animation/_Int64KeyFrameCollection.md) | Represents a collection of [Int64KeyFrame](/Gui.Animation/_Int64KeyFrame.md) objects. |
| [Italic](/Gui.Core/_Italic.md) | An inline-level flow content element that causes content to render with an italic font style. |
| [ItemCollection](/Gui.Core/_ItemCollection.md) | Holds the list of items that constitute the content of an [ItemsControl](/Gui.Core/_ItemsControl.md). |
| [ItemContainerGenerator](/Gui.Core/_ItemContainerGenerator.md) | Generates the user interface on behalf of its host, such as an [ItemsControl](/Gui.Core/_ItemsControl.md). |
| [ItemsControl](/Gui.Core/_ItemsControl.md) | Represents a control that can be used to present a collection of items. |
| [ItemsPanelTemplate](/Gui.Core/_ItemsPanelTemplate.md) | Specifies the panel that the [ItemsPresenter](/Gui.Core/_ItemsPresenter.md) creates for the layout of the items of an [ItemsControl](/Gui.Core/_ItemsControl.md). |
| [ItemsPresenter](/Gui.Core/_ItemsPresenter.md) | Used within the template of an ItemControl to specify the place in the control's visual tree where the ItemsPanel defined by the [ItemsControl](/Gui.Core/_ItemsControl.md) is to be added. |
| [KeyBinding](/Gui.Core/_KeyBinding.md) | Binds a [KeyGesture](/Gui.Core/_KeyGesture.md) to a Command. |
| [KeyGesture](/Gui.Core/_KeyGesture.md) | Defines a keyboard combination that can be used to invoke a command. |
| [KeySpline](/Gui.Animation/_KeySpline.md) | This class is used by a spline key frame to define animation progress. |
| [KeyTime](/Gui.Animation/_KeyTime.md) | Specifies the precise timing when a particular key frame should take place |
| [Keyboard](/Gui.Core/_Keyboard.md) | Represents the keyboard device. |
| [KeyboardNavigation](/Gui.Core/_KeyboardNavigation.md) | Provides logical and directional navigation between focusable objects. |
| [Label](/Gui.Core/_Label.md) | Represents the text label for a control. |
| [Line](/Gui.Core/_Line.md) | Draws a line. |
| [LineBreak](/Gui.Core/_LineBreak.md) | An inline flow content element that causes a line break to occur in flow content. |
| [LineGeometry](/Gui.Core/_LineGeometry.md) | Represents the geometry of a line. |
| [LineSegment](/Gui.Core/_LineSegment.md) | Creates a line between two points in a [PathFigure](/Gui.Core/_PathFigure.md). |
| [LinearColorKeyFrame](/Gui.Animation/_LinearColorKeyFrame.md) | Animates from the *Color* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearDoubleKeyFrame](/Gui.Animation/_LinearDoubleKeyFrame.md) | Animates from the *Float* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearGradientBrush](/Gui.Core/_LinearGradientBrush.md) | Paints an area with a linear gradient. A [LinearGradientBrush](/Gui.Core/_LinearGradientBrush.md) paints an area with a linear gradient. A linear gradient defines a gradient along a line. The line's end points are defined by the *StartPoint* and *EndPoint* properties of the linear gradient. A [LinearGradientBrush](/Gui.Core/_LinearGradientBrush.md) brush paints its *GradientStops* along this line. |
| [LinearInt16KeyFrame](/Gui.Animation/_LinearInt16KeyFrame.md) | Animates from the *Int16* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearInt32KeyFrame](/Gui.Animation/_LinearInt32KeyFrame.md) | Animates from the *Int32* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearInt64KeyFrame](/Gui.Animation/_LinearInt64KeyFrame.md) | Animates from the *Int64* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearPoint3DKeyFrame](/Gui.Animation/_LinearPoint3DKeyFrame.md) | Animates from the *Point3D* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearPointKeyFrame](/Gui.Animation/_LinearPointKeyFrame.md) | Animates from the *Point* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearRectKeyFrame](/Gui.Animation/_LinearRectKeyFrame.md) | Animates from the *Rect* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearSizeKeyFrame](/Gui.Animation/_LinearSizeKeyFrame.md) | Animates from the *Size* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearThicknessKeyFrame](/Gui.Animation/_LinearThicknessKeyFrame.md) | Animates from the *Thickness* value of the previous key frame to its own *Value* using linear interpolation. |
| [ListBox](/Gui.Core/_ListBox.md) | Contains a list of selectable items. |
| [ListBoxItem](/Gui.Core/_ListBoxItem.md) | Represents a selectable item in a [ListBox](/Gui.Core/_ListBox.md). |
| [ListView](/Gui.Controls/_ListView.md) | Represents a control that displays a list of data items. |
| [ListViewItem](/Gui.Controls/_ListViewItem.md) | Represents an item in a [ListView](/Gui.Controls/_ListView.md) control. |
| [LogicalTreeHelper](/Gui.Core/_LogicalTreeHelper.md) | Contains static methods useful for performing common tasks with nodes in a logical tree. |
| [MarkupExtension](/Gui.Core/_MarkupExtension.md) | Provides a base class for XAML markup extension implementations. |
| [MatrixAnimationBase](/Gui.Animation/_MatrixAnimationBase.md) | Abstract class that, when implemented, animates a *Matrix* value. |
| [MatrixAnimationUsingKeyFrames](/Gui.Animation/_MatrixAnimationUsingKeyFrames.md) | Animates the value of a *Matrix* property along a set of *KeyFrames*. |
| [MatrixKeyFrame](/Gui.Animation/_MatrixKeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [MatrixAnimationUsingKeyFrames](/Gui.Animation/_MatrixAnimationUsingKeyFrames.md). |
| [MatrixKeyFrameCollection](/Gui.Animation/_MatrixKeyFrameCollection.md) | Represents a collection of [MatrixKeyFrame](/Gui.Animation/_MatrixKeyFrame.md) objects. |
| [MatrixTransform](/Gui.Core/_MatrixTransform.md) | Creates an arbitrary affine matrix transformation that is used to manipulate objects or coordinate systems in a 2D plane. |
| [MatrixTransform3D](/Gui.Core/_MatrixTransform3D.md) | Applies a 3D transformation matrix to an object. |
| [Menu](/Gui.Core/_Menu.md) | Represents a Windows menu control that enables you to hierarchically organize elements associated with commands and event handlers. |
| [MenuItem](/Gui.Core/_MenuItem.md) | Represents a selectable item inside a [Menu](/Gui.Core/_Menu.md) or [ContextMenu](/Gui.Core/_ContextMenu.md). |
| [Mesh](/Gui.Core/_Mesh.md) | Renders a mesh geometry defined by vertices and indexed triangles. |
| [MeshData](/Gui.Core/_MeshData.md) | Represents a low-level geometric mesh composed of vertices and indexed triangles. |
| [Mouse](/Gui.Core/_Mouse.md) | Represents the mouse device. |
| [MouseBinding](/Gui.Core/_MouseBinding.md) | Binds a [MouseGesture](/Gui.Core/_MouseGesture.md) to a Command. |
| [MouseGesture](/Gui.Core/_MouseGesture.md) | Defines a mouse input gesture that can be used to invoke a command. |
| [MultiBinding](/Gui.Core/_MultiBinding.md) | Describes a collection of [Binding](/Gui.Core/_Binding.md) objects attached to a single binding target property. |
| [MultiBindingExpression](/Gui.Core/_MultiBindingExpression.md) | Contains instance information about a single instance of a [MultiBinding](/Gui.Core/_MultiBinding.md). |
| [MultiDataTrigger](/Gui.Core/_MultiDataTrigger.md) | Represents a trigger that applies property values or performs actions when the bound data meets a set of conditions. |
| [MultiTrigger](/Gui.Core/_MultiTrigger.md) | Represents a trigger that applies property values or performs actions when a set of conditions are satisfied. |
| [NameScope](/Gui.Core/_NameScope.md) | Store relationships between the XAML defined names of objects and their instances. |
| [NullExtension](/Gui.Core/_NullExtension.md) | Implements a XAML markup extension in order to return a null object. |
| [ObjectAnimationBase](/Gui.Animation/_ObjectAnimationBase.md) | Abstract class that, when implemented, animates a *Object* value. |
| [ObjectAnimationUsingKeyFrames](/Gui.Animation/_ObjectAnimationUsingKeyFrames.md) | Animates the value of a *BaseComponent* property along a set of *KeyFrames*. |
| [ObjectKeyFrame](/Gui.Animation/_ObjectKeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [ObjectAnimationUsingKeyFrames](/Gui.Animation/_ObjectAnimationUsingKeyFrames.md). |
| [ObjectKeyFrameCollection](/Gui.Animation/_ObjectKeyFrameCollection.md) | Represents a collection of [ObjectKeyFrame](/Gui.Animation/_ObjectKeyFrame.md) objects. |
| [ObservableCollection](/Gui.Core/_ObservableCollection.md) | Represents a dynamic data collection that provides notifications when items get added or removed. |
| [Page](/Gui.Core/_Page.md) | Encapsulates a page of content. |
| [Panel](/Gui.Core/_Panel.md) | Provides a base class for all [Panel](/Gui.Core/_Panel.md) elements. Use [Panel](/Gui.Core/_Panel.md) elements to position and arrange child objects. |
| [ParallelTimeline](/Gui.Animation/_ParallelTimeline.md) | Defines a segment of time that may contain child [Timeline](/Gui.Animation/_Timeline.md) objects. |
| [PasswordBox](/Gui.Core/_PasswordBox.md) | Represents a control designed for entering and handling passwords. |
| [Path](/Gui.Core/_Path.md) | Draws a series of connected lines and curves. |
| [PathFigure](/Gui.Core/_PathFigure.md) | Represents a subsection of a geometry, a single connected series of two-dimensional segments. |
| [PathGeometry](/Gui.Core/_PathGeometry.md) | Represents a complex shape that may be composed of arcs, curves, ellipses, lines and rectangles. |
| [PathSegment](/Gui.Core/_PathSegment.md) | Represents a complex shape that may be composed of arcs, curves, ellipses, lines and rectangles. |
| [PauseStoryboard](/Gui.Animation/_PauseStoryboard.md) | A trigger action that pauses a [Storyboard](/Gui.Animation/_Storyboard.md). |
| [Pen](/Gui.Core/_Pen.md) | Describes how a shape is outlined. |
| [Point3DAnimation](/Gui.Animation/_Point3DAnimation.md) | Animates the value of a *Point3D* property between two target values using linear interpolation over a specified *Duration*. |
| [Point3DAnimationBase](/Gui.Animation/_Point3DAnimationBase.md) | Abstract class that, when implemented, animates a *Point3D* value. |
| [Point3DAnimationUsingKeyFrames](/Gui.Animation/_Point3DAnimationUsingKeyFrames.md) | Animates the value of a *Point3D* property along a set of *KeyFrames*. |
| [Point3DKeyFrame](/Gui.Animation/_Point3DKeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [Point3DAnimationUsingKeyFrames](/Gui.Animation/_Point3DAnimationUsingKeyFrames.md). |
| [Point3DKeyFrameCollection](/Gui.Animation/_Point3DKeyFrameCollection.md) | Represents a collection of [Point3DKeyFrame](/Gui.Animation/_Point3DKeyFrame.md) objects. |
| [PointAnimation](/Gui.Animation/_PointAnimation.md) | Animates the value of a *Point* property between two target values using linear interpolation over a specified *Duration*. |
| [PointAnimationBase](/Gui.Animation/_PointAnimationBase.md) | Abstract class that, when implemented, animates a *Point* value. |
| [PointAnimationUsingKeyFrames](/Gui.Animation/_PointAnimationUsingKeyFrames.md) | Animates the value of a *Point* property along a set of *KeyFrames*. |
| [PointKeyFrame](/Gui.Animation/_PointKeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [PointAnimationUsingKeyFrames](/Gui.Animation/_PointAnimationUsingKeyFrames.md). |
| [PointKeyFrameCollection](/Gui.Animation/_PointKeyFrameCollection.md) | Represents a collection of [PointKeyFrame](/Gui.Animation/_PointKeyFrame.md) objects. |
| [PolyBezierSegment](/Gui.Core/_PolyBezierSegment.md) | Represents one or more cubic Bezier curves. |
| [PolyLineSegment](/Gui.Core/_PolyLineSegment.md) | Represents a set of line segments defined by a PointCollection with each Point specifying the end point of a line segment. |
| [PolyQuadraticBezierSegment](/Gui.Core/_PolyQuadraticBezierSegment.md) | Represents one or more quadratic Bezier curves. |
| [Popup](/Gui.Core/_Popup.md) | Represents a pop-up window that has content. |
| [PowerEase](/Gui.Animation/_PowerEase.md) | Represents an easing function that creates an animation that accelerates and/or decelerates using the formula f(t) = tp where p is equal to the *Power* property. |
| [ProgressBar](/Gui.Core/_ProgressBar.md) | Indicates the progress of an operation. |
| [PropertyMetadata](/Gui.DependencySystem/_PropertyMetadata.md) | Defines certain behavior aspects of a dependency property as it is applied to a specific type, including conditions it was registered with. |
| [PropertyPath](/Gui.Core/_PropertyPath.md) | Implements a data structure for describing a property as a path below another property, or below an owning type. Property paths are used in data binding to objects, and in storyboards and timelines for animations. |
| [QuadraticBezierSegment](/Gui.Core/_QuadraticBezierSegment.md) | Represents a quadratic Bezier curve drawn between two points. |
| [QuadraticEase](/Gui.Animation/_QuadraticEase.md) | Represents an easing function that creates an animation that accelerates and/or decelerates using the formula f(t) = t2. |
| [QuarticEase](/Gui.Animation/_QuarticEase.md) | Represents an easing function that creates an animation that accelerates and/or decelerates using the formula f(t) = t4. |
| [QuinticEase](/Gui.Animation/_QuinticEase.md) | Represents an easing function that creates an animation that accelerates and/or decelerates using the formula f(t) = t5. |
| [RadialGradientBrush](/Gui.Core/_RadialGradientBrush.md) | Paints an area with a radial gradient. |
| [RadioButton](/Gui.Core/_RadioButton.md) | Represents a button that can be selected, but not cleared, by a user. |
| [RangeBase](/Gui.Core/_RangeBase.md) | Represents an element that has a value within a specific range. |
| [RectAnimation](/Gui.Animation/_RectAnimation.md) | Animates the value of a *Rect* property between two target values using linear interpolation over a specified *Duration*. |
| [RectAnimationBase](/Gui.Animation/_RectAnimationBase.md) | Abstract class that, when implemented, animates a *Rect* value. |
| [RectAnimationUsingKeyFrames](/Gui.Animation/_RectAnimationUsingKeyFrames.md) | Animates the value of a *Rect* property along a set of *KeyFrames*. |
| [RectKeyFrame](/Gui.Animation/_RectKeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [RectAnimationUsingKeyFrames](/Gui.Animation/_RectAnimationUsingKeyFrames.md). |
| [RectKeyFrameCollection](/Gui.Animation/_RectKeyFrameCollection.md) | Represents a collection of [RectKeyFrame](/Gui.Animation/_RectKeyFrame.md) objects. |
| [Rectangle](/Gui.Core/_Rectangle.md) | Draws a rectangle. |
| [RectangleGeometry](/Gui.Core/_RectangleGeometry.md) | Describes a two-dimensional rectangle geometry. |
| [RelativeSource](/Gui.Core/_RelativeSource.md) | Implements a markup extension that describes the location of the binding source relative to the position of the binding target. |
| [RenderOptions](/Gui.Core/_RenderOptions.md) | Provides options for controlling the rendering behavior of objects. |
| [RepeatBehavior](/Gui.Animation/_RepeatBehavior.md) | Describes how a [Timeline](/Gui.Animation/_Timeline.md) repeats its simple duration. Examples: |
| [RepeatButton](/Gui.Core/_RepeatButton.md) | Represents a control that raises its *Click* event repeatedly from the time it is pressed until it is released. |
| [ResourceDictionary](/Gui.Core/_ResourceDictionary.md) | Provides a hash table implementation that contains resources used by the UI. |
| [ResumeStoryboard](/Gui.Animation/_ResumeStoryboard.md) | A trigger action that resumes a paused [Storyboard](/Gui.Animation/_Storyboard.md). |
| [RotateTransform](/Gui.Core/_RotateTransform.md) | Rotates an object clockwise about a specified point in 2D coordinate system. |
| [RoutedCommand](/Gui.Core/_RoutedCommand.md) | A command that is routed through the element tree. |
| [RoutedEvent](/Gui.Core/_RoutedEvent.md) | An event instance that propagates through a tree of related elements. There are three types of routing: bubbling, tunneling and direct. With bubbling, the event instance moves from the source of the event up to the top of the tree. With tunneling, the event instance starts at the top of the tree and moves down to the source of the event. With direct routing, the event instance behaves like a standard event. |
| [RoutedUICommand](/Gui.Core/_RoutedUICommand.md) | A command that is routed through the element tree and contains a text property. |
| [RowDefinition](/Gui.Core/_RowDefinition.md) | Defines row-specific properties that apply to [Grid](/Gui.Core/_Grid.md) elements. |
| [Run](/Gui.Core/_Run.md) | An inline-level flow content element intended to contain a run of formatted or unformatted text. |
| [ScaleTransform](/Gui.Core/_ScaleTransform.md) | Scales an object in the 2D coordinate system. |
| [ScrollBar](/Gui.Core/_ScrollBar.md) | Represents a control that provides a scroll bar that has a sliding [Thumb](/Gui.Core/_Thumb.md) whose position corresponds to a value. |
| [ScrollContentPresenter](/Gui.Core/_ScrollContentPresenter.md) | Displays the content of a [ScrollViewer](/Gui.Core/_ScrollViewer.md) control. |
| [ScrollViewer](/Gui.Core/_ScrollViewer.md) | Represents a scrollable area that can contain other visible elements. |
| [Selector](/Gui.Core/_Selector.md) | Represents a control that allows a user to select items from among its child elements. |
| [Separator](/Gui.Core/_Separator.md) | [Control](/Gui.Core/_Control.md) that is used to separate items in items controls. |
| [Setter](/Gui.Core/_Setter.md) | Represents a setter that applies a property value. |
| [ShaderEffect](/Gui.Core/_ShaderEffect.md) | Provides a custom bitmap effect by using a pixel shader. |
| [Shape](/Gui.Core/_Shape.md) | Provides a base class for shape elements. |
| [SineEase](/Gui.Animation/_SineEase.md) | Represents an easing function that creates an animation that accelerates and/or decelerates using a sine formula |
| [SizeAnimation](/Gui.Animation/_SizeAnimation.md) | Animates the value of a *Size* property between two target values using linear interpolation over a specified *Duration*. |
| [SizeAnimationBase](/Gui.Animation/_SizeAnimationBase.md) | Abstract class that, when implemented, animates a *Size* value. |
| [SizeAnimationUsingKeyFrames](/Gui.Animation/_SizeAnimationUsingKeyFrames.md) | Animates the value of a *Size* property along a set of *KeyFrames*. |
| [SizeKeyFrame](/Gui.Animation/_SizeKeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [SizeAnimationUsingKeyFrames](/Gui.Animation/_SizeAnimationUsingKeyFrames.md). |
| [SizeKeyFrameCollection](/Gui.Animation/_SizeKeyFrameCollection.md) | Represents a collection of [SizeKeyFrame](/Gui.Animation/_SizeKeyFrame.md) objects. |
| [SkewTransform](/Gui.Core/_SkewTransform.md) | Represents a 2D skew. It is useful for creating the illusion of 3-dimensional depth in a 2D object. |
| [Slider](/Gui.Core/_Slider.md) | Represents a control that lets the user select from a range of values by moving a [Thumb](/Gui.Core/_Thumb.md) control along a [Track](/Gui.Core/_Track.md). |
| [SolidColorBrush](/Gui.Core/_SolidColorBrush.md) | Paints an area with a solid color. |
| [Span](/Gui.Core/_Span.md) | Groups other [Inline](/Gui.Core/_Inline.md) content elements. |
| [SplineColorKeyFrame](/Gui.Animation/_SplineColorKeyFrame.md) | Animates from the *Color* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineDoubleKeyFrame](/Gui.Animation/_SplineDoubleKeyFrame.md) | Animates from the *Float* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineInt16KeyFrame](/Gui.Animation/_SplineInt16KeyFrame.md) | Animates from the *Int16* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineInt32KeyFrame](/Gui.Animation/_SplineInt32KeyFrame.md) | Animates from the *Int32* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineInt64KeyFrame](/Gui.Animation/_SplineInt64KeyFrame.md) | Animates from the *Int64* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplinePoint3DKeyFrame](/Gui.Animation/_SplinePoint3DKeyFrame.md) | Animates from the *Point3D* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplinePointKeyFrame](/Gui.Animation/_SplinePointKeyFrame.md) | Animates from the *Point* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineRectKeyFrame](/Gui.Animation/_SplineRectKeyFrame.md) | Animates from the *Rect* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineSizeKeyFrame](/Gui.Animation/_SplineSizeKeyFrame.md) | Animates from the *Size* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineThicknessKeyFrame](/Gui.Animation/_SplineThicknessKeyFrame.md) | Animates from the *Thickness* value of the previous key frame to its own *Value* using splined interpolation. |
| [StackPanel](/Gui.Core/_StackPanel.md) | Arranges child elements into a single horizontal or vertical line. |
| [StaticExtension](/Gui.Core/_StaticExtension.md) | Implements a markup extension that returns static field and property references. |
| [StaticResourceExtension](/Gui.Core/_StaticResourceExtension.md) | Implements a markup extension that supports static resource references made from XAML. |
| [StatusBar](/Gui.Core/_StatusBar.md) | Represents a control that displays items and information in a horizontal bar (typically at the bottom) in an application window. |
| [StatusBarItem](/Gui.Core/_StatusBarItem.md) | Represents an item of a [StatusBar](/Gui.Core/_StatusBar.md) control. |
| [StopStoryboard](/Gui.Animation/_StopStoryboard.md) | A trigger action that stops a [Storyboard](/Gui.Animation/_Storyboard.md). |
| [Storyboard](/Gui.Animation/_Storyboard.md) | A container timeline that provides object and property targeting information for its child animations. |
| [StreamGeometry](/Gui.Core/_StreamGeometry.md) | Defines a geometric shape, described using a [StreamGeometryContext](/Gui.Core/_StreamGeometryContext.md) or a SVG command string as described in the [W3C](http://www.w3.org/TR/SVG11/paths.html) specs. |
| [StreamGeometryContext](/Gui.Core/_StreamGeometryContext.md) | Describes a geometry using drawing commands. This class is used with the [StreamGeometry](/Gui.Core/_StreamGeometry.md) class to create a lightweight geometry that does not support data binding, animation, or modification. |
| [StringAnimationBase](/Gui.Animation/_StringAnimationBase.md) | Abstract class that, when implemented, animates a *String* value. |
| [StringAnimationUsingKeyFrames](/Gui.Animation/_StringAnimationUsingKeyFrames.md) | Animates the value of a *String* property along a set of *KeyFrames*. |
| [StringKeyFrame](/Gui.Animation/_StringKeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [StringAnimationUsingKeyFrames](/Gui.Animation/_StringAnimationUsingKeyFrames.md). |
| [StringKeyFrameCollection](/Gui.Animation/_StringKeyFrameCollection.md) | Represents a collection of [StringKeyFrame](/Gui.Animation/_StringKeyFrame.md) objects. |
| [Style](/Gui.Core/_Style.md) | Enables the sharing of properties, resources, and event handlers between instances of a type. |
| [TabControl](/Gui.Core/_TabControl.md) | Represents a control that contains multiple items that share the same space on the screen. |
| [TabItem](/Gui.Core/_TabItem.md) | Represents a selectable item inside a [TabControl](/Gui.Core/_TabControl.md). |
| [TabPanel](/Gui.Core/_TabPanel.md) | Handles the layout of the [TabItem](/Gui.Core/_TabItem.md) objects on a [TabControl](/Gui.Core/_TabControl.md). |
| [TemplateBindingExpression](/Gui.Core/_TemplateBindingExpression.md) | Describes a run-time instance of a [TemplateBindingExtension](/Gui.Core/_TemplateBindingExtension.md). |
| [TemplateBindingExtension](/Gui.Core/_TemplateBindingExtension.md) | Implements a markup extension that supports the binding between the value of a property in a template and the value of some other exposed property on the templated control. |
| [TextBlock](/Gui.Core/_TextBlock.md) | Provides a lightweight control for displaying small amounts of text content. |
| [TextBox](/Gui.Core/_TextBox.md) | Represents a control that can be used to display or edit unformatted text. |
| [TextElement](/Gui.Core/_TextElement.md) | Defines text attached properties. |
| [Texture](/Render.RenderDevice/_Texture.md) | Base class for 2D textures |
| [TextureSource](/Gui.Core/_TextureSource.md) | Defines a [BitmapSource](/Gui.Core/_BitmapSource.md) constructed from a [Texture](/Render.RenderDevice/_Texture.md). |
| [ThicknessAnimation](/Gui.Animation/_ThicknessAnimation.md) | Animates the value of a *Thickness* property between two target values using linear interpolationover a specified *Duration*. |
| [ThicknessAnimationBase](/Gui.Animation/_ThicknessAnimationBase.md) | Abstract class that, when implemented, animates a *Thickness* value. |
| [ThicknessAnimationUsingKeyFrames](/Gui.Animation/_ThicknessAnimationUsingKeyFrames.md) | Animates the value of a *Thickness* property along a set of *KeyFrames*. |
| [ThicknessKeyFrame](/Gui.Animation/_ThicknessKeyFrame.md) | Defines an animation segment with its own target value and interpolation method for a [BooleanAnimationUsingKeyFrames](/Gui.Animation/_BooleanAnimationUsingKeyFrames.md). |
| [ThicknessKeyFrameCollection](/Gui.Animation/_ThicknessKeyFrameCollection.md) | Represents a collection of [ThicknessKeyFrame](/Gui.Animation/_ThicknessKeyFrame.md) objects. |
| [Thumb](/Gui.Core/_Thumb.md) | Represents a control that can be dragged by the user. |
| [TickBar](/Gui.Core/_TickBar.md) | Represents a control that draws a set of tick marks for a [Slider](/Gui.Core/_Slider.md) control. |
| [TileBrush](/Gui.Core/_TileBrush.md) | Describes a way to paint a region by using one or more tiles. |
| [TimeSpan](/Gui.Animation/_TimeSpan.md) | Represents a time interval. |
| [Timeline](/Gui.Animation/_Timeline.md) | Defines a segment of time. |
| [TimelineGroup](/Gui.Animation/_TimelineGroup.md) | Abstract class that, when implemented represents a [Timeline](/Gui.Animation/_Timeline.md) that may contain a collection of child [Timeline](/Gui.Animation/_Timeline.md) objects. |
| [ToggleButton](/Gui.Core/_ToggleButton.md) | Base class for button controls that can switch states. |
| [ToolBar](/Gui.Core/_ToolBar.md) | Provides a container for a group of commands or controls. |
| [ToolBarOverflowPanel](/Gui.Core/_ToolBarOverflowPanel.md) | Used to arrange overflow [ToolBar](/Gui.Core/_ToolBar.md) items. |
| [ToolBarPanel](/Gui.Core/_ToolBarPanel.md) | Arranges [ToolBar](/Gui.Core/_ToolBar.md) items inside a [ToolBar](/Gui.Core/_ToolBar.md). |
| [ToolBarTray](/Gui.Core/_ToolBarTray.md) | Represents the container that handles the layout of a [ToolBar](/Gui.Core/_ToolBar.md). |
| [ToolTip](/Gui.Core/_ToolTip.md) | Represents a control that creates a pop-up window that displays information for an element in the interface. |
| [ToolTipService](/Gui.Core/_ToolTipService.md) | Represents a service that provides properties and events to control the display and behavior of tooltips. |
| [Track](/Gui.Core/_Track.md) | Represents a control primitive that handles the positioning and sizing of a [Thumb](/Gui.Core/_Thumb.md) control and two [RepeatButton](/Gui.Core/_RepeatButton.md) controls that are used to set a Value. |
| [Transform](/Gui.Core/_Transform.md) | Defines functionality that enables transformations in a 2D plane. |
| [Transform3D](/Gui.Core/_Transform3D.md) | Provides a base class for all three-dimensional transformations, including translation, rotation, and scale transformations. |
| [TransformGroup](/Gui.Core/_TransformGroup.md) | Represents a composite [Transform](/Gui.Core/_Transform.md) composed of other [Transform](/Gui.Core/_Transform.md) objects. |
| [TranslateTransform](/Gui.Core/_TranslateTransform.md) | Translates an object in the 2D coordinate system. |
| [TreeView](/Gui.Core/_TreeView.md) | Represents a control that displays hierarchical data in a tree structure that has items that can expand and collapse. |
| [TreeViewItem](/Gui.Core/_TreeViewItem.md) | Implements a selectable item in a [TreeView](/Gui.Core/_TreeView.md) control. |
| [Trigger](/Gui.Core/_Trigger.md) | Represents a trigger that applies property values or performs actions conditionally. |
| [TriggerAction](/Gui.Core/_TriggerAction.md) | Describes an action to perform for a trigger. |
| [TypeExtension](/Gui.Core/_TypeExtension.md) | Implements a markup extension that returns a *Type* based on a string input. |
| [Typography](/Gui.Core/_Typography.md) | Provides access to a rich set of OpenType typography properties. |
| [UIElement](/Gui.Core/_UIElement.md) | Provides a starting point for element layout characteristics, and also exposes virtual methods that derived classes can override, which can influence the layout rendering behavior of the element and its child elements. |
| [UIElementCollection](/Gui.Core/_UIElementCollection.md) | Represents an ordered collection of [UIElement](/Gui.Core/_UIElement.md) child elements. |
| [UIPropertyMetadata](/Gui.Core/_UIPropertyMetadata.md) | Provides property metadata for non-framework properties that do have rendering/user interface impact at the core level. |
| [Underline](/Gui.Core/_Underline.md) | An inline-level flow content element which causes content to render with an underlined text decoration. |
| [UniformGrid](/Gui.Core/_UniformGrid.md) | Provides a way to arrange content in a grid where all the cells in the grid have the same size. |
| [Uri](/Gui.Providers/_Uri.md) | Provides a representation of a uniform resource identifier and easy access to parts of the URI. |
| [UserControl](/Gui.Core/_UserControl.md) | Provides a simple way to create a composition of controls. |
| [ValueTargetProvider](/Gui.Core/_ValueTargetProvider.md) | Provides useful information during [MarkupExtension](/Gui.Core/_MarkupExtension.md) *ProvideValue* calls. |
| [Viewbox](/Gui.Core/_Viewbox.md) | Defines a content decorator that can stretch and scale a single child to fill the available space. |
| [VirtualizationCacheLength](/Gui.Core/_VirtualizationCacheLength.md) | Represents the measurements for the *VirtualizingPanel.CacheLength* attached property. |
| [VirtualizingPanel](/Gui.Core/_VirtualizingPanel.md) | Base class that provides access to information that is useful for implementing virtualization. |
| [VirtualizingStackPanel](/Gui.Core/_VirtualizingStackPanel.md) | Arranges and virtualizes content on a single line that is oriented either horizontally or vertically. |
| [VirtualizingWrapPanel](/Gui.Core/_VirtualizingWrapPanel.md) | A high-performance [WrapPanel](/Gui.Core/_WrapPanel.md) that supports UI virtualization, designed for use in both horizontal and vertical layouts. |
| [Visual](/Gui.Core/_Visual.md) | Provides rendering support, which includes hit testing, coordinate transformation, and bounding box calculations. |
| [VisualBrush](/Gui.Core/_VisualBrush.md) | Paints an area with a [Visual](/Gui.Core/_Visual.md). |
| [VisualCollection](/Gui.Core/_VisualCollection.md) | Represents an ordered collection of [Visual](/Gui.Core/_Visual.md) objects. |
| [VisualState](/Gui.Animation/_VisualState.md) | Represents the visual appearance of the control when it is in a specific state. |
| [VisualStateGroup](/Gui.Animation/_VisualStateGroup.md) | Contains mutually exclusive [VisualState](/Gui.Animation/_VisualState.md) objects and [VisualTransition](/Gui.Animation/_VisualTransition.md) objects that are used to go from one state to another. |
| [VisualStateManager](/Gui.Animation/_VisualStateManager.md) | Manages states and the logic for transitioning between states for controls. |
| [VisualTransition](/Gui.Animation/_VisualTransition.md) | Represents the visual behavior that occurs when the control transitions from one state to another. |
| [VisualTreeHelper](/Gui.Core/_VisualTreeHelper.md) | Provides utility methods that perform common tasks involving nodes in a visual tree. |
| [WrapPanel](/Gui.Core/_WrapPanel.md) | Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box. |

# NoesisApp Namespace

| Class | Description |
| --- | --- |
| [Application](/App.ApplicationLauncher/_Application.md) | Encapsulates a NoesisGUI application. |
| [AttachableCollection](/App.Interactivity/_AttachableCollection.md) | Represents a collection of IAttachedObject with a shared *AssociatedObject* and provides change notifications to its contents when that *AssociatedObject* changes. |
| [AttachableObject](/App.Interactivity/_AttachableObject.md) | Represents the base class for specifying attachable objects. |
| [BackgroundEffectBehavior](/App.Interactivity/_BackgroundEffectBehavior.md) | Applies an effect to the contents beneath the associated object. |
| [Behavior](/App.Interactivity/_Behavior.md) | Represents the base class for specifying *Behaviors* for a [DependencyObject](/Gui.DependencySystem/_DependencyObject.md). |
| [BehaviorCollection](/App.Interactivity/_BehaviorCollection.md) | Represents a collection of behaviors with a shared *AssociatedObject* and provides change notifications to its contents when that *AssociatedObject* changes. |
| [BehaviorT](/App.Interactivity/_BehaviorT.md) | Templatized base class for *Behaviors*. |
| [BoxShadow](/App.Shaders/_BoxShadow.md) | A box for rendering blurred rounded rectangles. |
| [ChangePropertyAction](/App.Interactivity/_ChangePropertyAction.md) | An action that will change a property to a specified value when invoked. |
| [CollectionFilterBehavior](/App.Interactivity/_CollectionFilterBehavior.md) | A behavior that filters a collection depending on the supplied Predicate object. |
| [CollectionSortBehavior](/App.Interactivity/_CollectionSortBehavior.md) | A behavior that sorts a collection depending on the supplied Comparer object. |
| [ComparisonCondition](/App.Interactivity/_ComparisonCondition.md) | Represents one ternary condition: *left operand*, *operator*, *right operand*. Used as condition in the list of conditions on a [ConditionalExpression](/App.Interactivity/_ConditionalExpression.md). |
| [ConditionBehavior](/App.Interactivity/_ConditionBehavior.md) | A behavior that attaches to a trigger and controls the conditions to fire the actions. |
| [ConditionalExpression](/App.Interactivity/_ConditionalExpression.md) | Represents a conditional expression that is set on a *ConditionBehavior.Condition* property. Contains a list of conditions that gets evaluated in order. |
| [ConicGradientBrush](/App.Shaders/_ConicGradientBrush.md) | Creates an pattern consisting of a gradient with color transitions rotated around a center point |
| [ControlStoryboardAction](/App.Interactivity/_ControlStoryboardAction.md) | An action that will change the state of a targeted storyboard when invoked. |
| [CrossFadeBrush](/App.Shaders/_CrossFadeBrush.md) | Interpolates between two images. |
| [DataEventTrigger](/App.Interactivity/_DataEventTrigger.md) | Represents a trigger which fires when an event is raised on an object. Can be used to trigger from events on the data context, as opposed to a standard [EventTrigger](/App.Interactivity/_EventTrigger.md) which uses routed events on a [FrameworkElement](/Gui.Core/_FrameworkElement.md). |
| [DataTrigger](/App.Interactivity/_DataTrigger.md) | Represents a trigger that performs actions when the bound data meets a specified condition. |
| [DirectionalBlurEffect](/App.Shaders/_DirectionalBlurEffect.md) | Blurs an object along a specific angle, to create a blurred streaking effect. |
| [EventTrigger](/App.Interactivity/_EventTrigger.md) | A trigger that listens for a specified event on its source and fires when that event is raised. |
| [EventTriggerBase](/App.Interactivity/_EventTriggerBase.md) | Represents a trigger that can listen to an object other than its AssociatedObject. |
| [EventTriggerBaseT](/App.Interactivity/_EventTriggerBaseT.md) | Templatized base class for EventTriggers. |
| [FilterPredicate](/App.Interactivity/_FilterPredicate.md) | Base class for Filter predicate object used by [CollectionFilterBehavior](/App.Interactivity/_CollectionFilterBehavior.md). |
| [GamepadTrigger](/App.Interactivity/_GamepadTrigger.md) | A [Trigger](/Gui.Core/_Trigger.md) that is triggered by a specified gamepad button. |
| [GoToStateAction](/App.Interactivity/_GoToStateAction.md) | An action that will transition a [FrameworkElement](/Gui.Core/_FrameworkElement.md) to a specified [VisualState](/Gui.Animation/_VisualState.md) when invoked. |
| [Interaction](/App.Interactivity/_Interaction.md) | Manages a collection of behaviors and triggers that expand the object functionality from XAML. |
| [InvokeCommandAction](/App.Interactivity/_InvokeCommandAction.md) | Executes the specified *ICommand* when invoked. |
| [KeyTrigger](/App.Interactivity/_KeyTrigger.md) | A [Trigger](/Gui.Core/_Trigger.md) that is triggered by a keyboard event. If *Key* and *Modifiers* are detected, it fires. |
| [LaunchUriOrFileAction](/App.Interactivity/_LaunchUriOrFileAction.md) | An action that will launch a process to open a file or uri. |
| [LineDecorationBehavior](/App.Interactivity/_LineDecorationBehavior.md) | Renders a line decoration on the associated [TextBlock](/Gui.Core/_TextBlock.md). |
| [LoadContentAction](/App.Interactivity/_LoadContentAction.md) | An action that will set the Content of the target [ContentControl](/Gui.Core/_ContentControl.md) by loading a xaml. |
| [LocExtension](/App.ApplicationLauncher/_LocExtension.md) | Implements a markup extension that supports references to a localization [ResourceDictionary](/Gui.Core/_ResourceDictionary.md). |
| [MediaElement](/App.MediaElement/_MediaElement.md) | Represents a control that contains audio and/or video. |
| [MediaPlayer](/App.MediaElement/_MediaPlayer.md) | Abstract class for the implementation of audio/video in a [MediaElement](/App.MediaElement/_MediaElement.md). |
| [MessageBox](/App.ApplicationLauncher/_MessageBox.md) | Displays a message box by calling the static *Show* method. The callback gets called when the dialog is closed indicating which button was pressed as result. |
| [MonochromeBrush](/App.Shaders/_MonochromeBrush.md) | [BrushShader](/Gui.Core/_BrushShader.md) that turns an image into a monochrome color |
| [MouseDragElementBehavior](/App.Interactivity/_MouseDragElementBehavior.md) | Moves the attached element in response to mouse drag gestures on the element. |
| [MoveFocusAction](/App.Interactivity/_MoveFocusAction.md) | An action that will try move focus in the specified direction. |
| [PauseMediaAction](/App.Interactivity/_PauseMediaAction.md) | Pauses a media element. |
| [PinchEffect](/App.Shaders/_PinchEffect.md) | [Effect](/Gui.Core/_Effect.md) to warp or pinch a specific area in a visual. |
| [PixelateEffect](/App.Shaders/_PixelateEffect.md) | [ShaderEffect](/Gui.Core/_ShaderEffect.md) that pixelates a visual. |
| [PlasmaBrush](/App.Shaders/_PlasmaBrush.md) | [BrushShader](/Gui.Core/_BrushShader.md) for old school plasma effect. |
| [PlayMediaAction](/App.Interactivity/_PlayMediaAction.md) | Plays a media element. |
| [PlaySoundAction](/App.Interactivity/_PlaySoundAction.md) | An action that will play a sound to completion. |
| [PropertyChangedTrigger](/App.Interactivity/_PropertyChangedTrigger.md) | Represents a trigger that performs actions when the bound data changes. |
| [RemoveElementAction](/App.Interactivity/_RemoveElementAction.md) | An action that will remove the targeted element from the tree when invoked. |
| [RewindMediaAction](/App.Interactivity/_RewindMediaAction.md) | Seeks a media element to position 0. |
| [RichText](/App.ApplicationLauncher/_RichText.md) | Adds a *Text* attached property for [TextBlock](/Gui.Core/_TextBlock.md) which formats [BBCode](https://www.bbcode.org/reference.php) into Inlines. |
| [RiveControl](/App.RiveBase/_RiveControl.md) | Renders a [Rive](https://rive.app/) scene. |
| [RiveInput](/App.RiveBase/_RiveInput.md) | Represents an input value for the [RiveControl](/App.RiveBase/_RiveControl.md) state machine. |
| [RiveRun](/App.RiveBase/_RiveRun.md) | Represents a text run in the [RiveControl](/App.RiveBase/_RiveControl.md) scene. |
| [RiveTriggerAction](/App.Rive/_RiveTriggerAction.md) | An action that will fire a trigger in a [RiveControl](/App.RiveBase/_RiveControl.md). |
| [SaturationEffect](/App.Shaders/_SaturationEffect.md) | Use this effect to alter the saturation of an image. |
| [SelectAction](/App.Interactivity/_SelectAction.md) | An action that will set *Selector.IsSelected* property to true on the asssociated object. |
| [SelectAllAction](/App.Interactivity/_SelectAllAction.md) | An action that will select all the text on a text control. |
| [SetFocusAction](/App.Interactivity/_SetFocusAction.md) | An action that will try to focus the associated element. |
| [SortComparer](/App.Interactivity/_SortComparer.md) | Base class for Comparer object used by [CollectionSortBehavior](/App.Interactivity/_CollectionSortBehavior.md). It compares 2 items. |
| [StopMediaAction](/App.Interactivity/_StopMediaAction.md) | Stops a media element. |
| [StoryboardAction](/App.Interactivity/_StoryboardAction.md) | An abstract action class that provides the ability to target a [Storyboard](/Gui.Animation/_Storyboard.md). |
| [StoryboardCompletedTrigger](/App.Interactivity/_StoryboardCompletedTrigger.md) | A trigger that listens for the completion of a [Storyboard](/Gui.Animation/_Storyboard.md). |
| [StoryboardTrigger](/App.Interactivity/_StoryboardTrigger.md) | An abstract trigger class that provides the ability to target a [Storyboard](/Gui.Animation/_Storyboard.md). |
| [StringFilterPredicate](/App.Interactivity/_StringFilterPredicate.md) | Predicate that matches a filter string against item text representation. |
| [StringSortComparer](/App.Interactivity/_StringSortComparer.md) | Compares the text representation of two items for sorting. |
| [StyleInteraction](/App.Interactivity/_StyleInteraction.md) | Allows setting a collection of *Interactivity* behaviors and triggers in a [Style](/Gui.Core/_Style.md), so they are applied to all instances of the styled control. |
| [TargetedTriggerAction](/App.Interactivity/_TargetedTriggerAction.md) | Represents an action that can be targeted to affect an object other than its *AssociatedObject*. |
| [TargetedTriggerActionT](/App.Interactivity/_TargetedTriggerActionT.md) | Templatized base class for [TargetedTriggerAction](/App.Interactivity/_TargetedTriggerAction.md). |
| [TimerTrigger](/App.Interactivity/_TimerTrigger.md) | A trigger that is triggered by a specified event and fires after a delay. |
| [TintEffect](/App.Shaders/_TintEffect.md) | This effect tints the source image by multiplying the source image by the specified color |
| [TranslateZoomRotateBehavior](/App.Interactivity/_TranslateZoomRotateBehavior.md) | Moves the attached element in response to mouse drag and touch gestures on the element. |
| [TriggerAction](/App.Interactivity/_TriggerAction.md) | Represents an attachable object that encapsulates a unit of functionality. |
| [TriggerActionCollection](/App.Interactivity/_TriggerActionCollection.md) | Represents a collection of actions with a shared *AssociatedObject* and provides change notifications to its contents when that *AssociatedObject* changes. |
| [TriggerActionT](/App.Interactivity/_TriggerActionT.md) | Templatized base class for [TriggerAction](/App.Interactivity/_TriggerAction.md). |
| [TriggerBase](/App.Interactivity/_TriggerBase.md) | Represents an object that can invoke *Actions* conditionally. |
| [TriggerBaseT](/App.Interactivity/_TriggerBaseT.md) | Templatized base class for [TriggerBase](/App.Interactivity/_TriggerBase.md). |
| [TriggerCollection](/App.Interactivity/_TriggerCollection.md) | Represents a collection of triggers with a shared *AssociatedObject* and provides change notifications to its contents when that *AssociatedObject* changes. |
| [VignetteEffect](/App.Shaders/_VignetteEffect.md) | Fades the input image at the edges to a user-set color. |
| [WavesBrush](/App.Shaders/_WavesBrush.md) | [BrushShader](/Gui.Core/_BrushShader.md) that paints a PSP wavy background effect. |
| [Window](/App.ApplicationLauncher/_Window.md) | Provides the ability to create, configure, show, and manage the lifetime of windows. |