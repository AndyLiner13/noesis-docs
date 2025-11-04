# GeometryGroup Class

## namespace Noesis | MSDN

Represents a composite geometry, composed of other Geometry objects.

A GeometryGroup creates a composite geometry from any number of geometry objects. GeometryGroup uses the FillRule property to specify how its geometry objects are combined.

# Inheritance Hierarchy

 • DispatcherObject • DependencyObject • Freezable • Animatable • Geometry • GeometryGroup

# Properties

## From Geometry

| Property | Description |
|----------|-------------|
| Bounds | Gets geometry bounds |
| Transform | Gets or sets the Transform object applied to a Geometry |
| TrimEnd | Gets or sets the amount to trim the end of the geometry path |
| TrimOffset | Gets or sets the amount to offset trimming the geometry path |
| TrimStart | Gets or sets the amount to trim the start of the geometry path |

## From Freezable

| Property | Description |
|----------|-------------|
| CanFreeze | Gets a value that indicates whether the object can be made unmodifiable. |
| IsFrozen | Gets a value that indicates whether the object is currently modifiable. |

## From DispatcherObject

| Property | Description |
|----------|-------------|
| ThreadId | Gets the thread this DispatcherObject is associated with. Returns NoThreadId when this object is not attached to any thread. |

## Own Properties

| Property | Description |
|----------|-------------|
| Children | Gets or sets the GeometryCollection that contains the objects that define this GeometryGroup |
| FillRule | Gets or sets how the intersecting areas of the objects contained in this GeometryGroup are combined |

# Attached Properties

GeometryGroup has no attached properties

# Methods

## From Geometry

| Method | Description |
|--------|-------------|
| FillContains(point) | Indicates whether the geometry contains the specified Point |
| GetRenderBounds(pen) | Returns an axis-aligned rectangle that is exactly large enough to contain the geometry after it has been outlined with the specified Pen |
| IsEmpty() | Determines whether the object is empty |
| StrokeContains(pen, point) | Determines whether the specified Point is contained in the stroke produced by applying the specified Pen to the geometry |
| TryParse(str, result) | Creates a new Geometry instance from the specified string |

## From Freezable

| Method | Description |
|--------|-------------|
| Clone() | Creates a modifiable clone of the Freezable, making deep copies of the object's values. When copying the object's dependency properties, this method copies expressions (which might no longer resolve) but not animations or their current values. The cloned Freezable::IsFrozen property is false even if the source's IsFrozen property is true. |
| CloneCurrentValue() | Creates a modifiable clone (deep copy) of the Freezable using its current values. The cloned object's IsFrozen property is false even if the source's IsFrozen property is true. |
| Freeze() | Makes the current object unmodifiable and sets its IsFrozen property to true. |
| GetAsFrozen() | Creates a frozen copy of the Freezable, using base (non-animated) property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. Throws if the Freezable cannot be frozen because it contains expressions or animated properties. |
| GetCurrentValueAsFrozen() | Creates a frozen copy of the Freezable using current property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. |

## From DependencyObject

| Method | Description |
|--------|-------------|
| ClearAnimation(dp) | Clears the animation value of a property |
| ClearLocalValue(dp) | Clears the local value of a property The property to be cleared is specified by a DependencyProperty identifier |
| CoerceValue(dp) | Coerces and validates the effective property value |
| DependencyPropertyChanged() | Returns the PropertyChanged event |
| Destroyed() | Destroyed delegate is raised when object is going to be destroyed |
| GetBaseValue(dp) | Returns the base value without animation nor coerce (this never returns Expression like GetLocalValue) |
| GetExpression(dp) | Gets the expression, if any, used to evaluate the specified property value |
| GetLocalValue(dp) | Returns the local value of a dependency property, if it exists |
| GetValue(dp) | Returns the current effective value of a dependency property on this instance of a DependencyObject |
| GetValueObject(dp) | Returns the current effective value of a dependency property on this instance of a DependencyObject as a boxed value |
| GetValueProvider(dp) | Gets the provider that returns the effective value for the specified dependency property |
| HasAnimatedProperties() | Returns true if there is any animated property |
| InvalidateProperty(dp, priority) | Re-evaluates the effective value for the specified dependency property if necessary If null is passed, a full re-evaluation could be needed |
| IsCached(dp, provider) | Returns if the value is stored in the cache. If true, the priority is returned in the provider field |
| IsSealed() | Gets a value that indicates whether this instance is currently sealed (read-only) |
| SetAnimation(dp, value) | Sets the animated value of a property |
| SetCurrentValue(dp, value) | Sets the current value of a dependency property. The current value is set on the coerce field, without modifying source or animated value |
| SetCurrentValueObject(dp, value) | Sets the current value of a dependency property using a boxed value |
| SetExpression(dp, expression) | Sets the expression to be evaluated dynamically to obtain the value of the property |
| SetValue(dp, value) | Sets the local value of a dependency property |
| SetValueObject(dp, value) | Sets the local value (boxed) of a dependency property |

## From DispatcherObject

| Method | Description |
|--------|-------------|
| CheckAccess() | Determines whether the calling thread has access to this DispatcherObject |
| VerifyAccess() | Enforces that the calling thread has access to this DispatcherObject |

# Events

GeometryGroup has no events