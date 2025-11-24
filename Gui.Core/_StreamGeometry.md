Source: https://www.noesisengine.com/docs/Gui.Core._StreamGeometry.html

# StreamGeometry Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.streamgeometry.aspx)

Defines a geometric shape, described using a [StreamGeometryContext](/Gui.Core/_StreamGeometryContext.md) or a SVG command string as described in the [W3C](http://www.w3.org/TR/SVG11/paths.html) specs.

```
StreamGeometry geometry = new StreamGeometry();

using (StreamGeometryContext context = geometry.Open())
{
    context.BeginFigure(new Point(100.0f, 100.0f), true, true);
    context.LineTo(new Point(200.0f, 100.0f), false, false);
    context.LineTo(new Point(200.0f, 200.0f), false, false);
}
```

```
StreamGeometry geometry = new StreamGeometry();
geometry.SetData("M 100, 100 L 200, 100 200, 200 Z");
```

```
<Canvas xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">
  <Path Fill="#FFF2F000" Data="M 100, 100 L 200, 100 200, 200 Z"/>
</Canvas>
```

# Inheritance Hierarchy

• [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](/Gui.DependencySystem/_DependencyObject.md)

• [Freezable](/Gui.DependencySystem/_Freezable.md)

• [Animatable](/Gui.Core/_Animatable.md)

• [Geometry](/Gui.Core/_Geometry.md)

• *StreamGeometry*

# Properties

| Name | Description |
| --- | --- |
| ● *FillRule* | Gets or sets a value that determines how the intersecting areas contained in this [StreamGeometry](/Gui.Core/_StreamGeometry.md) are combined |

● Dependency Property   ○ Reflection Property

## From [Geometry](/Gui.Core/_Geometry.md)

| Name | Description |
| --- | --- |
| ○ *Bounds* | Gets geometry bounds |
| ● *Transform* | Gets or sets the [Transform](/Gui.Core/_Transform.md) object applied to a [Geometry](/Gui.Core/_Geometry.md) |
| ● *TrimEnd* | Gets or sets the amount to trim the end of the geometry path |
| ● *TrimOffset* | Gets or sets the amount to offset trimming the geometry path |
| ● *TrimStart* | Gets or sets the amount to trim the start of the geometry path |

● Dependency Property   ○ Reflection Property

## From [Freezable](/Gui.DependencySystem/_Freezable.md)

| Name | Description |
| --- | --- |
| ○ *CanFreeze* | Gets a value that indicates whether the object can be made unmodifiable. |
| ○ *IsFrozen* | Gets a value that indicates whether the object is currently modifiable. |

● Dependency Property   ○ Reflection Property

## From [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

| Name | Description |
| --- | --- |
| ○ *ThreadId* | Gets the thread this [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) is associated with. Returns NoThreadId when this object is not attached to any thread. |

● Dependency Property   ○ Reflection Property

# Attached Properties

StreamGeometry has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *GetCommandBuffer()* | Returns the command buffer that encodes the geometry's path instructions |
|  *GetCommands()* | Returns an iterator of commands describing the path |
|  *Open()* | Opens a [StreamGeometryContext](/Gui.Core/_StreamGeometryContext.md) for defining the geometry using drawing commands |
|  *SetCommandBuffer(commands)* | Sets the command buffer that encodes the geometry's path instructions. This provides an alternative to using 'Open()' and manually writing to the [StreamGeometryContext](/Gui.Core/_StreamGeometryContext.md) |
|  *SetData(data)* | Rebuild the geometry with a new set of [SVG](http://www.w3.org/TR/SVG11/paths.html) path commands  Example:  ``` M 100, 100 L 200, 100 200, 200 Z ``` |
|  *TryParse(str, result)* | Constructs a [StreamGeometry](/Gui.Core/_StreamGeometry.md) from SVG path commands |

## From [Geometry](/Gui.Core/_Geometry.md)

| Name | Description |
| --- | --- |
|  *FillContains(point)* | Indicates whether the geometry contains the specified Point |
|  *GetRenderBounds(pen)* | Returns an axis-aligned rectangle that is exactly large enough to contain the geometry after it has been outlined with the specified [Pen](/Gui.Core/_Pen.md) |
|  *IsEmpty()* | Determines whether the object is empty |
|  *StrokeContains(pen, point)* | Determines whether the specified Point is contained in the stroke produced by applying the specified [Pen](/Gui.Core/_Pen.md) to the geometry |
|  *TryParse(str, result)* | Creates a new [Geometry](/Gui.Core/_Geometry.md) instance from the specified string |

## From [Freezable](/Gui.DependencySystem/_Freezable.md)

| Name | Description |
| --- | --- |
|  *Clone()* | Creates a modifiable clone of the [Freezable](/Gui.DependencySystem/_Freezable.md), making deep copies of the object's values. When copying the object's dependency properties, this method copies expressions (which might no longer resolve) but not animations or their current values. The cloned Freezable::IsFrozen property is false even if the source's IsFrozen property is true. |
|  *CloneCurrentValue()* | Creates a modifiable clone (deep copy) of the [Freezable](/Gui.DependencySystem/_Freezable.md) using its current values. The cloned object's IsFrozen property is false even if the source's IsFrozen property is true. |
|  *Freeze()* | Makes the current object unmodifiable and sets its IsFrozen property to true. |
|  *GetAsFrozen()* | Creates a frozen copy of the [Freezable](/Gui.DependencySystem/_Freezable.md), using base (non-animated) property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. Throws if the [Freezable](/Gui.DependencySystem/_Freezable.md) cannot be frozen because it contains expressions or animated properties. |
|  *GetCurrentValueAsFrozen()* | Creates a frozen copy of the [Freezable](/Gui.DependencySystem/_Freezable.md) using current property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. |

## From [DependencyObject](/Gui.DependencySystem/_DependencyObject.md)

| Name | Description |
| --- | --- |
|  *ClearAnimation(dp)* | Clears the animation value of a property |
|  *ClearLocalValue(dp)* | Clears the local value of a property The property to be cleared is specified by a [DependencyProperty](/Gui.DependencySystem/_DependencyProperty.md) identifier |
|  *CoerceValue(dp)* | Coerces and validates the effective property value |
|  *DependencyPropertyChanged()* | Returns the PropertyChanged event |
|  *Destroyed()* | Destroyed delegate is raised when object is going to be destroyed |
|  *GetBaseValue(dp)* | Returns the base value without animation nor coerce (this never returns [Expression](/Gui.DependencySystem/_Expression.md) like GetLocalValue) |
|  *GetExpression(dp)* | Gets the expression, if any, used to evaluate the specified property value |
|  *GetLocalValue(dp)* | Returns the local value of a dependency property, if it exists |
|  *GetValue(dp)* | Returns the current effective value of a dependency property on this instance of a [DependencyObject](/Gui.DependencySystem/_DependencyObject.md) |
|  *GetValueObject(dp)* | Returns the current effective value of a dependency property on this instance of a [DependencyObject](/Gui.DependencySystem/_DependencyObject.md) as a boxed value |
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

## From [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

| Name | Description |
| --- | --- |
|  *CheckAccess()* | Determines whether the calling thread has access to this [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) |
|  *VerifyAccess()* | Enforces that the calling thread has access to this [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) |

# Events

StreamGeometry has no events