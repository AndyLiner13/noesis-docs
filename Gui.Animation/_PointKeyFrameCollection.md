Source: https://www.noesisengine.com/docs/Gui.Animation._PointKeyFrameCollection.html

# PointKeyFrameCollection Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](https://docs.microsoft.com/en-us/dotnet/api/system.windows.media.animation.pointkeyframecollection)

Represents a collection of [PointKeyFrame](/Gui.Animation/_PointKeyFrame.md) objects.

This collection is used as part of a [PointAnimationUsingKeyFrames](/Gui.Animation/_PointAnimationUsingKeyFrames.md) to animate a Point property value along a set of key frames.

# Inheritance Hierarchy

• [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](/Gui.DependencySystem/_DependencyObject.md)

• [Freezable](/Gui.DependencySystem/_Freezable.md)

• [Animatable](/Gui.Core/_Animatable.md)

• [BaseFreezableCollection](/Gui.Core/_BaseFreezableCollection.md)

• [FreezableCollection](/Gui.Core/_FreezableCollection.md)

• *PointKeyFrameCollection*

# Properties

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

PointKeyFrameCollection has no attached properties

# Methods

## From [FreezableCollection](/Gui.Core/_FreezableCollection.md)

| Name | Description |
| --- | --- |
|  *Add(item)* | Adds an item to the collection. Returns The position into which the new element was inserted, or -1 to indicate that the item was not inserted into the collection |
|  *Clone()* | Creates a modifiable clone of this [FreezableCollection](/Gui.Core/_FreezableCollection.md) and its contents, making deep copies |
|  *CloneCurrentValue()* | Creates a modifiable copy of this [FreezableCollection](/Gui.Core/_FreezableCollection.md) and its contents, making deep copies of this object's current values |
|  *Contains(item)* | Determines whether the collection contains a specific value |
|  *Get(index)* | Gets the element at the specified index |
|  *IndexOf(item)* | Determines the index of a specific item in the collection. Returns -1 if not found |
|  *Insert(index, item)* | Inserts an item to the collection at the specified index |
|  *Remove(item)* | Removes the first occurrence of a specific object from the collection. Returns true if item was removed, false to indicate that the item was not found in the collection |
|  *Set(index, item)* | Sets the element at the specified index |

## From [BaseFreezableCollection](/Gui.Core/_BaseFreezableCollection.md)

| Name | Description |
| --- | --- |
|  *AddComponent(item)* | Adds an item to the collection. Returns The position into which the new element was inserted, or -1 to indicate that the item was not inserted into the collection |
|  *Clear()* | Removes all items from the collection |
|  *CollectionChanged()* | Occurs when the collection changes |
|  *Count()* | Gets the number of items in the collection |
|  *GetComponent(index)* | Gets the item at the specified index |
|  *IndexOfComponent(item)* | Determines the index of a specific item in the collection. Returns -1 if not found |
|  *InsertComponent(index, item)* | Inserts an item to the collection at the specified index |
|  *PropertyChanged()* | Occurs when a property value changes |
|  *RemoveAt(index)* | Removes the item at the specified index |
|  *SetComponent(index, item)* | Sets the item at the specified index |

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

PointKeyFrameCollection has no events