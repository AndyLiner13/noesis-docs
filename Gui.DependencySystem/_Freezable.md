Source: https://www.noesisengine.com/docs/Gui.DependencySystem._Freezable.html

# Freezable Class

## namespace [Noesis](../Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](https://docs.microsoft.com/en-us/dotnet/api/system.windows.freezable)

Defines an object that has a modifiable state and a read-only (frozen) state.

Classes that derive from [Freezable](_Freezable.md) provide detailed change notification, can be made immutable, and can clone themselves. The [Freezable](_Freezable.md) class provides special features that can help improve application performance when using objects that are expensive to modify or copy.

A class that derives from [Freezable](_Freezable.md) gains the following features:

- Special states: a read-only (frozen) state and a writable state.
- Thread safety: a frozen [Freezable](_Freezable.md) object can be shared across threads.
- Detailed change notification: Unlike other [DependencyObject](_DependencyObject.md) objects, a [Freezable](_Freezable.md) object
  provides change notifications when sub-property values change
- Easy cloning: the [Freezable](_Freezable.md) class has already implemented several methods that produce
  deep clones

# Inheritance Hierarchy

• [DispatcherObject](_DispatcherObject.md)

• [DependencyObject](_DependencyObject.md)

• *Freezable*

• [Animatable](../Gui.Core/_Animatable.md)

• [BaseKeyFrame](../Gui.Animation/_BaseKeyFrame.md)

• [InputBinding](../Gui.Core/_InputBinding.md)

• [KeySpline](../Gui.Animation/_KeySpline.md)

# Properties

| Name | Description |
| --- | --- |
| ○ *CanFreeze* | Gets a value that indicates whether the object can be made unmodifiable. |
| ○ *IsFrozen* | Gets a value that indicates whether the object is currently modifiable. |

● Dependency Property   ○ Reflection Property

## From [DispatcherObject](_DispatcherObject.md)

| Name | Description |
| --- | --- |
| ○ *ThreadId* | Gets the thread this [DispatcherObject](_DispatcherObject.md) is associated with. Returns NoThreadId when this object is not attached to any thread. |

● Dependency Property   ○ Reflection Property

# Attached Properties

Freezable has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *Clone()* | Creates a modifiable clone of the [Freezable](_Freezable.md), making deep copies of the object's values. When copying the object's dependency properties, this method copies expressions (which might no longer resolve) but not animations or their current values. The cloned Freezable::IsFrozen property is false even if the source's IsFrozen property is true. |
|  *CloneCurrentValue()* | Creates a modifiable clone (deep copy) of the [Freezable](_Freezable.md) using its current values. The cloned object's IsFrozen property is false even if the source's IsFrozen property is true. |
|  *Freeze()* | Makes the current object unmodifiable and sets its IsFrozen property to true. |
|  *GetAsFrozen()* | Creates a frozen copy of the [Freezable](_Freezable.md), using base (non-animated) property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. Throws if the [Freezable](_Freezable.md) cannot be frozen because it contains expressions or animated properties. |
|  *GetCurrentValueAsFrozen()* | Creates a frozen copy of the [Freezable](_Freezable.md) using current property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. |

## From [DependencyObject](_DependencyObject.md)

| Name | Description |
| --- | --- |
|  *ClearAnimation(dp)* | Clears the animation value of a property |
|  *ClearLocalValue(dp)* | Clears the local value of a property The property to be cleared is specified by a [DependencyProperty](_DependencyProperty.md) identifier |
|  *CoerceValue(dp)* | Coerces and validates the effective property value |
|  *DependencyPropertyChanged()* | Returns the PropertyChanged event |
|  *Destroyed()* | Destroyed delegate is raised when object is going to be destroyed |
|  *GetBaseValue(dp)* | Returns the base value without animation nor coerce (this never returns [Expression](_Expression.md) like GetLocalValue) |
|  *GetExpression(dp)* | Gets the expression, if any, used to evaluate the specified property value |
|  *GetLocalValue(dp)* | Returns the local value of a dependency property, if it exists |
|  *GetValue(dp)* | Returns the current effective value of a dependency property on this instance of a [DependencyObject](_DependencyObject.md) |
|  *GetValueObject(dp)* | Returns the current effective value of a dependency property on this instance of a [DependencyObject](_DependencyObject.md) as a boxed value |
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

## From [DispatcherObject](_DispatcherObject.md)

| Name | Description |
| --- | --- |
|  *CheckAccess()* | Determines whether the calling thread has access to this [DispatcherObject](_DispatcherObject.md) |
|  *VerifyAccess()* | Enforces that the calling thread has access to this [DispatcherObject](_DispatcherObject.md) |

# Events

Freezable has no events