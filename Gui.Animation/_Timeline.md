Source: https://www.noesisengine.com/docs/Gui.Animation._Timeline.html

# Timeline Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.animation.timeline.aspx)

Defines a segment of time.

A timeline represents a segment of time. It provides properties that enable you to specify the length of that segment, when it should start, how many times it will repeat, how fast time progresses in that segment, and more.

# Inheritance Hierarchy

• [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](/Gui.DependencySystem/_DependencyObject.md)

• [Freezable](/Gui.DependencySystem/_Freezable.md)

• [Animatable](/Gui.Core/_Animatable.md)

• *Timeline*

• [AnimationTimeline](/Gui.Animation/_AnimationTimeline.md)

• [TimelineGroup](/Gui.Animation/_TimelineGroup.md)

# Properties

| Name | Description |
| --- | --- |
| ● *AccelerationRatio* | Gets or sets a value specifying the percentage of the timeline's [Duration](/Gui.Animation/_Duration.md) spent accelerating the passage of time from zero to its maximum rate |
| ○ *AccelerationRatio* | Gets or sets a value specifying the percentage of the timeline's [Duration](/Gui.Animation/_Duration.md) spent accelerating the passage of time from zero to its maximum rate |
| ● *AutoReverse* | Gets or sets a value that indicates whether the timeline plays in reverse after it completes a forward iteration |
| ○ *AutoReverse* | Gets or sets a value that indicates whether the timeline plays in reverse after it completes a forward iteration |
| ● *BeginTime* | Gets or sets the time at which this [Timeline](/Gui.Animation/_Timeline.md) should begin. A timeline's own *SpeedRatio* setting does not affect its BeginTime. For example, a timeline with a *BeginTime* of 5 seconds, a *SpeedRatio* of 2, and a parent timeline with a *SpeedRatio* of 1 starts after 5 seconds, not 2.5. |
| ○ *BeginTime* | Gets or sets the time at which this [Timeline](/Gui.Animation/_Timeline.md) should begin. A timeline's own *SpeedRatio* setting does not affect its BeginTime. For example, a timeline with a *BeginTime* of 5 seconds, a *SpeedRatio* of 2, and a parent timeline with a *SpeedRatio* of 1 starts after 5 seconds, not 2.5. |
| ● *DecelerationRatio* | Gets or sets a value specifying the percentage of the timeline's [Duration](/Gui.Animation/_Duration.md) spent decelerating the passage of time from its maximum rate to zero |
| ○ *DecelerationRatio* | Gets or sets a value specifying the percentage of the timeline's [Duration](/Gui.Animation/_Duration.md) spent decelerating the passage of time from its maximum rate to zero |
| ● *Duration* | Gets or sets the length of time for which this timeline plays, not counting repetitions |
| ● *FillBehavior* | Gets or sets a value that specifies how the animation behaves after it reaches the end of its active period |
| ● *Name* | Gets or sets the name of this [Timeline](/Gui.Animation/_Timeline.md) |
| ● *RepeatBehavior* | Gets or sets the repeating behavior of this timeline |
| ● *SpeedRatio* | Gets or sets the rate, relative to its parent, at which time progresses for this [Timeline](/Gui.Animation/_Timeline.md) |
| ○ *SpeedRatio* | Gets or sets the rate, relative to its parent, at which time progresses for this [Timeline](/Gui.Animation/_Timeline.md) |

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

| Name | Description |
| --- | --- |
| ● *DesiredFrameRate* | Gets or sets the desired frame rate for this timeline and its child timelines |

# Methods

| Name | Description |
| --- | --- |
|  *CalculateEffectiveDurations()* | Computes the effective durations of the timeline |
|  *CreateClock(timeManager, hasControllableRoot)* | Creates a new [Clock](/Gui.Animation/_Clock.md) from this [Timeline](/Gui.Animation/_Timeline.md) and specifies whether the new [Clock](/Gui.Animation/_Clock.md) is controllable. If this [Timeline](/Gui.Animation/_Timeline.md) has children, a tree of clocks is created with this [Timeline](/Gui.Animation/_Timeline.md) as the root. |
|  *GetEffectiveDuration()* | Calculated as TotalDuration / SpeedRatio + BeginTime |
|  *GetIterationDuration()* | Gets duration of a complete pass (with the reverse, if applicable) |
|  *GetNaturalDuration(clock)* | Gets the duration of the timeline when duration is set to automatic |
|  *GetSinglePassDuration()* | Gets duration of a single pass (without the reverse) |
|  *GetTotalDuration()* | Gets total duration of the animation (with repetitions and autoreverse, but without BeginTime nor SpeedRatio) |
|  *IsTotalDurationAbsolute()* | Indicates that the total duration is not affected by SpeedRatio |

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

| Name | Description |
| --- | --- |
| ◆ *Completed* | Occurs when the [Storyboard](/Gui.Animation/_Storyboard.md) object has completed playing |

▸ Routed Event    Non-routed Event   ◆ Delegate Event