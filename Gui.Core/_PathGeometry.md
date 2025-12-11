Source: https://www.noesisengine.com/docs/Gui.Core._PathGeometry.html

# PathGeometry Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](https://docs.microsoft.com/en-us/dotnet/api/system.windows.media.pathgeometry)

Represents a complex shape that may be composed of arcs, curves, ellipses, lines and rectangles.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
    <Path Fill="Red">
        <Path.Data>
            <PathGeometry>
                <PathFigure IsClosed="True" StartPoint="0,0">
                    <QuadraticBezierSegment Point1="25,25" Point2="50,0"/>
                    <LineSegment Point="100,0"/>
                    <ArcSegment Size="25,50" RotationAngle="30" Point="100,50"/>
                    <LineSegment Point="100,100"/>
                    <LineSegment Point="0,100"/>
                    <BezierSegment Point1="25,75" Point2="25,50" Point3="0,50"/>
                </PathFigure>
            </PathGeometry>
        </Path.Data>
    </Path>
</Grid>
```

# Inheritance Hierarchy

• [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](../Gui.DependencySystem/_DependencyObject.md)

• [Freezable](../Gui.DependencySystem/_Freezable.md)

• [Animatable](_Animatable.md)

• [Geometry](_Geometry.md)

• *PathGeometry*

# Properties

| Name | Description |
| --- | --- |
| ● *Figures* | Gets or sets the collection of [PathFigure](_PathFigure.md) objects that describe the path's contents |
| ● *FillRule* | Gets or sets a value that determines how the intersecting areas contained in this [PathGeometry](_PathGeometry.md) are combined |

● Dependency Property   ○ Reflection Property

## From [Geometry](_Geometry.md)

| Name | Description |
| --- | --- |
| ○ *Bounds* | Gets geometry bounds |
| ● *Transform* | Gets or sets the [Transform](_Transform.md) object applied to a [Geometry](_Geometry.md) |
| ● *TrimEnd* | Gets or sets the amount to trim the end of the geometry path |
| ● *TrimOffset* | Gets or sets the amount to offset trimming the geometry path |
| ● *TrimStart* | Gets or sets the amount to trim the start of the geometry path |

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

PathGeometry has no attached properties

# Methods

## From [Geometry](_Geometry.md)

| Name | Description |
| --- | --- |
|  *FillContains(point)* | Indicates whether the geometry contains the specified Point |
|  *GetRenderBounds(pen)* | Returns an axis-aligned rectangle that is exactly large enough to contain the geometry after it has been outlined with the specified [Pen](_Pen.md) |
|  *IsEmpty()* | Determines whether the object is empty |
|  *StrokeContains(pen, point)* | Determines whether the specified Point is contained in the stroke produced by applying the specified [Pen](_Pen.md) to the geometry |
|  *TryParse(str, result)* | Creates a new [Geometry](_Geometry.md) instance from the specified string |

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

PathGeometry has no events