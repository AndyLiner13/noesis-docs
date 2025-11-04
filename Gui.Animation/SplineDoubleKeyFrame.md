# SplineDoubleKeyFrame Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.animation.splinedoublekeyframe.aspx)

Animates from the Float value of the previous key frame to its own Value using splined interpolation.

This class is used as part of a [DoubleKeyFrameCollection](https://www.noesisengine.com/docs/Gui.Animation._DoubleKeyFrameCollection.html) in conjunction with a [DoubleAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._DoubleAnimationUsingKeyFrames.html) to animate a Double property value along a set of key frames.

A key frame defines a segment of the [DoubleAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._DoubleAnimationUsingKeyFrames.html) to which it belongs. Each key frame has a target Value and a [KeyTime](https://www.noesisengine.com/docs/Gui.Animation._KeyTime.html). The [KeyTime](https://www.noesisengine.com/docs/Gui.Animation._KeyTime.html) specifies the time at which the key frame's Value should be reached. A key frame animates from the target value of the previous key frame to its own target value. It starts when the previous key frame ends and ends when its own key time is reached.

Spline key frames like SplineDoubleKeyFrame creates a variable transition between values which is determined by the [KeySpline](https://www.noesisengine.com/docs/Gui.Animation._KeySpline.html) property. Splined interpolation can be used to achieve more realistic "real world" timing effects such as acceleration and deceleration.

## Inheritance Hierarchy

- [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html)
- [DependencyObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html)
- [Freezable](https://www.noesisengine.com/docs/Gui.DependencySystem._Freezable.html)
- [BaseKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._BaseKeyFrame.html)
- [DoubleKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DoubleKeyFrame.html)
- SplineDoubleKeyFrame

## Properties

### From [DoubleKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DoubleKeyFrame.html)

| Property | Description |
|----------|-------------|
| Value | Gets or sets the key frame's target value |

### From [BaseKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._BaseKeyFrame.html)

| Property | Description |
|----------|-------------|
| KeyTime | Gets or sets the time at which the key frame's target Value should be reached |

### From [Freezable](https://www.noesisengine.com/docs/Gui.DependencySystem._Freezable.html)

| Property | Description |
|----------|-------------|
| CanFreeze | Gets a value that indicates whether the object can be made unmodifiable. |
| IsFrozen | Gets a value that indicates whether the object is currently modifiable. |

### From [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html)

| Property | Description |
|----------|-------------|
| ThreadId | Gets the thread this DispatcherObject is associated with. Returns NoThreadId when this object is not attached to any thread. |

### Own Properties

| Property | Description |
|----------|-------------|
| KeySpline | Gets or sets the two control points that define animation progress for this key frame |

## Attached Properties

SplineDoubleKeyFrame has no attached properties

## Methods

### From [DoubleKeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DoubleKeyFrame.html)

| Method | Description |
|--------|-------------|
| InterpolateValue(baseValue, keyFrameProgress) | Returns the interpolated value of a specific key frame at the progress increment provided |

### From [Freezable](https://www.noesisengine.com/docs/Gui.DependencySystem._Freezable.html)

| Method | Description |
|--------|-------------|
| Clone() | Creates a modifiable clone of the Freezable, making deep copies of the object's values. When copying the object's dependency properties, this method copies expressions (which might no longer resolve) but not animations or their current values. The cloned Freezable::IsFrozen property is false even if the source's IsFrozen property is true. |
| CloneCurrentValue() | Creates a modifiable clone (deep copy) of the Freezable using its current values. The cloned object's IsFrozen property is false even if the source's IsFrozen property is true. |
| Freeze() | Makes the current object unmodifiable and sets its IsFrozen property to true. |
| GetAsFrozen() | Creates a frozen copy of the Freezable, using base (non-animated) property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. Throws if the Freezable cannot be frozen because it contains expressions or animated properties. |
| GetCurrentValueAsFrozen() | Creates a frozen copy of the Freezable using current property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. |

### From [DependencyObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html)

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

### From [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html)

| Method | Description |
|--------|-------------|
| CheckAccess() | Determines whether the calling thread has access to this DispatcherObject |
| VerifyAccess() | Enforces that the calling thread has access to this DispatcherObject |

## Events

SplineDoubleKeyFrame has no events