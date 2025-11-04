# Class Hierarchy

This section of the documentation contains details of the *API* that *NoesisGUI* provides. Supported classes are described with their *Methods*, *Properties* and *Events* in a language-independent way that matches the implementation for each available language like C++ or C#. The *API* is grouped into two namespaces, *Noesis* with the core functionality of the framework and [NoesisApp](https://www.noesisengine.com/docs/Gui.Core.ApplicationTutorial.html) used by all our examples and tutorials. Most clients will only use the *Noesis* namespace and will take *NoesisApp* source code as a reference sample.

## Table of Contents

- [Noesis Namespace](#noesis-namespace)
- [NoesisApp Namespace](#noesisapp-namespace)

## Noesis Namespace

| Class | Description |
|-------|-------------|
| [Adorner](https://www.noesisengine.com/docs/Gui.Core._Adorner.html) | Abstract class that represents a [FrameworkElement](https://www.noesisengine.com/docs/Gui.Core._FrameworkElement.html) that decorates another element. |
| [AdornerDecorator](https://www.noesisengine.com/docs/Gui.Core._AdornerDecorator.html) | Provides an adorner layer for elements beneath it in the visual tree. |
| [AdornerLayer](https://www.noesisengine.com/docs/Gui.Core._AdornerLayer.html) | Represents a surface for rendering adorners. An adorner layer is guaranteed to be at a higher Z-order than the elements being adorned, so adorners are always rendered on top of the adorned elements. |
| [AlternationConverter](https://www.noesisengine.com/docs/Gui.Core._AlternationConverter.html) | Converts an integer to/from an object by applying the integer as an index to a list of objects. |
| [Animatable](https://www.noesisengine.com/docs/Gui.Core._Animatable.html) | Abstract class that provides animation support. |
| [AnimationClock](https://www.noesisengine.com/docs/Gui.Animation._AnimationClock.html) | Maintains the run-time state of an [AnimationTimeline](https://www.noesisengine.com/docs/Gui.Animation._AnimationTimeline.html) and processes its output values. |
| [AnimationTimeline](https://www.noesisengine.com/docs/Gui.Animation._AnimationTimeline.html) | Defines a segment of time over which output values are produced. These values are used to animate a target property. |
| [ApplicationCommands](https://www.noesisengine.com/docs/Gui.Core._ApplicationCommands.html) | Provides a standard set of application related commands. |
| [ArcSegment](https://www.noesisengine.com/docs/Gui.Core._ArcSegment.html) | Represents an elliptical arc between two points. |
| [BackEase](https://www.noesisengine.com/docs/Gui.Animation._BackEase.html) | Represents an easing function that retracts the motion of an animation slightly before it begins to animate in the path indicated. |
| [BaseBinding](https://www.noesisengine.com/docs/Gui.Core._BaseBinding.html) | Defines the common features for [Binding](https://www.noesisengine.com/docs/Gui.Core._Binding.html). |
| [BaseBindingExpression](https://www.noesisengine.com/docs/Gui.Core._BaseBindingExpression.html) | Represents the base class for all [Binding](https://www.noesisengine.com/docs/Gui.Core._Binding.html) Expressions. |
| [BaseButton](https://www.noesisengine.com/docs/Gui.Core._BaseButton.html) | Represents the base class for all button controls. |
| [BaseCommand](https://www.noesisengine.com/docs/Gui.Core._BaseCommand.html) | Base class for commands. |
| [BaseDefinition](https://www.noesisengine.com/docs/Gui.Core._BaseDefinition.html) | Defines the functionality required to support a shared-size group that is used by the ColumnDefinitionCollection and RowDefinitionCollection classes. |
| [BaseDictionary](https://www.noesisengine.com/docs/Gui.Core._BaseDictionary.html) | Base class for dictionaries. |
| [BaseFreezableCollection](https://www.noesisengine.com/docs/Gui.Core._BaseFreezableCollection.html) | Base class implementation for a [FreezableCollection](https://www.noesisengine.com/docs/Gui.Core._FreezableCollection.html). |
| [BaseGridViewRowPresenter](https://www.noesisengine.com/docs/Gui.Controls._BaseGridViewRowPresenter.html) | Represents the base class for classes that define the layout for a row of data where different data items are displayed in different columns. |
| [BaseKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._BaseKeyFrame.html) | Base class for KeyFrame classes |
| [BaseMenu](https://www.noesisengine.com/docs/Gui.Core._BaseMenu.html) | Represents a control that defines choices for users to select. |
| [BaseMultiValueConverter](https://www.noesisengine.com/docs/Gui.Core._BaseMultiValueConverter.html) | Base class for value converters used in MultiBindings. |
| [BaseSetter](https://www.noesisengine.com/docs/Gui.Core._BaseSetter.html) | Represents the base class for value setters. |
| [BaseTextBox](https://www.noesisengine.com/docs/Gui.Core._BaseTextBox.html) | An abstract base class that provides functionality for text editing controls. |
| [BaseTrigger](https://www.noesisengine.com/docs/Gui.Core._BaseTrigger.html) | Represents the base class for specifying a conditional value within a [Style](https://www.noesisengine.com/docs/Gui.Core._Style.html) object. |
| [BaseValueConverter](https://www.noesisengine.com/docs/Gui.Core._BaseValueConverter.html) | Base class for value converters used in Bindings. |
| [BaseView](https://www.noesisengine.com/docs/Gui.Controls._BaseView.html) | Represents the base class for views that define the appearance of data in a [ListView](https://www.noesisengine.com/docs/Gui.Controls._ListView.html) control. |
| [BeginStoryboard](https://www.noesisengine.com/docs/Gui.Animation._BeginStoryboard.html) | A trigger action that begins a [Storyboard](https://www.noesisengine.com/docs/Gui.Animation._Storyboard.html) and distributes its animations to their targeted objects and properties. |
| [BezierSegment](https://www.noesisengine.com/docs/Gui.Core._BezierSegment.html) | Represents a cubic Bezier curve drawn between two points. |
| [Binding](https://www.noesisengine.com/docs/Gui.Core._Binding.html) | Provides high-level access to the definition of a binding, which connects the properties of binding target objects and any data source. |
| [BindingExpression](https://www.noesisengine.com/docs/Gui.Core._BindingExpression.html) | Contains information about a single instance of a [Binding](https://www.noesisengine.com/docs/Gui.Core._Binding.html). |
| [BindingOperations](https://www.noesisengine.com/docs/Gui.Core._BindingOperations.html) | Provides static methods to manipulate bindings. |
| [BitmapImage](https://www.noesisengine.com/docs/Gui.Core._BitmapImage.html) | Provides a [BitmapSource](https://www.noesisengine.com/docs/Gui.Core._BitmapSource.html) created from an image file located at the specifed [Uri](https://www.noesisengine.com/docs/Gui.Providers._Uri.html). |
| [BitmapSource](https://www.noesisengine.com/docs/Gui.Core._BitmapSource.html) | Represents a single, constant set of pixels at a certain size and resolution. |
| [BlurEffect](https://www.noesisengine.com/docs/Gui.Core._BlurEffect.html) | A bitmap effect that blurs the target texture. |
| [Bold](https://www.noesisengine.com/docs/Gui.Core._Bold.html) | An inline-level flow content element which causes content to render with a *bold* font weight. |
| [BooleanAnimationBase](https://www.noesisengine.com/docs/Gui.Animation._BooleanAnimationBase.html) | Abstract class that, when implemented, animates a *Boolean* value. |
| [BooleanAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._BooleanAnimationUsingKeyFrames.html) | Animates the value of a *Boolean* property along a set of *KeyFrames*. |
| [BooleanKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._BooleanKeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [BooleanAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._BooleanAnimationUsingKeyFrames.html). |
| [BooleanKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._BooleanKeyFrameCollection.html) | Represents a collection of [BooleanKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._BooleanKeyFrame.html) objects. |
| [BooleanToVisibilityConverter](https://www.noesisengine.com/docs/Gui.Core._BooleanToVisibilityConverter.html) | Represents the converter that converts *Boolean* values to and from *Visibility* enumeration values. |
| [Border](https://www.noesisengine.com/docs/Gui.Core._Border.html) | Draws a border, background, or both around another element. |
| [BounceEase](https://www.noesisengine.com/docs/Gui.Animation._BounceEase.html) | Represents an easing function that creates an animated bouncing effect. |
| [Brush](https://www.noesisengine.com/docs/Gui.Core._Brush.html) | Defines objects used to paint graphical objects. Classes that derive from [Brush](https://www.noesisengine.com/docs/Gui.Core._Brush.html) describe how the area is painted. |
| [BrushShader](https://www.noesisengine.com/docs/Gui.Core._BrushShader.html) | Provides a custom brush by using a pixel shader. |
| [Brushes](https://www.noesisengine.com/docs/Gui.Core._Brushes.html) | Declares a set of predefined [SolidColorBrush](https://www.noesisengine.com/docs/Gui.Core._SolidColorBrush.html) objects. |
| [BulletDecorator](https://www.noesisengine.com/docs/Gui.Core._BulletDecorator.html) | Represents a layout control that aligns a bullet and another visual object. |
| [Button](https://www.noesisengine.com/docs/Gui.Core._Button.html) | Represents a push button which reacts to the *Click* event. |
| [Canvas](https://www.noesisengine.com/docs/Gui.Core._Canvas.html) | Defines an area within which you can explicitly position child elements by using coordinates that are relative to the [Canvas](https://www.noesisengine.com/docs/Gui.Core._Canvas.html) area. |
| [CheckBox](https://www.noesisengine.com/docs/Gui.Core._CheckBox.html) | Represents a control that a user can select and clear. |
| [CircleEase](https://www.noesisengine.com/docs/Gui.Animation._CircleEase.html) | Represents an easing function that creates an animation that accelerates and/or decelerates using a circular function. |
| [Clock](https://www.noesisengine.com/docs/Gui.Animation._Clock.html) | Maintains run-time timing state for a [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html). |
| [ClockGroup](https://www.noesisengine.com/docs/Gui.Animation._ClockGroup.html) | An assemblage of [Clock](https://www.noesisengine.com/docs/Gui.Animation._Clock.html) types with behavior based off of a [TimelineGroup](https://www.noesisengine.com/docs/Gui.Animation._TimelineGroup.html). |
| [Collection](https://www.noesisengine.com/docs/Gui.Core._Collection.html) | Represents a generic collection of objects that can be individually accessed by index. |
| [CollectionView](https://www.noesisengine.com/docs/Gui.Core._CollectionView.html) | Represents a view for grouping, sorting, filtering, and navigating a data collection. |
| [CollectionViewSource](https://www.noesisengine.com/docs/Gui.Core._CollectionViewSource.html) | Proxy of [CollectionView](https://www.noesisengine.com/docs/Gui.Core._CollectionView.html) to be used from XAML files. |
| [ColorAnimation](https://www.noesisengine.com/docs/Gui.Animation._ColorAnimation.html) | Animates the value of a *Color* property between two target values using linear interpolation over a specified *Duration*. |
| [ColorAnimationBase](https://www.noesisengine.com/docs/Gui.Animation._ColorAnimationBase.html) | Abstract class that, when implemented, animates a *Color* value. |
| [ColorAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._ColorAnimationUsingKeyFrames.html) | Animates the value of a *Color* property along a set of *KeyFrames*. |
| [ColorKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._ColorKeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [ColorAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._ColorAnimationUsingKeyFrames.html). |
| [ColorKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._ColorKeyFrameCollection.html) | Represents a collection of [ColorKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._ColorKeyFrame.html) objects. |
| [Colors](https://www.noesisengine.com/docs/Gui.Core._Colors.html) | Implements a set of predefined colors. |
| [ColumnDefinition](https://www.noesisengine.com/docs/Gui.Core._ColumnDefinition.html) | Defines column-specific properties that apply to [Grid](https://www.noesisengine.com/docs/Gui.Core._Grid.html) elements. |
| [CombinedGeometry](https://www.noesisengine.com/docs/Gui.Core._CombinedGeometry.html) | Represents a 2D geometric shape defined by the combination of two [Geometry](https://www.noesisengine.com/docs/Gui.Core._Geometry.html) objects. |
| [ComboBox](https://www.noesisengine.com/docs/Gui.Core._ComboBox.html) | Represents a selection control with a drop-down list that can be shown or hidden by clicking the arrow on the control. |
| [ComboBoxItem](https://www.noesisengine.com/docs/Gui.Core._ComboBoxItem.html) | Implements a selectable item inside a [ComboBox](https://www.noesisengine.com/docs/Gui.Core._ComboBox.html). |
| [CommandBinding](https://www.noesisengine.com/docs/Gui.Core._CommandBinding.html) | Binds a [RoutedCommand](https://www.noesisengine.com/docs/Gui.Core._RoutedCommand.html) to the event handlers that implement the command. |
| [CommandManager](https://www.noesisengine.com/docs/Gui.Core._CommandManager.html) | Provides command related events and is responsible for managing routed commands execution. |
| [ComponentCommands](https://www.noesisengine.com/docs/Gui.Core._ComponentCommands.html) | Provides a standard set of component related commands. |
| [CompositeTransform](https://www.noesisengine.com/docs/Gui.Core._CompositeTransform.html) | This class lets you apply multiple different transforms to an object. |
| [CompositeTransform3D](https://www.noesisengine.com/docs/Gui.Core._CompositeTransform3D.html) | Represents 3-D scale, rotation, and translate transforms to be applied to an element. |
| [Condition](https://www.noesisengine.com/docs/Gui.Core._Condition.html) | Represents a condition for the [MultiTrigger](https://www.noesisengine.com/docs/Gui.Core._MultiTrigger.html) and the [MultiDataTrigger](https://www.noesisengine.com/docs/Gui.Core._MultiDataTrigger.html), which apply changes to property values based on a set of conditions. |
| [ContentControl](https://www.noesisengine.com/docs/Gui.Core._ContentControl.html) | Represents a control with a single piece of content. |
| [ContentPresenter](https://www.noesisengine.com/docs/Gui.Core._ContentPresenter.html) | Displays the content of [ContentControl](https://www.noesisengine.com/docs/Gui.Core._ContentControl.html). |
| [ContextMenu](https://www.noesisengine.com/docs/Gui.Core._ContextMenu.html) | Represents a pop-up menu that enables a control to expose functionality that is specific to the context of the control. |
| [ContextMenuService](https://www.noesisengine.com/docs/Gui.Core._ContextMenuService.html) | Provides the system implementation for displaying a [ContextMenu](https://www.noesisengine.com/docs/Gui.Core._ContextMenu.html). |
| [Control](https://www.noesisengine.com/docs/Gui.Core._Control.html) | Represents the base class for all user interactive elements. |
| [ControlTemplate](https://www.noesisengine.com/docs/Gui.Core._ControlTemplate.html) | Specifies the visual structure and behavioral aspects of a [Control](https://www.noesisengine.com/docs/Gui.Core._Control.html) that can be shared across multiple instances of the control. |
| [ControllableStoryboardAction](https://www.noesisengine.com/docs/Gui.Animation._ControllableStoryboardAction.html) | Manipulates a [Storyboard](https://www.noesisengine.com/docs/Gui.Animation._Storyboard.html) that has been applied by a [BeginStoryboard](https://www.noesisengine.com/docs/Gui.Animation._BeginStoryboard.html) action. |
| [CroppedBitmap](https://www.noesisengine.com/docs/Gui.Core._CroppedBitmap.html) | Provides an image source that crops another [BitmapSource](https://www.noesisengine.com/docs/Gui.Core._BitmapSource.html). |
| [CubicEase](https://www.noesisengine.com/docs/Gui.Animation._CubicEase.html) | Represents an easing function that creates an animation that accelerates and/or decelerates using the formula f(t) = t<sup>3</sup>. |
| [Cursor](https://www.noesisengine.com/docs/Gui.Core._Cursor.html) | Represents the image used for the mouse pointer. |
| [Cursors](https://www.noesisengine.com/docs/Gui.Core._Cursors.html) | Defines a set of default cursors. |
| [DashStyle](https://www.noesisengine.com/docs/Gui.Core._DashStyle.html) | Represents the sequence of dashes and gaps that will be applied by a [Pen](https://www.noesisengine.com/docs/Gui.Core._Pen.html). |
| [DataObject](https://www.noesisengine.com/docs/Gui.Core._DataObject.html) | Defines a format-independent mechanism for transferring data. |
| [DataTemplate](https://www.noesisengine.com/docs/Gui.Core._DataTemplate.html) | Describes the visual structure of a data object. |
| [DataTemplateSelector](https://www.noesisengine.com/docs/Gui.Core._DataTemplateSelector.html) | Provides a way to choose a [DataTemplate](https://www.noesisengine.com/docs/Gui.Core._DataTemplate.html) based on the data object and the data-bound element. |
| [DataTrigger](https://www.noesisengine.com/docs/Gui.Core._DataTrigger.html) | Represents a trigger that applies property values or performs actions when the bound data meets a specified condition. |
| [Decorator](https://www.noesisengine.com/docs/Gui.Core._Decorator.html) | Provides a base class for elements that apply effects onto or around a single child element, such as [Border](https://www.noesisengine.com/docs/Gui.Core._Border.html) or [Viewbox](https://www.noesisengine.com/docs/Gui.Core._Viewbox.html). |
| [DependencyObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html) | Represents an object that participates in the dependency property system. |
| [DependencyProperty](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyProperty.html) | Represents a dependency property that is registered in the property system. Dependency properties provide support for value expressions, property invalidation and dependent-value coercion, default values, inheritance, data binding, animation, property change notification, and styling. |
| [DiscreteBooleanKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteBooleanKeyFrame.html) | Animates from the *Boolean* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteColorKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteColorKeyFrame.html) | Animates from the *Color* value of the previous key frame to its own *Value* using discrete interpolation. This class is used as part of a [ColorKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._ColorKeyFrameCollection.html) in conjunction with a [ColorAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._ColorAnimationUsingKeyFrames.html) to animate a Color property value along a set of key frames. |
| [DiscreteDoubleKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteDoubleKeyFrame.html) | Animates from the *Single* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteInt16KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteInt16KeyFrame.html) | Animates from the *Int16* value of the previous key frame to its own *Value* using discrete interpolation. This class is used as part of a [Int16KeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._Int16KeyFrameCollection.html) in conjunction with a [Int16AnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Int16AnimationUsingKeyFrames.html) to animate a Int16 property value along a set of key frames. |
| [DiscreteInt32KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteInt32KeyFrame.html) | Animates from the *Int32* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteInt64KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteInt64KeyFrame.html) | Animates from the *Int64* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteMatrixKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteMatrixKeyFrame.html) | Animates from the *Matrix* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteObjectKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteObjectKeyFrame.html) | Animates from the *Object* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscretePoint3DKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscretePoint3DKeyFrame.html) | Animates from the *Point3D* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscretePointKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscretePointKeyFrame.html) | Animates from the *Point* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteRectKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteRectKeyFrame.html) | Animates from the *Rect* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteSizeKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteSizeKeyFrame.html) | Animates from the *Size* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteStringKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteStringKeyFrame.html) | Animates from the *String* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DiscreteThicknessKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteThicknessKeyFrame.html) | Animates from the *Thickness* value of the previous key frame to its own *Value* using discrete interpolation. |
| [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html) | Represents an object with thread affinity. |
| [DockPanel](https://www.noesisengine.com/docs/Gui.Core._DockPanel.html) | Defines an area where you can arrange child elements either horizontally or vertically, relative to each other. |
| [DoubleAnimation](https://www.noesisengine.com/docs/Gui.Animation._DoubleAnimation.html) | Animates the value of a *Float* property between two target values using linear interpolation over a specified *Duration*. |
| [DoubleAnimationBase](https://www.noesisengine.com/docs/Gui.Animation._DoubleAnimationBase.html) | Abstract class that, when implemented, animates a *Float* value. |
| [DoubleAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._DoubleAnimationUsingKeyFrames.html) | Animates the value of a *Double* property along a set of *KeyFrames*. |
| [DoubleKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DoubleKeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [DoubleAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._DoubleAnimationUsingKeyFrames.html). |
| [DoubleKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._DoubleKeyFrameCollection.html) | Represents a collection of [DoubleKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DoubleKeyFrame.html) objects. |
| [DragDrop](https://www.noesisengine.com/docs/Gui.Core._DragDrop.html) | Provides helper methods and fields for initiating drag-and-drop operations. |
| [DrawingContext](https://www.noesisengine.com/docs/Gui.Core._DrawingContext.html) | Describes visual content using draw, push, and pop commands during [UIElement](https://www.noesisengine.com/docs/Gui.Core._UIElement.html) *OnRender*. |
| [DropShadowEffect](https://www.noesisengine.com/docs/Gui.Core._DropShadowEffect.html) | A bitmap effect that paints a drop shadow around the target texture. |
| [Duration](https://www.noesisengine.com/docs/Gui.Animation._Duration.html) | Represents the duration of time that a [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html) is active. |
| [DynamicResourceExtension](https://www.noesisengine.com/docs/Gui.Core._DynamicResourceExtension.html) | Implements a markup extension that supports dynamic resource references made from XAML. |
| [DynamicTextureSource](https://www.noesisengine.com/docs/Gui.Core._DynamicTextureSource.html) | Defines an [ImageSource](https://www.noesisengine.com/docs/Gui.Core._ImageSource.html) implementation based on a dynamic texture. |
| [EasingColorKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._EasingColorKeyFrame.html) | A class that enables you to associate easing functions with a [ColorAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._ColorAnimationUsingKeyFrames.html) key frame animation. |
| [EasingDoubleKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._EasingDoubleKeyFrame.html) | A class that enables you to associate easing functions with a [DoubleAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._DoubleAnimationUsingKeyFrames.html) key frame animation. |
| [EasingFunctionBase](https://www.noesisengine.com/docs/Gui.Animation._EasingFunctionBase.html) | Provides the base class for all the easing functions. You can create your own custom easing functions by inheriting from this class. |
| [EasingInt16KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._EasingInt16KeyFrame.html) | A class that enables you to associate easing functions with a [Int16AnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Int16AnimationUsingKeyFrames.html) key frame animation. |
| [EasingInt32KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._EasingInt32KeyFrame.html) | A class that enables you to associate easing functions with a [Int32AnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Int32AnimationUsingKeyFrames.html) key frame animation. |
| [EasingInt64KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._EasingInt64KeyFrame.html) | A class that enables you to associate easing functions with a [Int64AnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Int64AnimationUsingKeyFrames.html) key frame animation. |
| [EasingPoint3DKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._EasingPoint3DKeyFrame.html) | A class that enables you to associate easing functions with a [Point3DAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Point3DAnimationUsingKeyFrames.html) key frame animation. |
| [EasingPointKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._EasingPointKeyFrame.html) | A class that enables you to associate easing functions with a [PointAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._PointAnimationUsingKeyFrames.html) key frame animation. |
| [EasingRectKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._EasingRectKeyFrame.html) | A class that enables you to associate easing functions with a [RectAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._RectAnimationUsingKeyFrames.html) key frame animation. |
| [EasingSizeKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._EasingSizeKeyFrame.html) | A class that enables you to associate easing functions with a [SizeAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._SizeAnimationUsingKeyFrames.html) key frame animation. |
| [EasingThicknessKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._EasingThicknessKeyFrame.html) | A class that enables you to associate easing functions with a [ThicknessAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._ThicknessAnimationUsingKeyFrames.html) key frame animation. |
| [Effect](https://www.noesisengine.com/docs/Gui.Core._Effect.html) | Provides a custom bitmap effect. |
| [ElasticEase](https://www.noesisengine.com/docs/Gui.Animation._ElasticEase.html) | Represents an easing function that creates an animation that resembles a spring oscillating back and forth until it comes to rest. |
| [Ellipse](https://www.noesisengine.com/docs/Gui.Core._Ellipse.html) | Draws an ellipse. |
| [EllipseGeometry](https://www.noesisengine.com/docs/Gui.Core._EllipseGeometry.html) | Represents the geometry of a circle or ellipse. |
| [EventTrigger](https://www.noesisengine.com/docs/Gui.Core._EventTrigger.html) | Represents a trigger that applies a set of actions in response to an event. |
| [Expander](https://www.noesisengine.com/docs/Gui.Core._Expander.html) | Represents a control that displays a header with a collapsible window to display content. |
| [ExponentialEase](https://www.noesisengine.com/docs/Gui.Animation._ExponentialEase.html) | Represents an easing function that creates an animation that accelerates and/or decelerates using an exponential formula. |
| [Expression](https://www.noesisengine.com/docs/Gui.DependencySystem._Expression.html) | Base implementation for all expressions. |
| [FocusManager](https://www.noesisengine.com/docs/Gui.Core._FocusManager.html) | Provides a set of static methods, attached properties, and events for determining and setting focus scopes and for setting the focused element within the scope. |
| [FontFamily](https://www.noesisengine.com/docs/Gui.Core._FontFamily.html) | Represents a family of related fonts. |
| [FormattedText](https://www.noesisengine.com/docs/Gui.Core._FormattedText.html) | Provides low-level control for drawing text. |
| [FrameworkElement](https://www.noesisengine.com/docs/Gui.Core._FrameworkElement.html) | Provides GUI framework-level features for user interface elements. |
| [FrameworkPropertyMetadata](https://www.noesisengine.com/docs/Gui.Core._FrameworkPropertyMetadata.html) | Reports or applies metadata for a dependency property, specifically adding framework-specific property system characteristics. |
| [FrameworkTemplate](https://www.noesisengine.com/docs/Gui.Core._FrameworkTemplate.html) | Enables the instantiation of a tree of elements for a template. |
| [Freezable](https://www.noesisengine.com/docs/Gui.DependencySystem._Freezable.html) | Defines an object that has a modifiable state and a read-only (frozen) state. |
| [FreezableCollection](https://www.noesisengine.com/docs/Gui.Core._FreezableCollection.html) | Represents a collection of [DependencyObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html), [Freezable](https://www.noesisengine.com/docs/Gui.DependencySystem._Freezable.html), or [Animatable](https://www.noesisengine.com/docs/Gui.Core._Animatable.html) objects. [FreezableCollection](https://www.noesisengine.com/docs/Gui.Core._FreezableCollection.html) is itself an [Animatable](https://www.noesisengine.com/docs/Gui.Core._Animatable.html) type. |
| [Geometry](https://www.noesisengine.com/docs/Gui.Core._Geometry.html) | Classes that derive from this abstract base class define geometric shapes. [Geometry](https://www.noesisengine.com/docs/Gui.Core._Geometry.html) objects can be used for clipping, hit-testing, and rendering 2D graphic data. |
| [GeometryGroup](https://www.noesisengine.com/docs/Gui.Core._GeometryGroup.html) | Represents a composite geometry, composed of other [Geometry](https://www.noesisengine.com/docs/Gui.Core._Geometry.html) objects. |
| [GradientBrush](https://www.noesisengine.com/docs/Gui.Core._GradientBrush.html) | Defines an abstract class that describes a gradient, composed of gradient stops. Classes that inherit from [GradientBrush](https://www.noesisengine.com/docs/Gui.Core._GradientBrush.html) describe different ways of interpreting gradient stops. |
| [GradientStop](https://www.noesisengine.com/docs/Gui.Core._GradientStop.html) | Describes the location and color of a transition point in a gradient. |
| [GradientStopCollection](https://www.noesisengine.com/docs/Gui.Core._GradientStopCollection.html) | Represents a collection of [GradientStop](https://www.noesisengine.com/docs/Gui.Core._GradientStop.html) objects that can be individually accessed by index. |
| [Grid](https://www.noesisengine.com/docs/Gui.Core._Grid.html) | Defines a flexible grid area that consists of columns and rows. |
| [GridLength](https://www.noesisengine.com/docs/Gui.Core._GridLength.html) | Represents the length of elements that explicitly support *Star* unit types. Elements such as [ColumnDefinition](https://www.noesisengine.com/docs/Gui.Core._ColumnDefinition.html) and [RowDefinition](https://www.noesisengine.com/docs/Gui.Core._RowDefinition.html) use this type to describe width and height in order to support variable distribution of available space. |
| [GridSplitter](https://www.noesisengine.com/docs/Gui.Core._GridSplitter.html) | Represents the control that redistributes space between columns or rows of a [Grid](https://www.noesisengine.com/docs/Gui.Core._Grid.html) control. |
| [GridView](https://www.noesisengine.com/docs/Gui.Controls._GridView.html) | Represents a view mode that displays data items in columns for a [ListView](https://www.noesisengine.com/docs/Gui.Controls._ListView.html) control. |
| [GridViewColumn](https://www.noesisengine.com/docs/Gui.Controls._GridViewColumn.html) | Represents a column that displays data. |
| [GridViewColumnHeader](https://www.noesisengine.com/docs/Gui.Controls._GridViewColumnHeader.html) | Represents a column header for a [GridViewColumn](https://www.noesisengine.com/docs/Gui.Controls._GridViewColumn.html). |
| [GridViewHeaderRowPresenter](https://www.noesisengine.com/docs/Gui.Controls._GridViewHeaderRowPresenter.html) | Represents an object that is used to define the layout of a row of column headers. |
| [GridViewRowPresenter](https://www.noesisengine.com/docs/Gui.Controls._GridViewRowPresenter.html) | Represents an object that specifies the layout of a row of data. |
| [GroupBox](https://www.noesisengine.com/docs/Gui.Core._GroupBox.html) | Represents a control that displays a frame around a group of controls with an optional caption. |
| [HeaderedContentControl](https://www.noesisengine.com/docs/Gui.Core._HeaderedContentControl.html) | Provides the base implementation for all controls that contain single content and have a header. |
| [HeaderedItemsControl](https://www.noesisengine.com/docs/Gui.Core._HeaderedItemsControl.html) | Represents a control that contains multiple items and has a header. |
| [HierarchicalDataTemplate](https://www.noesisengine.com/docs/Gui.Core._HierarchicalDataTemplate.html) | Represents a [DataTemplate](https://www.noesisengine.com/docs/Gui.Core._DataTemplate.html) that supports [HeaderedItemsControl](https://www.noesisengine.com/docs/Gui.Core._HeaderedItemsControl.html), such as [TreeViewItem](https://www.noesisengine.com/docs/Gui.Core._TreeViewItem.html) or [MenuItem](https://www.noesisengine.com/docs/Gui.Core._MenuItem.html). |
| [Hyperlink](https://www.noesisengine.com/docs/Gui.Core._Hyperlink.html) | An inline-level flow content element that hosts hyperlinks within flow content. |
| [ISealable](https://www.noesisengine.com/docs/Gui.DependencySystem._ISealable.html) | This interface is shared across [Freezable](https://www.noesisengine.com/docs/Gui.DependencySystem._Freezable.html), [Style](https://www.noesisengine.com/docs/Gui.Core._Style.html) and Template. A sealed object is free-threaded. |
| [Image](https://www.noesisengine.com/docs/Gui.Core._Image.html) | Represents a control that displays an image. |
| [ImageBrush](https://www.noesisengine.com/docs/Gui.Core._ImageBrush.html) | Paints an area with an image. |
| [ImageSource](https://www.noesisengine.com/docs/Gui.Core._ImageSource.html) | Represents an image object that has width and height. |
| [Inline](https://www.noesisengine.com/docs/Gui.Core._Inline.html) | An abstract class that provides a base for all inline flow content elements. |
| [InlineUIContainer](https://www.noesisengine.com/docs/Gui.Core._InlineUIContainer.html) | An inline-level flow content element which enables [UIElement](https://www.noesisengine.com/docs/Gui.Core._UIElement.html) elements (i.e. a [Button](https://www.noesisengine.com/docs/Gui.Core._Button.html)) to be embedded in flow content. |
| [InputBinding](https://www.noesisengine.com/docs/Gui.Core._InputBinding.html) | Represents a binding between an [InputGesture](https://www.noesisengine.com/docs/Gui.Core._InputGesture.html) and a command. |
| [InputGesture](https://www.noesisengine.com/docs/Gui.Core._InputGesture.html) | Abstract class that describes input device gestures. |
| [Int16Animation](https://www.noesisengine.com/docs/Gui.Animation._Int16Animation.html) | Animates the value of a *Int16* property between two 'target values' using linear interpolation over a specified *Duration*. |
| [Int16AnimationBase](https://www.noesisengine.com/docs/Gui.Animation._Int16AnimationBase.html) | Abstract class that, when implemented, animates a *Int16* value. |
| [Int16AnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Int16AnimationUsingKeyFrames.html) | Animates the value of a *Int16* property along a set of *KeyFrames*. |
| [Int16KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._Int16KeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [Int16AnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Int16AnimationUsingKeyFrames.html). |
| [Int16KeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._Int16KeyFrameCollection.html) | Represents a collection of [Int16KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._Int16KeyFrame.html) objects. |
| [Int32Animation](https://www.noesisengine.com/docs/Gui.Animation._Int32Animation.html) | Animates the value of a *Int32* property between two target values using linear interpolation over a specified *Duration*. |
| [Int32AnimationBase](https://www.noesisengine.com/docs/Gui.Animation._Int32AnimationBase.html) | Abstract class that, when implemented, animates a *Int32* value. |
| [Int32AnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Int32AnimationUsingKeyFrames.html) | Animates the value of a *Int32* property along a set of *KeyFrames*. |
| [Int32KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._Int32KeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [Int32AnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Int32AnimationUsingKeyFrames.html). |
| [Int32KeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._Int32KeyFrameCollection.html) | Represents a collection of [Int32KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._Int32KeyFrame.html) objects. |
| [Int64Animation](https://www.noesisengine.com/docs/Gui.Animation._Int64Animation.html) | Animates the value of a *Int64* property between two target values using linear interpolation over a specified *Duration*. |
| [Int64AnimationBase](https://www.noesisengine.com/docs/Gui.Animation._Int64AnimationBase.html) | Abstract class that, when implemented, animates a *Int64* value. |
| [Int64AnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Int64AnimationUsingKeyFrames.html) | Animates the value of a *Int64* property along a set of *KeyFrames*. |
| [Int64KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._Int64KeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [Int64AnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Int64AnimationUsingKeyFrames.html). |
| [Int64KeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._Int64KeyFrameCollection.html) | Represents a collection of [Int64KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._Int64KeyFrame.html) objects. |
| [Italic](https://www.noesisengine.com/docs/Gui.Core._Italic.html) | An inline-level flow content element that causes content to render with an italic font style. |
| [ItemCollection](https://www.noesisengine.com/docs/Gui.Core._ItemCollection.html) | Holds the list of items that constitute the content of an [ItemsControl](https://www.noesisengine.com/docs/Gui.Core._ItemsControl.html). |
| [ItemContainerGenerator](https://www.noesisengine.com/docs/Gui.Core._ItemContainerGenerator.html) | Generates the user interface on behalf of its host, such as an [ItemsControl](https://www.noesisengine.com/docs/Gui.Core._ItemsControl.html). |
| [ItemsControl](https://www.noesisengine.com/docs/Gui.Core._ItemsControl.html) | Represents a control that can be used to present a collection of items. |
| [ItemsPanelTemplate](https://www.noesisengine.com/docs/Gui.Core._ItemsPanelTemplate.html) | Specifies the panel that the [ItemsPresenter](https://www.noesisengine.com/docs/Gui.Core._ItemsPresenter.html) creates for the layout of the items of an [ItemsControl](https://www.noesisengine.com/docs/Gui.Core._ItemsControl.html). |
| [ItemsPresenter](https://www.noesisengine.com/docs/Gui.Core._ItemsPresenter.html) | Used within the template of an ItemControl to specify the place in the control's visual tree where the ItemsPanel defined by the [ItemsControl](https://www.noesisengine.com/docs/Gui.Core._ItemsControl.html) is to be added. |
| [KeyBinding](https://www.noesisengine.com/docs/Gui.Core._KeyBinding.html) | Binds a [KeyGesture](https://www.noesisengine.com/docs/Gui.Core._KeyGesture.html) to a Command. |
| [KeyGesture](https://www.noesisengine.com/docs/Gui.Core._KeyGesture.html) | Defines a keyboard combination that can be used to invoke a command. |
| [KeySpline](https://www.noesisengine.com/docs/Gui.Animation._KeySpline.html) | This class is used by a spline key frame to define animation progress. |
| [KeyTime](https://www.noesisengine.com/docs/Gui.Animation._KeyTime.html) | Specifies the precise timing when a particular key frame should take place |
| [Keyboard](https://www.noesisengine.com/docs/Gui.Core._Keyboard.html) | Represents the keyboard device. |
| [KeyboardNavigation](https://www.noesisengine.com/docs/Gui.Core._KeyboardNavigation.html) | Provides logical and directional navigation between focusable objects. |
| [Label](https://www.noesisengine.com/docs/Gui.Core._Label.html) | Represents the text label for a control. |
| [Line](https://www.noesisengine.com/docs/Gui.Core._Line.html) | Draws a line. |
| [LineBreak](https://www.noesisengine.com/docs/Gui.Core._LineBreak.html) | An inline flow content element that causes a line break to occur in flow content. |
| [LineGeometry](https://www.noesisengine.com/docs/Gui.Core._LineGeometry.html) | Represents the geometry of a line. |
| [LineSegment](https://www.noesisengine.com/docs/Gui.Core._LineSegment.html) | Creates a line between two points in a [PathFigure](https://www.noesisengine.com/docs/Gui.Core._PathFigure.html). |
| [LinearColorKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._LinearColorKeyFrame.html) | Animates from the *Color* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearDoubleKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._LinearDoubleKeyFrame.html) | Animates from the *Float* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearGradientBrush](https://www.noesisengine.com/docs/Gui.Core._LinearGradientBrush.html) | Paints an area with a linear gradient. A [LinearGradientBrush](https://www.noesisengine.com/docs/Gui.Core._LinearGradientBrush.html) paints an area with a linear gradient. A linear gradient defines a gradient along a line. The line's end points are defined by the *StartPoint* and *EndPoint* properties of the linear gradient. A [LinearGradientBrush](https://www.noesisengine.com/docs/Gui.Core._LinearGradientBrush.html) brush paints its *GradientStops* along this line. |
| [LinearInt16KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._LinearInt16KeyFrame.html) | Animates from the *Int16* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearInt32KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._LinearInt32KeyFrame.html) | Animates from the *Int32* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearInt64KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._LinearInt64KeyFrame.html) | Animates from the *Int64* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearPoint3DKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._LinearPoint3DKeyFrame.html) | Animates from the *Point3D* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearPointKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._LinearPointKeyFrame.html) | Animates from the *Point* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearRectKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._LinearRectKeyFrame.html) | Animates from the *Rect* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearSizeKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._LinearSizeKeyFrame.html) | Animates from the *Size* value of the previous key frame to its own *Value* using linear interpolation. |
| [LinearThicknessKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._LinearThicknessKeyFrame.html) | Animates from the *Thickness* value of the previous key frame to its own *Value* using linear interpolation. |
| [ListBox](https://www.noesisengine.com/docs/Gui.Core._ListBox.html) | Contains a list of selectable items. |
| [ListBoxItem](https://www.noesisengine.com/docs/Gui.Core._ListBoxItem.html) | Represents a selectable item in a [ListBox](https://www.noesisengine.com/docs/Gui.Core._ListBox.html). |
| [ListView](https://www.noesisengine.com/docs/Gui.Controls._ListView.html) | Represents a control that displays a list of data items. |
| [ListViewItem](https://www.noesisengine.com/docs/Gui.Controls._ListViewItem.html) | Represents an item in a [ListView](https://www.noesisengine.com/docs/Gui.Controls._ListView.html) control. |
| [LogicalTreeHelper](https://www.noesisengine.com/docs/Gui.Core._LogicalTreeHelper.html) | Contains static methods useful for performing common tasks with nodes in a logical tree. |
| [MarkupExtension](https://www.noesisengine.com/docs/Gui.Core._MarkupExtension.html) | Provides a base class for XAML markup extension implementations. |
| [MatrixAnimationBase](https://www.noesisengine.com/docs/Gui.Animation._MatrixAnimationBase.html) | Abstract class that, when implemented, animates a *Matrix* value. |
| [MatrixAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._MatrixAnimationUsingKeyFrames.html) | Animates the value of a *Matrix* property along a set of *KeyFrames*. |
| [MatrixKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._MatrixKeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [MatrixAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._MatrixAnimationUsingKeyFrames.html). |
| [MatrixKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._MatrixKeyFrameCollection.html) | Represents a collection of [MatrixKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._MatrixKeyFrame.html) objects. |
| [MatrixTransform](https://www.noesisengine.com/docs/Gui.Core._MatrixTransform.html) | Creates an arbitrary affine matrix transformation that is used to manipulate objects or coordinate systems in a 2D plane. |
| [MatrixTransform3D](https://www.noesisengine.com/docs/Gui.Core._MatrixTransform3D.html) | Applies a 3D transformation matrix to an object. |
| [Menu](https://www.noesisengine.com/docs/Gui.Core._Menu.html) | Represents a Windows menu control that enables you to hierarchically organize elements associated with commands and event handlers. |
| [MenuItem](https://www.noesisengine.com/docs/Gui.Core._MenuItem.html) | Represents a selectable item inside a [Menu](https://www.noesisengine.com/docs/Gui.Core._Menu.html) or [ContextMenu](https://www.noesisengine.com/docs/Gui.Core._ContextMenu.html). |
| [Mesh](https://www.noesisengine.com/docs/Gui.Core._Mesh.html) | Renders a mesh geometry defined by vertices and indexed triangles. |
| [MeshData](https://www.noesisengine.com/docs/Gui.Core._MeshData.html) | Represents a low-level geometric mesh composed of vertices and indexed triangles. |
| [Mouse](https://www.noesisengine.com/docs/Gui.Core._Mouse.html) | Represents the mouse device. |
| [MouseBinding](https://www.noesisengine.com/docs/Gui.Core._MouseBinding.html) | Binds a [MouseGesture](https://www.noesisengine.com/docs/Gui.Core._MouseGesture.html) to a Command. |
| [MouseGesture](https://www.noesisengine.com/docs/Gui.Core._MouseGesture.html) | Defines a mouse input gesture that can be used to invoke a command. |
| [MultiBinding](https://www.noesisengine.com/docs/Gui.Core._MultiBinding.html) | Describes a collection of [Binding](https://www.noesisengine.com/docs/Gui.Core._Binding.html) objects attached to a single binding target property. |
| [MultiBindingExpression](https://www.noesisengine.com/docs/Gui.Core._MultiBindingExpression.html) | Contains instance information about a single instance of a [MultiBinding](https://www.noesisengine.com/docs/Gui.Core._MultiBinding.html). |
| [MultiDataTrigger](https://www.noesisengine.com/docs/Gui.Core._MultiDataTrigger.html) | Represents a trigger that applies property values or performs actions when the bound data meets a set of conditions. |
| [MultiTrigger](https://www.noesisengine.com/docs/Gui.Core._MultiTrigger.html) | Represents a trigger that applies property values or performs actions when a set of conditions are satisfied. |
| [NameScope](https://www.noesisengine.com/docs/Gui.Core._NameScope.html) | Store relationships between the XAML defined names of objects and their instances. |
| [NullExtension](https://www.noesisengine.com/docs/Gui.Core._NullExtension.html) | Implements a XAML markup extension in order to return a null object. |
| [ObjectAnimationBase](https://www.noesisengine.com/docs/Gui.Animation._ObjectAnimationBase.html) | Abstract class that, when implemented, animates a *Object* value. |
| [ObjectAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._ObjectAnimationUsingKeyFrames.html) | Animates the value of a *BaseComponent* property along a set of *KeyFrames*. |
| [ObjectKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._ObjectKeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [ObjectAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._ObjectAnimationUsingKeyFrames.html). |
| [ObjectKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._ObjectKeyFrameCollection.html) | Represents a collection of [ObjectKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._ObjectKeyFrame.html) objects. |
| [ObservableCollection](https://www.noesisengine.com/docs/Gui.Core._ObservableCollection.html) | Represents a dynamic data collection that provides notifications when items get added or removed. |
| [Page](https://www.noesisengine.com/docs/Gui.Core._Page.html) | Encapsulates a page of content. |
| [Panel](https://www.noesisengine.com/docs/Gui.Core._Panel.html) | Provides a base class for all [Panel](https://www.noesisengine.com/docs/Gui.Core._Panel.html) elements. Use [Panel](https://www.noesisengine.com/docs/Gui.Core._Panel.html) elements to position and arrange child objects. |
| [ParallelTimeline](https://www.noesisengine.com/docs/Gui.Animation._ParallelTimeline.html) | Defines a segment of time that may contain child [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html) objects. |
| [PasswordBox](https://www.noesisengine.com/docs/Gui.Core._PasswordBox.html) | Represents a control designed for entering and handling passwords. |
| [Path](https://www.noesisengine.com/docs/Gui.Core._Path.html) | Draws a series of connected lines and curves. |
| [PathFigure](https://www.noesisengine.com/docs/Gui.Core._PathFigure.html) | Represents a subsection of a geometry, a single connected series of two-dimensional segments. |
| [PathGeometry](https://www.noesisengine.com/docs/Gui.Core._PathGeometry.html) | Represents a complex shape that may be composed of arcs, curves, ellipses, lines and rectangles. |
| [PathSegment](https://www.noesisengine.com/docs/Gui.Core._PathSegment.html) | Represents a complex shape that may be composed of arcs, curves, ellipses, lines and rectangles. |
| [PauseStoryboard](https://www.noesisengine.com/docs/Gui.Animation._PauseStoryboard.html) | A trigger action that pauses a [Storyboard](https://www.noesisengine.com/docs/Gui.Animation._Storyboard.html). |
| [Pen](https://www.noesisengine.com/docs/Gui.Core._Pen.html) | Describes how a shape is outlined. |
| [Point3DAnimation](https://www.noesisengine.com/docs/Gui.Animation._Point3DAnimation.html) | Animates the value of a *Point3D* property between two target values using linear interpolation over a specified *Duration*. |
| [Point3DAnimationBase](https://www.noesisengine.com/docs/Gui.Animation._Point3DAnimationBase.html) | Abstract class that, when implemented, animates a *Point3D* value. |
| [Point3DAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Point3DAnimationUsingKeyFrames.html) | Animates the value of a *Point3D* property along a set of *KeyFrames*. |
| [Point3DKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._Point3DKeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [Point3DAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._Point3DAnimationUsingKeyFrames.html). |
| [Point3DKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._Point3DKeyFrameCollection.html) | Represents a collection of [Point3DKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._Point3DKeyFrame.html) objects. |
| [PointAnimation](https://www.noesisengine.com/docs/Gui.Animation._PointAnimation.html) | Animates the value of a *Point* property between two target values using linear interpolation over a specified *Duration*. |
| [PointAnimationBase](https://www.noesisengine.com/docs/Gui.Animation._PointAnimationBase.html) | Abstract class that, when implemented, animates a *Point* value. |
| [PointAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._PointAnimationUsingKeyFrames.html) | Animates the value of a *Point* property along a set of *KeyFrames*. |
| [PointKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._PointKeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [PointAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._PointAnimationUsingKeyFrames.html). |
| [PointKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._PointKeyFrameCollection.html) | Represents a collection of [PointKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._PointKeyFrame.html) objects. |
| [PolyBezierSegment](https://www.noesisengine.com/docs/Gui.Core._PolyBezierSegment.html) | Represents one or more cubic Bezier curves. |
| [PolyLineSegment](https://www.noesisengine.com/docs/Gui.Core._PolyLineSegment.html) | Represents a set of line segments defined by a PointCollection with each Point specifying the end point of a line segment. |
| [PolyQuadraticBezierSegment](https://www.noesisengine.com/docs/Gui.Core._PolyQuadraticBezierSegment.html) | Represents one or more quadratic Bezier curves. |
| [Popup](https://www.noesisengine.com/docs/Gui.Core._Popup.html) | Represents a pop-up window that has content. |
| [PowerEase](https://www.noesisengine.com/docs/Gui.Animation._PowerEase.html) | Represents an easing function that creates an animation that accelerates and/or decelerates using the formula f(t) = t<sup>p</sup> where p is equal to the *Power* property. |
| [ProgressBar](https://www.noesisengine.com/docs/Gui.Core._ProgressBar.html) | Indicates the progress of an operation. |
| [PropertyMetadata](https://www.noesisengine.com/docs/Gui.DependencySystem._PropertyMetadata.html) | Defines certain behavior aspects of a dependency property as it is applied to a specific type, including conditions it was registered with. |
| [PropertyPath](https://www.noesisengine.com/docs/Gui.Core._PropertyPath.html) | Implements a data structure for describing a property as a path below another property, or below an owning type. Property paths are used in data binding to objects, and in storyboards and timelines for animations. |
| [QuadraticBezierSegment](https://www.noesisengine.com/docs/Gui.Core._QuadraticBezierSegment.html) | Represents a quadratic Bezier curve drawn between two points. |
| [QuadraticEase](https://www.noesisengine.com/docs/Gui.Animation._QuadraticEase.html) | Represents an easing function that creates an animation that accelerates and/or decelerates using the formula f(t) = t<sup>2</sup>. |
| [QuarticEase](https://www.noesisengine.com/docs/Gui.Animation._QuarticEase.html) | Represents an easing function that creates an animation that accelerates and/or decelerates using the formula f(t) = t<sup>4</sup>. |
| [QuinticEase](https://www.noesisengine.com/docs/Gui.Animation._QuinticEase.html) | Represents an easing function that creates an animation that accelerates and/or decelerates using the formula f(t) = t<sup>5</sup>. |
| [RadialGradientBrush](https://www.noesisengine.com/docs/Gui.Core._RadialGradientBrush.html) | Paints an area with a radial gradient. |
| [RadioButton](https://www.noesisengine.com/docs/Gui.Core._RadioButton.html) | Represents a button that can be selected, but not cleared, by a user. |
| [RangeBase](https://www.noesisengine.com/docs/Gui.Core._RangeBase.html) | Represents an element that has a value within a specific range. |
| [RectAnimation](https://www.noesisengine.com/docs/Gui.Animation._RectAnimation.html) | Animates the value of a *Rect* property between two target values using linear interpolation over a specified *Duration*. |
| [RectAnimationBase](https://www.noesisengine.com/docs/Gui.Animation._RectAnimationBase.html) | Abstract class that, when implemented, animates a *Rect* value. |
| [RectAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._RectAnimationUsingKeyFrames.html) | Animates the value of a *Rect* property along a set of *KeyFrames*. |
| [RectKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._RectKeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [RectAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._RectAnimationUsingKeyFrames.html). |
| [RectKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._RectKeyFrameCollection.html) | Represents a collection of [RectKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._RectKeyFrame.html) objects. |
| [Rectangle](https://www.noesisengine.com/docs/Gui.Core._Rectangle.html) | Draws a rectangle. |
| [RectangleGeometry](https://www.noesisengine.com/docs/Gui.Core._RectangleGeometry.html) | Describes a two-dimensional rectangle geometry. |
| [RelativeSource](https://www.noesisengine.com/docs/Gui.Core._RelativeSource.html) | Implements a markup extension that describes the location of the binding source relative to the position of the binding target. |
| [RenderOptions](https://www.noesisengine.com/docs/Gui.Core._RenderOptions.html) | Provides options for controlling the rendering behavior of objects. |
| [RepeatBehavior](https://www.noesisengine.com/docs/Gui.Animation._RepeatBehavior.html) | Describes how a [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html) repeats its simple duration. Examples: |
| [RepeatButton](https://www.noesisengine.com/docs/Gui.Core._RepeatButton.html) | Represents a control that raises its *Click* event repeatedly from the time it is pressed until it is released. |
| [ResourceDictionary](https://www.noesisengine.com/docs/Gui.Core._ResourceDictionary.html) | Provides a hash table implementation that contains resources used by the UI. |
| [ResumeStoryboard](https://www.noesisengine.com/docs/Gui.Animation._ResumeStoryboard.html) | A trigger action that resumes a paused [Storyboard](https://www.noesisengine.com/docs/Gui.Animation._Storyboard.html). |
| [RotateTransform](https://www.noesisengine.com/docs/Gui.Core._RotateTransform.html) | Rotates an object clockwise about a specified point in 2D coordinate system. |
| [RoutedCommand](https://www.noesisengine.com/docs/Gui.Core._RoutedCommand.html) | A command that is routed through the element tree. |
| [RoutedEvent](https://www.noesisengine.com/docs/Gui.Core._RoutedEvent.html) | An event instance that propagates through a tree of related elements. There are three types of routing: bubbling, tunneling and direct. With bubbling, the event instance moves from the source of the event up to the top of the tree. With tunneling, the event instance starts at the top of the tree and moves down to the source of the event. With direct routing, the event instance behaves like a standard event. |
| [RoutedUICommand](https://www.noesisengine.com/docs/Gui.Core._RoutedUICommand.html) | A command that is routed through the element tree and contains a text property. |
| [RowDefinition](https://www.noesisengine.com/docs/Gui.Core._RowDefinition.html) | Defines row-specific properties that apply to [Grid](https://www.noesisengine.com/docs/Gui.Core._Grid.html) elements. |
| [Run](https://www.noesisengine.com/docs/Gui.Core._Run.html) | An inline-level flow content element intended to contain a run of formatted or unformatted text. |
| [ScaleTransform](https://www.noesisengine.com/docs/Gui.Core._ScaleTransform.html) | Scales an object in the 2D coordinate system. |
| [ScrollBar](https://www.noesisengine.com/docs/Gui.Core._ScrollBar.html) | Represents a control that provides a scroll bar that has a sliding [Thumb](https://www.noesisengine.com/docs/Gui.Core._Thumb.html) whose position corresponds to a value. |
| [ScrollContentPresenter](https://www.noesisengine.com/docs/Gui.Core._ScrollContentPresenter.html) | Displays the content of a [ScrollViewer](https://www.noesisengine.com/docs/Gui.Core._ScrollViewer.html) control. |
| [ScrollViewer](https://www.noesisengine.com/docs/Gui.Core._ScrollViewer.html) | Represents a scrollable area that can contain other visible elements. |
| [Selector](https://www.noesisengine.com/docs/Gui.Core._Selector.html) | Represents a control that allows a user to select items from among its child elements. |
| [Separator](https://www.noesisengine.com/docs/Gui.Core._Separator.html) | [Control](https://www.noesisengine.com/docs/Gui.Core._Control.html) that is used to separate items in items controls. |
| [Setter](https://www.noesisengine.com/docs/Gui.Core._Setter.html) | Represents a setter that applies a property value. |
| [ShaderEffect](https://www.noesisengine.com/docs/Gui.Core._ShaderEffect.html) | Provides a custom bitmap effect by using a pixel shader. |
| [Shape](https://www.noesisengine.com/docs/Gui.Core._Shape.html) | Provides a base class for shape elements. |
| [SineEase](https://www.noesisengine.com/docs/Gui.Animation._SineEase.html) | Represents an easing function that creates an animation that accelerates and/or decelerates using a sine formula |
| [SizeAnimation](https://www.noesisengine.com/docs/Gui.Animation._SizeAnimation.html) | Animates the value of a *Size* property between two target values using linear interpolation over a specified *Duration*. |
| [SizeAnimationBase](https://www.noesisengine.com/docs/Gui.Animation._SizeAnimationBase.html) | Abstract class that, when implemented, animates a *Size* value. |
| [SizeAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._SizeAnimationUsingKeyFrames.html) | Animates the value of a *Size* property along a set of *KeyFrames*. |
| [SizeKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SizeKeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [SizeAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._SizeAnimationUsingKeyFrames.html). |
| [SizeKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._SizeKeyFrameCollection.html) | Represents a collection of [SizeKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SizeKeyFrame.html) objects. |
| [SkewTransform](https://www.noesisengine.com/docs/Gui.Core._SkewTransform.html) | Represents a 2D skew. It is useful for creating the illusion of 3-dimensional depth in a 2D object. |
| [Slider](https://www.noesisengine.com/docs/Gui.Core._Slider.html) | Represents a control that lets the user select from a range of values by moving a [Thumb](https://www.noesisengine.com/docs/Gui.Core._Thumb.html) control along a [Track](https://www.noesisengine.com/docs/Gui.Core._Track.html). |
| [SolidColorBrush](https://www.noesisengine.com/docs/Gui.Core._SolidColorBrush.html) | Paints an area with a solid color. |
| [Span](https://www.noesisengine.com/docs/Gui.Core._Span.html) | Groups other [Inline](https://www.noesisengine.com/docs/Gui.Core._Inline.html) content elements. |
| [SplineColorKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SplineColorKeyFrame.html) | Animates from the *Color* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineDoubleKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SplineDoubleKeyFrame.html) | Animates from the *Float* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineInt16KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SplineInt16KeyFrame.html) | Animates from the *Int16* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineInt32KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SplineInt32KeyFrame.html) | Animates from the *Int32* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineInt64KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SplineInt64KeyFrame.html) | Animates from the *Int64* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplinePoint3DKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SplinePoint3DKeyFrame.html) | Animates from the *Point3D* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplinePointKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SplinePointKeyFrame.html) | Animates from the *Point* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineRectKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SplineRectKeyFrame.html) | Animates from the *Rect* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineSizeKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SplineSizeKeyFrame.html) | Animates from the *Size* value of the previous key frame to its own *Value* using splined interpolation. |
| [SplineThicknessKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._SplineThicknessKeyFrame.html) | Animates from the *Thickness* value of the previous key frame to its own *Value* using splined interpolation. |
| [StackPanel](https://www.noesisengine.com/docs/Gui.Core._StackPanel.html) | Arranges child elements into a single horizontal or vertical line. |
| [StaticExtension](https://www.noesisengine.com/docs/Gui.Core._StaticExtension.html) | Implements a markup extension that returns static field and property references. |
| [StaticResourceExtension](https://www.noesisengine.com/docs/Gui.Core._StaticResourceExtension.html) | Implements a markup extension that supports static resource references made from XAML. |
| [StatusBar](https://www.noesisengine.com/docs/Gui.Core._StatusBar.html) | Represents a control that displays items and information in a horizontal bar (typically at the bottom) in an application window. |
| [StatusBarItem](https://www.noesisengine.com/docs/Gui.Core._StatusBarItem.html) | Represents an item of a [StatusBar](https://www.noesisengine.com/docs/Gui.Core._StatusBar.html) control. |
| [StopStoryboard](https://www.noesisengine.com/docs/Gui.Animation._StopStoryboard.html) | A trigger action that stops a [Storyboard](https://www.noesisengine.com/docs/Gui.Animation._Storyboard.html). |
| [Storyboard](https://www.noesisengine.com/docs/Gui.Animation._Storyboard.html) | A container timeline that provides object and property targeting information for its child animations. |
| [StreamGeometry](https://www.noesisengine.com/docs/Gui.Core._StreamGeometry.html) | Defines a geometric shape, described using a [StreamGeometryContext](https://www.noesisengine.com/docs/Gui.Core._StreamGeometryContext.html) or a SVG command string as described in the [W3C](http://www.w3.org/TR/SVG11/paths.html) specs. |
| [StreamGeometryContext](https://www.noesisengine.com/docs/Gui.Core._StreamGeometryContext.html) | Describes a geometry using drawing commands. This class is used with the [StreamGeometry](https://www.noesisengine.com/docs/Gui.Core._StreamGeometry.html) class to create a lightweight geometry that does not support data binding, animation, or modification. |
| [StringAnimationBase](https://www.noesisengine.com/docs/Gui.Animation._StringAnimationBase.html) | Abstract class that, when implemented, animates a *String* value. |
| [StringAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._StringAnimationUsingKeyFrames.html) | Animates the value of a *String* property along a set of *KeyFrames*. |
| [StringKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._StringKeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [StringAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._StringAnimationUsingKeyFrames.html). |
| [StringKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._StringKeyFrameCollection.html) | Represents a collection of [StringKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._StringKeyFrame.html) objects. |
| [Style](https://www.noesisengine.com/docs/Gui.Core._Style.html) | Enables the sharing of properties, resources, and event handlers between instances of a type. |
| [TabControl](https://www.noesisengine.com/docs/Gui.Core._TabControl.html) | Represents a control that contains multiple items that share the same space on the screen. |
| [TabItem](https://www.noesisengine.com/docs/Gui.Core._TabItem.html) | Represents a selectable item inside a [TabControl](https://www.noesisengine.com/docs/Gui.Core._TabControl.html). |
| [TabPanel](https://www.noesisengine.com/docs/Gui.Core._TabPanel.html) | Handles the layout of the [TabItem](https://www.noesisengine.com/docs/Gui.Core._TabItem.html) objects on a [TabControl](https://www.noesisengine.com/docs/Gui.Core._TabControl.html). |
| [TemplateBindingExpression](https://www.noesisengine.com/docs/Gui.Core._TemplateBindingExpression.html) | Describes a run-time instance of a [TemplateBindingExtension](https://www.noesisengine.com/docs/Gui.Core._TemplateBindingExtension.html). |
| [TemplateBindingExtension](https://www.noesisengine.com/docs/Gui.Core._TemplateBindingExtension.html) | Implements a markup extension that supports the binding between the value of a property in a template and the value of some other exposed property on the templated control. |
| [TextBlock](https://www.noesisengine.com/docs/Gui.Core._TextBlock.html) | Provides a lightweight control for displaying small amounts of text content. |
| [TextBox](https://www.noesisengine.com/docs/Gui.Core._TextBox.html) | Represents a control that can be used to display or edit unformatted text. |
| [TextElement](https://www.noesisengine.com/docs/Gui.Core._TextElement.html) | Defines text attached properties. |
| [Texture](https://www.noesisengine.com/docs/Render.RenderDevice._Texture.html) | Base class for 2D textures |
| [TextureSource](https://www.noesisengine.com/docs/Gui.Core._TextureSource.html) | Defines a [BitmapSource](https://www.noesisengine.com/docs/Gui.Core._BitmapSource.html) constructed from a [Texture](https://www.noesisengine.com/docs/Render.RenderDevice._Texture.html). |
| [ThicknessAnimation](https://www.noesisengine.com/docs/Gui.Animation._ThicknessAnimation.html) | Animates the value of a *Thickness* property between two target values using linear interpolationover a specified *Duration*. |
| [ThicknessAnimationBase](https://www.noesisengine.com/docs/Gui.Animation._ThicknessAnimationBase.html) | Abstract class that, when implemented, animates a *Thickness* value. |
| [ThicknessAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._ThicknessAnimationUsingKeyFrames.html) | Animates the value of a *Thickness* property along a set of *KeyFrames*. |
| [ThicknessKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._ThicknessKeyFrame.html) | Defines an animation segment with its own target value and interpolation method for a [BooleanAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._BooleanAnimationUsingKeyFrames.html). |
| [ThicknessKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._ThicknessKeyFrameCollection.html) | Represents a collection of [ThicknessKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._ThicknessKeyFrame.html) objects. |
| [Thumb](https://www.noesisengine.com/docs/Gui.Core._Thumb.html) | Represents a control that can be dragged by the user. |
| [TickBar](https://www.noesisengine.com/docs/Gui.Core._TickBar.html) | Represents a control that draws a set of tick marks for a [Slider](https://www.noesisengine.com/docs/Gui.Core._Slider.html) control. |
| [TileBrush](https://www.noesisengine.com/docs/Gui.Core._TileBrush.html) | Describes a way to paint a region by using one or more tiles. |
| [TimeSpan](https://www.noesisengine.com/docs/Gui.Animation._TimeSpan.html) | Represents a time interval. |
| [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html) | Defines a segment of time. |
| [TimelineGroup](https://www.noesisengine.com/docs/Gui.Animation._TimelineGroup.html) | Abstract class that, when implemented represents a [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html) that may contain a collection of child [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html) objects. |
| [ToggleButton](https://www.noesisengine.com/docs/Gui.Core._ToggleButton.html) | Base class for button controls that can switch states. |
| [ToolBar](https://www.noesisengine.com/docs/Gui.Core._ToolBar.html) | Provides a container for a group of commands or controls. |
| [ToolBarOverflowPanel](https://www.noesisengine.com/docs/Gui.Core._ToolBarOverflowPanel.html) | Used to arrange overflow [ToolBar](https://www.noesisengine.com/docs/Gui.Core._ToolBar.html) items. |
| [ToolBarPanel](https://www.noesisengine.com/docs/Gui.Core._ToolBarPanel.html) | Arranges [ToolBar](https://www.noesisengine.com/docs/Gui.Core._ToolBar.html) items inside a [ToolBar](https://www.noesisengine.com/docs/Gui.Core._ToolBar.html). |
| [ToolBarTray](https://www.noesisengine.com/docs/Gui.Core._ToolBarTray.html) | Represents the container that handles the layout of a [ToolBar](https://www.noesisengine.com/docs/Gui.Core._ToolBar.html). |
| [ToolTip](https://www.noesisengine.com/docs/Gui.Core._ToolTip.html) | Represents a control that creates a pop-up window that displays information for an element in the interface. |
| [ToolTipService](https://www.noesisengine.com/docs/Gui.Core._ToolTipService.html) | Represents a service that provides properties and events to control the display and behavior of tooltips. |
| [Track](https://www.noesisengine.com/docs/Gui.Core._Track.html) | Represents a control primitive that handles the positioning and sizing of a [Thumb](https://www.noesisengine.com/docs/Gui.Core._Thumb.html) control and two [RepeatButton](https://www.noesisengine.com/docs/Gui.Core._RepeatButton.html) controls that are used to set a Value. |
| [Transform](https://www.noesisengine.com/docs/Gui.Core._Transform.html) | Defines functionality that enables transformations in a 2D plane. |
| [Transform3D](https://www.noesisengine.com/docs/Gui.Core._Transform3D.html) | Provides a base class for all three-dimensional transformations, including translation, rotation, and scale transformations. |
| [TransformGroup](https://www.noesisengine.com/docs/Gui.Core._TransformGroup.html) | Represents a composite [Transform](https://www.noesisengine.com/docs/Gui.Core._Transform.html) composed of other [Transform](https://www.noesisengine.com/docs/Gui.Core._Transform.html) objects. |
| [TranslateTransform](https://www.noesisengine.com/docs/Gui.Core._TranslateTransform.html) | Translates an object in the 2D coordinate system. |
| [TreeView](https://www.noesisengine.com/docs/Gui.Core._TreeView.html) | Represents a control that displays hierarchical data in a tree structure that has items that can expand and collapse. |
| [TreeViewItem](https://www.noesisengine.com/docs/Gui.Core._TreeViewItem.html) | Implements a selectable item in a [TreeView](https://www.noesisengine.com/docs/Gui.Core._TreeView.html) control. |
| [Trigger](https://www.noesisengine.com/docs/Gui.Core._Trigger.html) | Represents a trigger that applies property values or performs actions conditionally. |
| [TriggerAction](https://www.noesisengine.com/docs/Gui.Core._TriggerAction.html) | Describes an action to perform for a trigger. |
| [TypeExtension](https://www.noesisengine.com/docs/Gui.Core._TypeExtension.html) | Implements a markup extension that returns a *Type* based on a string input. |
| [Typography](https://www.noesisengine.com/docs/Gui.Core._Typography.html) | Provides access to a rich set of OpenType typography properties. |
| [UIElement](https://www.noesisengine.com/docs/Gui.Core._UIElement.html) | Provides rendering support, which includes hit testing, coordinate transformation, and bounding box calculations. |
| [UIElementCollection](https://www.noesisengine.com/docs/Gui.Core._UIElementCollection.html) | Represents an ordered collection of [UIElement](https://www.noesisengine.com/docs/Gui.Core._UIElement.html) child elements. |
| [UIPropertyMetadata](https://www.noesisengine.com/docs/Gui.Core._UIPropertyMetadata.html) | Provides property metadata for non-framework properties that do have rendering/user interface impact at the core level. |
| [Underline](https://www.noesisengine.com/docs/Gui.Core._Underline.html) | An inline-level flow content element which causes content to render with an underlined text decoration. |
| [UniformGrid](https://www.noesisengine.com/docs/Gui.Core._UniformGrid.html) | Provides a way to arrange content in a grid where all the cells in the grid have the same size. |
| [Uri](https://www.noesisengine.com/docs/Gui.Providers._Uri.html) | Provides a representation of a uniform resource identifier and easy access to parts of the URI. |
| [UserControl](https://www.noesisengine.com/docs/Gui.Core._UserControl.html) | Provides a simple way to create a composition of controls. |
| [ValueTargetProvider](https://www.noesisengine.com/docs/Gui.Core._ValueTargetProvider.html) | Provides useful information during [MarkupExtension](https://www.noesisengine.com/docs/Gui.Core._MarkupExtension.html) *ProvideValue* calls. |
| [Viewbox](https://www.noesisengine.com/docs/Gui.Core._Viewbox.html) | Defines a content decorator that can stretch and scale a single child to fill the available space. |
| [VirtualizationCacheLength](https://www.noesisengine.com/docs/Gui.Core._VirtualizationCacheLength.html) | Represents the measurements for the *VirtualizingPanel.CacheLength* attached property. |
| [VirtualizingPanel](https://www.noesisengine.com/docs/Gui.Core._VirtualizingPanel.html) | Base class that provides access to information that is useful for implementing virtualization. |
| [VirtualizingStackPanel](https://www.noesisengine.com/docs/Gui.Core._VirtualizingStackPanel.html) | Arranges and virtualizes content on a single line that is oriented either horizontally or vertically. |
| [VirtualizingWrapPanel](https://www.noesisengine.com/docs/Gui.Core._VirtualizingWrapPanel.html) | A high-performance [WrapPanel](https://www.noesisengine.com/docs/Gui.Core._WrapPanel.html) that supports UI virtualization, designed for use in both horizontal and vertical layouts. |
| [Visual](https://www.noesisengine.com/docs/Gui.Core._Visual.html) | Provides rendering support, which includes hit testing, coordinate transformation, and bounding box calculations. |
| [VisualBrush](https://www.noesisengine.com/docs/Gui.Core._VisualBrush.html) | Paints an area with a [Visual](https://www.noesisengine.com/docs/Gui.Core._Visual.html). |
| [VisualCollection](https://www.noesisengine.com/docs/Gui.Core._VisualCollection.html) | Represents an ordered collection of [Visual](https://www.noesisengine.com/docs/Gui.Core._Visual.html) objects. |
| [VisualState](https://www.noesisengine.com/docs/Gui.Animation._VisualState.html) | Represents the visual appearance of the control when it is in a specific state. |
| [VisualStateGroup](https://www.noesisengine.com/docs/Gui.Animation._VisualStateGroup.html) | Contains mutually exclusive [VisualState](https://www.noesisengine.com/docs/Gui.Animation._VisualState.html) objects and [VisualTransition](https://www.noesisengine.com/docs/Gui.Animation._VisualTransition.html) objects that are used to go from one state to another. |
| [VisualStateManager](https://www.noesisengine.com/docs/Gui.Animation._VisualStateManager.html) | Manages states and the logic for transitioning between states for controls. |
| [VisualTransition](https://www.noesisengine.com/docs/Gui.Animation._VisualTransition.html) | Represents the visual behavior that occurs when the control transitions from one state to another. |
| [VisualTreeHelper](https://www.noesisengine.com/docs/Gui.Core._VisualTreeHelper.html) | Provides utility methods that perform common tasks involving nodes in a visual tree. |
| [WrapPanel](https://www.noesisengine.com/docs/Gui.Core._WrapPanel.html) | Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box. |

## NoesisApp Namespace

| Class | Description |
|-------|-------------|
| [Application](https://www.noesisengine.com/docs/App.ApplicationLauncher._Application.html) | Encapsulates a NoesisGUI application. |
| [AttachableCollection](https://www.noesisengine.com/docs/App.Interactivity._AttachableCollection.html) | Represents a collection of IAttachedObject with a shared *AssociatedObject* and provides change notifications to its contents when that *AssociatedObject* changes. |
| [AttachableObject](https://www.noesisengine.com/docs/App.Interactivity._AttachableObject.html) | Represents the base class for specifying attachable objects. |
| [BackgroundEffectBehavior](https://www.noesisengine.com/docs/App.Interactivity._BackgroundEffectBehavior.html) | Applies an effect to the contents beneath the associated object. |
| [Behavior](https://www.noesisengine.com/docs/App.Interactivity._Behavior.html) | Represents the base class for specifying *Behaviors* for a [DependencyObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html). |
| [BehaviorCollection](https://www.noesisengine.com/docs/App.Interactivity._BehaviorCollection.html) | Represents a collection of behaviors with a shared *AssociatedObject* and provides change notifications to its contents when that *AssociatedObject* changes. |
| [BehaviorT](https://www.noesisengine.com/docs/App.Interactivity._BehaviorT.html) | Templatized base class for *Behaviors*. |
| [BoxShadow](https://www.noesisengine.com/docs/App.Shaders._BoxShadow.html) | A box for rendering blurred rounded rectangles. |
| [ChangePropertyAction](https://www.noesisengine.com/docs/App.Interactivity._ChangePropertyAction.html) | An action that will change a property to a specified value when invoked. |
| [CollectionFilterBehavior](https://www.noesisengine.com/docs/App.Interactivity._CollectionFilterBehavior.html) | A behavior that filters a collection depending on the supplied Predicate object. |
| [CollectionSortBehavior](https://www.noesisengine.com/docs/App.Interactivity._CollectionSortBehavior.html) | A behavior that sorts a collection depending on the supplied Comparer object. |
| [ComparisonCondition](https://www.noesisengine.com/docs/App.Interactivity._ComparisonCondition.html) | Represents one ternary condition: *left operand*, *operator*, *right operand*. Used as condition in the list of conditions on a [ConditionalExpression](https://www.noesisengine.com/docs/App.Interactivity._ConditionalExpression.html). |
| [ConditionBehavior](https://www.noesisengine.com/docs/App.Interactivity._ConditionBehavior.html) | A behavior that attaches to a trigger and controls the conditions to fire the actions. |
| [ConditionalExpression](https://www.noesisengine.com/docs/App.Interactivity._ConditionalExpression.html) | Represents a conditional expression that is set on a *ConditionBehavior.Condition* property. Contains a list of conditions that gets evaluated in order. |
| [ConicGradientBrush](https://www.noesisengine.com/docs/App.Shaders._ConicGradientBrush.html) | Creates an pattern consisting of a gradient with color transitions rotated around a center point |
| [ControlStoryboardAction](https://www.noesisengine.com/docs/App.Interactivity._ControlStoryboardAction.html) | An action that will change the state of a targeted storyboard when invoked. |
| [CrossFadeBrush](https://www.noesisengine.com/docs/App.Shaders._CrossFadeBrush.html) | Interpolates between two images. |
| [DataEventTrigger](https://www.noesisengine.com/docs/App.Interactivity._DataEventTrigger.html) | Represents a trigger which fires when an event is raised on an object. Can be used to trigger from events on the data context, as opposed to a standard [EventTrigger](https://www.noesisengine.com/docs/App.Interactivity._EventTrigger.html) which uses routed events on a [FrameworkElement](https://www.noesisengine.com/docs/Gui.Core._FrameworkElement.html). |
| [DataTrigger](https://www.noesisengine.com/docs/App.Interactivity._DataTrigger.html) | Represents a trigger that performs actions when the bound data meets a specified condition. |
| [DirectionalBlurEffect](https://www.noesisengine.com/docs/App.Shaders._DirectionalBlurEffect.html) | Blurs an object along a specific angle, to create a blurred streaking effect. |
| [EventTrigger](https://www.noesisengine.com/docs/App.Interactivity._EventTrigger.html) | A trigger that listens for a specified event on its source and fires when that event is raised. |
| [EventTriggerBase](https://www.noesisengine.com/docs/App.Interactivity._EventTriggerBase.html) | Represents a trigger that can listen to an object other than its AssociatedObject. |
| [EventTriggerBaseT](https://www.noesisengine.com/docs/App.Interactivity._EventTriggerBaseT.html) | Templatized base class for EventTriggers. |
| [FilterPredicate](https://www.noesisengine.com/docs/App.Interactivity._FilterPredicate.html) | Base class for Filter predicate object used by [CollectionFilterBehavior](https://www.noesisengine.com/docs/App.Interactivity._CollectionFilterBehavior.html). |
| [GamepadTrigger](https://www.noesisengine.com/docs/App.Interactivity._GamepadTrigger.html) | A [Trigger](https://www.noesisengine.com/docs/Gui.Core._Trigger.html) that is triggered by a specified gamepad button. |
| [GoToStateAction](https://www.noesisengine.com/docs/App.Interactivity._GoToStateAction.html) | An action that will transition a [FrameworkElement](https://www.noesisengine.com/docs/Gui.Core._FrameworkElement.html) to a specified [VisualState](https://www.noesisengine.com/docs/Gui.Animation._VisualState.html) when invoked. |
| [Interaction](https://www.noesisengine.com/docs/App.Interactivity._Interaction.html) | Manages a collection of behaviors and triggers that expand the object functionality from XAML. |
| [InvokeCommandAction](https://www.noesisengine.com/docs/App.Interactivity._InvokeCommandAction.html) | Executes the specified *ICommand* when invoked. |
| [KeyTrigger](https://www.noesisengine.com/docs/App.Interactivity._KeyTrigger.html) | A [Trigger](https://www.noesisengine.com/docs/Gui.Core._Trigger.html) that is triggered by a keyboard event. If *Key* and *Modifiers* are detected, it fires. |
| [LaunchUriOrFileAction](https://www.noesisengine.com/docs/App.Interactivity._LaunchUriOrFileAction.html) | An action that will launch a process to open a file or uri. |
| [LineDecorationBehavior](https://www.noesisengine.com/docs/App.Interactivity._LineDecorationBehavior.html) | Renders a line decoration on the associated [TextBlock](https://www.noesisengine.com/docs/Gui.Core._TextBlock.html). |
| [LoadContentAction](https://www.noesisengine.com/docs/App.Interactivity._LoadContentAction.html) | An action that will set the Content of the target [ContentControl](https://www.noesisengine.com/docs/Gui.Core._ContentControl.html) by loading a xaml. |
| [LocExtension](https://www.noesisengine.com/docs/App.ApplicationLauncher._LocExtension.html) | Implements a markup extension that supports references to a localization [ResourceDictionary](https://www.noesisengine.com/docs/Gui.Core._ResourceDictionary.html). |
| [MediaElement](https://www.noesisengine.com/docs/App.MediaElement._MediaElement.html) | Represents a control that contains audio and/or video. |
| [MediaPlayer](https://www.noesisengine.com/docs/App.MediaElement._MediaPlayer.html) | Abstract class for the implementation of audio/video in a [MediaElement](https://www.noesisengine.com/docs/App.MediaElement._MediaElement.html). |
| [MessageBox](https://www.noesisengine.com/docs/App.ApplicationLauncher._MessageBox.html) | Displays a message box by calling the static *Show* method. The callback gets called when the dialog is closed indicating which button was pressed as result. |
| [MonochromeBrush](https://www.noesisengine.com/docs/App.Shaders._MonochromeBrush.html) | [BrushShader](https://www.noesisengine.com/docs/Gui.Core._BrushShader.html) that turns an image into a monochrome color |
| [MouseDragElementBehavior](https://www.noesisengine.com/docs/App.Interactivity._MouseDragElementBehavior.html) | Moves the attached element in response to mouse drag gestures on the element. |
| [MoveFocusAction](https://www.noesisengine.com/docs/App.Interactivity._MoveFocusAction.html) | An action that will try move focus in the specified direction. |
| [PauseMediaAction](https://www.noesisengine.com/docs/App.Interactivity._PauseMediaAction.html) | Pauses a media element. |
| [PinchEffect](https://www.noesisengine.com/docs/App.Shaders._PinchEffect.html) | [Effect](https://www.noesisengine.com/docs/Gui.Core._Effect.html) to warp or pinch a specific area in a visual. |
| [PixelateEffect](https://www.noesisengine.com/docs/App.Shaders._PixelateEffect.html) | [ShaderEffect](https://www.noesisengine.com/docs/Gui.Core._ShaderEffect.html) that pixelates a visual. |
| [PlasmaBrush](https://www.noesisengine.com/docs/App.Shaders._PlasmaBrush.html) | [BrushShader](https://www.noesisengine.com/docs/Gui.Core._BrushShader.html) for old school plasma effect. |
| [PlayMediaAction](https://www.noesisengine.com/docs/App.Interactivity._PlayMediaAction.html) | Plays a media element. |
| [PlaySoundAction](https://www.noesisengine.com/docs/App.Interactivity._PlaySoundAction.html) | An action that will play a sound to completion. |
| [PropertyChangedTrigger](https://www.noesisengine.com/docs/App.Interactivity._PropertyChangedTrigger.html) | Represents a trigger that performs actions when the bound data changes. |
| [RemoveElementAction](https://www.noesisengine.com/docs/App.Interactivity._RemoveElementAction.html) | An action that will remove the targeted element from the tree when invoked. |
| [RewindMediaAction](https://www.noesisengine.com/docs/App.Interactivity._RewindMediaAction.html) | Seeks a media element to position 0. |
| [RichText](https://www.noesisengine.com/docs/App.ApplicationLauncher._RichText.html) | Adds a *Text* attached property for [TextBlock](https://www.noesisengine.com/docs/Gui.Core._TextBlock.html) which formats [BBCode](https://en.wikipedia.org/wiki/BBCode) into Inlines. |
| [RiveControl](https://www.noesisengine.com/docs/App.RiveBase._RiveControl.html) | Renders a [Rive](https://rive.app/) scene. |
| [RiveInput](https://www.noesisengine.com/docs/App.RiveBase._RiveInput.html) | Represents an input value for the [RiveControl](https://www.noesisengine.com/docs/App.RiveBase._RiveControl.html) state machine. |
| [RiveRun](https://www.noesisengine.com/docs/App.RiveBase._RiveRun.html) | Represents a text run in the [RiveControl](https://www.noesisengine.com/docs/App.RiveBase._RiveControl.html) scene. |
| [RiveTriggerAction](https://www.noesisengine.com/docs/App.Rive._RiveTriggerAction.html) | An action that will fire a trigger in a [RiveControl](https://www.noesisengine.com/docs/App.RiveBase._RiveControl.html). |
| [SaturationEffect](https://www.noesisengine.com/docs/App.Shaders._SaturationEffect.html) | Use this effect to alter the saturation of an image. |
| [SelectAction](https://www.noesisengine.com/docs/App.Interactivity._SelectAction.html) | An action that will set *Selector.IsSelected* property to true on the asssociated object. |
| [SelectAllAction](https://www.noesisengine.com/docs/App.Interactivity._SelectAllAction.html) | An action that will select all the text on a text control. |
| [SetFocusAction](https://www.noesisengine.com/docs/App.Interactivity._SetFocusAction.html) | An action that will try to focus the associated element. |
| [SortComparer](https://www.noesisengine.com/docs/App.Interactivity._SortComparer.html) | Base class for Comparer object used by [CollectionSortBehavior](https://www.noesisengine.com/docs/App.Interactivity._CollectionSortBehavior.html). It compares 2 items. |
| [StopMediaAction](https://www.noesisengine.com/docs/App.Interactivity._StopMediaAction.html) | Stops a media element. |
| [StoryboardAction](https://www.noesisengine.com/docs/App.Interactivity._StoryboardAction.html) | An abstract action class that provides the ability to target a [Storyboard](https://www.noesisengine.com/docs/Gui.Animation._Storyboard.html). |
| [StoryboardCompletedTrigger](https://www.noesisengine.com/docs/App.Interactivity._StoryboardCompletedTrigger.html) | A trigger that listens for the completion of a [Storyboard](https://www.noesisengine.com/docs/Gui.Animation._Storyboard.html). |
| [StoryboardTrigger](https://www.noesisengine.com/docs/App.Interactivity._StoryboardTrigger.html) | An abstract trigger class that provides the ability to target a [Storyboard](https://www.noesisengine.com/docs/Gui.Animation._Storyboard.html). |
| [StringFilterPredicate](https://www.noesisengine.com/docs/App.Interactivity._StringFilterPredicate.html) | Predicate that matches a filter string against item text representation. |
| [StringSortComparer](https://www.noesisengine.com/docs/App.Interactivity._StringSortComparer.html) | Compares the text representation of two items for sorting. |
| [StyleInteraction](https://www.noesisengine.com/docs/App.Interactivity._StyleInteraction.html) | Allows setting a collection of *Interactivity* behaviors and triggers in a [Style](https://www.noesisengine.com/docs/Gui.Core._Style.html), so they are applied to all instances of the styled control. |
| [TargetedTriggerAction](https://www.noesisengine.com/docs/App.Interactivity._TargetedTriggerAction.html) | Represents an action that can be targeted to affect an object other than its *AssociatedObject*. |
| [TargetedTriggerActionT](https://www.noesisengine.com/docs/App.Interactivity._TargetedTriggerActionT.html) | Templatized base class for [TargetedTriggerAction](https://www.noesisengine.com/docs/App.Interactivity._TargetedTriggerAction.html). |
| [TimerTrigger](https://www.noesisengine.com/docs/App.Interactivity._TimerTrigger.html) | A trigger that is triggered by a specified event and fires after a delay. |
| [TintEffect](https://www.noesisengine.com/docs/App.Shaders._TintEffect.html) | This effect tints the source image by multiplying the source image by the specified color |
| [TranslateZoomRotateBehavior](https://www.noesisengine.com/docs/App.Interactivity._TranslateZoomRotateBehavior.html) | Moves the attached element in response to mouse drag and touch gestures on the element. |
| [TriggerAction](https://www.noesisengine.com/docs/App.Interactivity._TriggerAction.html) | Represents an attachable object that encapsulates a unit of functionality. |
| [TriggerActionCollection](https://www.noesisengine.com/docs/App.Interactivity._TriggerActionCollection.html) | Represents a collection of actions with a shared *AssociatedObject* and provides change notifications to its contents when that *AssociatedObject* changes. |
| [TriggerActionT](https://www.noesisengine.com/docs/App.Interactivity._TriggerActionT.html) | Templatized base class for [TriggerAction](https://www.noesisengine.com/docs/App.Interactivity._TriggerAction.html). |
| [TriggerBase](https://www.noesisengine.com/docs/App.Interactivity._TriggerBase.html) | Represents an object that can invoke *Actions* conditionally. |
| [TriggerBaseT](https://www.noesisengine.com/docs/App.Interactivity._TriggerBaseT.html) | Templatized base class for [TriggerBase](https://www.noesisengine.com/docs/App.Interactivity._TriggerBase.html). |
| [TriggerCollection](https://www.noesisengine.com/docs/App.Interactivity._TriggerCollection.html) | Represents a collection of triggers with a shared *AssociatedObject* and provides change notifications to its contents when that *AssociatedObject* changes. |
| [VignetteEffect](https://www.noesisengine.com/docs/App.Shaders._VignetteEffect.html) | Fades the input image at the edges to a user-set color. |
| [WavesBrush](https://www.noesisengine.com/docs/App.Shaders._WavesBrush.html) | [BrushShader](https://www.noesisengine.com/docs/Gui.Core._BrushShader.html) that paints a PSP wavy background effect. |
| [Window](https://www.noesisengine.com/docs/App.ApplicationLauncher._Window.html) | Provides the ability to create, configure, show, and manage the lifetime of windows. |