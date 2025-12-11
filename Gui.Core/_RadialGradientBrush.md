Source: https://www.noesisengine.com/docs/Gui.Core._RadialGradientBrush.html

# RadialGradientBrush Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.radialgradientbrush.aspx)

Paints an area with a radial gradient.

A focal point defines the beginning of the gradient, and a circle defines the end point of the gradient.

# Inheritance Hierarchy

• [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](../Gui.DependencySystem/_DependencyObject.md)

• [Freezable](../Gui.DependencySystem/_Freezable.md)

• [Animatable](_Animatable.md)

• [Brush](_Brush.md)

• [GradientBrush](_GradientBrush.md)

• *RadialGradientBrush*

# Properties

| Name | Description |
| --- | --- |
| ● *Center* | Gets or sets the center of the outermost circle of the radial gradient |
| ● *GradientOrigin* | Gets or sets the location of the two-dimensional focal point that defines the beginning of the gradient |
| ● *RadiusX* | Gets or sets the horizontal radius of the outermost circle of the radial gradient |
| ● *RadiusY* | Gets or sets the vertical radius of the outermost circle of a radial gradient |

● Dependency Property   ○ Reflection Property

## From [GradientBrush](_GradientBrush.md)

| Name | Description |
| --- | --- |
| ● *ColorInterpolationMode* | Gets or sets a ColorInterpolationMode enumeration that specifies how the gradient's colors are interpolated. |
| ● *GradientStops* | Gets or sets the brush's gradient stops |
| ● *MappingMode* | Gets or sets a BrushMappingMode enumeration that specifies whether the gradient brush's positioning coordinates are absolute or relative to the output area. |
| ● *SpreadMethod* | Gets or sets the type of spread method that specifies how to draw a gradient that starts or ends inside the bounds of the object to be painted. |

● Dependency Property   ○ Reflection Property

## From [Brush](_Brush.md)

| Name | Description |
| --- | --- |
| ● *Opacity* | Get/Set Opacity |
| ● *RelativeTransform* | Gets or sets the transformation that is applied to the brush using relative coordinates |
| ● *Transform* | Gets or sets the transformation that is applied to the brush. This transformation is applied after the brush's output has been mapped and positioned |

● Dependency Property   ○ Reflection Property

## From [Freezable](../Gui.DependencySystem/_Freezable.md)

| Name | Description |
| --- | --- |
| ○ *CanFreeze* | Gets a value that indicates whether the object can be made unmodifiable. |
| ○ *IsFrozen* | Gets a value that indicates whether the object is currently modifiable. |

● Dependency Property   ○ Reflection Property

## From [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md)

| Name | Description |
| --- | --- |
| ○ *ThreadId* | Gets the thread this [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md) is associated with. Returns NoThreadId when this object is not attached to any thread. |

● Dependency Property   ○ Reflection Property

# Attached Properties

RadialGradientBrush has no attached properties

# Methods

## From [GradientBrush](_GradientBrush.md)

| Name | Description |
| --- | --- |
|  *Clone()* | Hides [Freezable](../Gui.DependencySystem/_Freezable.md) methods for convenience |

## From [Brush](_Brush.md)

| Name | Description |
| --- | --- |
|  *IsTransparent()* | Indicates if this brush is transparent |
|  *TryParse(str, brush)* | Use this method to convert a Color string into a [SolidColorBrush](_SolidColorBrush.md) |

## From [Freezable](../Gui.DependencySystem/_Freezable.md)

| Name | Description |
| --- | --- |
|  *Clone()* | Creates a modifiable clone of the [Freezable](../Gui.DependencySystem/_Freezable.md), making deep copies of the object's values. When copying the object's dependency properties, this method copies expressions (which might no longer resolve) but not animations or their current values. The cloned Freezable::IsFrozen property is false even if the source's IsFrozen property is true. |
|  *CloneCurrentValue()* | Creates a modifiable clone (deep copy) of the [Freezable](../Gui.DependencySystem/_Freezable.md) using its current values. The cloned object's IsFrozen property is false even if the source's IsFrozen property is true. |
|  *Freeze()* | Makes the current object unmodifiable and sets its IsFrozen property to true. |
|  *GetAsFrozen()* | Creates a frozen copy of the [Freezable](../Gui.DependencySystem/_Freezable.md), using base (non-animated) property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. Throws if the [Freezable](../Gui.DependencySystem/_Freezable.md) cannot be frozen because it contains expressions or animated properties. |
|  *GetCurrentValueAsFrozen()* | Creates a frozen copy of the [Freezable](../Gui.DependencySystem/_Freezable.md) using current property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. |

## From [DependencyObject](../Gui.DependencySystem/_DependencyObject.md)

| Name | Description |
| --- | --- |
|  *ClearAnimation(dp)* | Clears the animation value of a property |
|  *ClearLocalValue(dp)* | Clears the local value of a property The property to be cleared is specified by a [DependencyProperty](../Gui.DependencySystem/_DependencyProperty.md) identifier |
|  *CoerceValue(dp)* | Coerces and validates the effective property value |
|  *DependencyPropertyChanged()* | Returns the PropertyChanged event |
|  *Destroyed()* | Destroyed delegate is raised when object is going to be destroyed |
|  *GetBaseValue(dp)* | Returns the base value without animation nor coerce (this never returns [Expression](../Gui.DependencySystem/_Expression.md) like GetLocalValue) |
|  *GetExpression(dp)* | Gets the expression, if any, used to evaluate the specified property value |
|  *GetLocalValue(dp)* | Returns the local value of a dependency property, if it exists |
|  *GetValue(dp)* | Returns the current effective value of a dependency property on this instance of a [DependencyObject](../Gui.DependencySystem/_DependencyObject.md) |
|  *GetValueObject(dp)* | Returns the current effective value of a dependency property on this instance of a [DependencyObject](../Gui.DependencySystem/_DependencyObject.md) as a boxed value |
|  *GetValueProvider(dp)* | Gets the provider that returns the effective value for the specified dependency property |
|  *HasAnimatedProperties()* | Returns true if there is any animated property |
|  *InvalidateProperty(dp, priority)* | Re-evaluates the effective value for the specified dependency property if necessary If null is passed, a full re-evaluation could be needed |
|  *IsCached(dp, provider)* | Returns if the value is stored in the cache. If true, the priority is returned in the provider field |
|  *IsSealed()* | Gets a value that indicates whether this instance is currently sealed (read-only) |
|  *SetAnimation(dp, value)* | Sets the animated value of a property |
|  *SetCurrentValue(dp, value)* | Sets the current value of a dependency property. The current value is set on the coerce field, without modifying source or animated value |
|  *SetCurrentValueObject(dp, value)* | Sets the current value of a dependency property using a boxed value |
|  *SetExpression(dp, expression)* | Sets the expression to be evaluated dynamically to obtain the value of the property |
|  *SetValue(dp, value)* | Sets the local value of a dependency property |
|  *SetValueObject(dp, value)* | Sets the local value (boxed) of a dependency property |

## From [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md)

| Name | Description |
| --- | --- |
|  *CheckAccess()* | Determines whether the calling thread has access to this [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md) |
|  *VerifyAccess()* | Enforces that the calling thread has access to this [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md) |

# Events

RadialGradientBrush has no events