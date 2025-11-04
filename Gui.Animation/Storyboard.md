# Storyboard Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.animation.storyboard.aspx)

A container timeline that provides object and property targeting information for its child animations.

## Inheritance Hierarchy

- [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html)
- [DependencyObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html)
- [Freezable](https://www.noesisengine.com/docs/Gui.DependencySystem._Freezable.html)
- [Animatable](https://www.noesisengine.com/docs/Gui.Core._Animatable.html)
- [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html)
- [TimelineGroup](https://www.noesisengine.com/docs/Gui.Animation._TimelineGroup.html)
- [ParallelTimeline](https://www.noesisengine.com/docs/Gui.Animation._ParallelTimeline.html)
- Storyboard

## Properties

### From [ParallelTimeline](https://www.noesisengine.com/docs/Gui.Animation._ParallelTimeline.html)

| Property | Description |
|----------|-------------|
| SlipBehavior | Gets or sets SlipBehavior property |

### From [TimelineGroup](https://www.noesisengine.com/docs/Gui.Animation._TimelineGroup.html)

| Property | Description |
|----------|-------------|
| Children | Gets or sets the collection of child Timeline objects |

### From [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html)

| Property | Description |
|----------|-------------|
| AccelerationRatio | Gets or sets a value specifying the percentage of the timeline's Duration spent accelerating the passage of time from zero to its maximum rate |
| AutoReverse | Gets or sets a value that indicates whether the timeline plays in reverse after it completes a forward iteration |
| BeginTime | Gets or sets the time at which this Timeline should begin. A timeline's own SpeedRatio setting does not affect its BeginTime. For example, a timeline with a BeginTime of 5 seconds, a SpeedRatio of 2, and a parent timeline with a SpeedRatio of 1 starts after 5 seconds, not 2.5. |
| DecelerationRatio | Gets or sets a value specifying the percentage of the timeline's Duration spent decelerating the passage of time from its maximum rate to zero |
| Duration | Gets or sets the length of time for which this timeline plays, not counting repetitions |
| FillBehavior | Gets or sets a value that specifies how the animation behaves after it reaches the end of its active period |
| Name | Gets or sets the name of this Timeline |
| RepeatBehavior | Gets or sets the repeating behavior of this timeline |
| SpeedRatio | Gets or sets the rate, relative to its parent, at which time progresses for this Timeline |

### From [Freezable](https://www.noesisengine.com/docs/Gui.DependencySystem._Freezable.html)

| Property | Description |
|----------|-------------|
| CanFreeze | Gets a value that indicates whether the object can be made unmodifiable. |
| IsFrozen | Gets a value that indicates whether the object is currently modifiable. |

### From [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html)

| Property | Description |
|----------|-------------|
| ThreadId | Gets the thread this DispatcherObject is associated with. Returns NoThreadId when this object is not attached to any thread. |

## Attached Properties

### Own Attached Properties

| Attached Property | Description |
|----------|-------------|
| Target | Gets or sets the object that should be animated |
| TargetName | Gets or sets the name of the object to animate |
| TargetProperty | Retrieves the TargetProperty value of the specified Timeline |

### From [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html)

| Attached Property | Description |
|----------|-------------|
| DesiredFrameRate | Gets or sets the desired frame rate for this timeline and its child timelines |

## Methods

### From [ParallelTimeline](https://www.noesisengine.com/docs/Gui.Animation._ParallelTimeline.html)

| Method | Description |
|--------|-------------|
| GetEffectiveDuration() | Calculated as TotalDuration / SpeedRatio + BeginTime |
| GetNaturalDuration(clock) | Gets the duration of the timeline when duration is set to automatic |

### From [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html)

| Method | Description |
|--------|-------------|
| CalculateEffectiveDurations() | Computes the effective durations of the timeline |
| CreateClock(timeManager, hasControllableRoot) | Creates a new Clock from this Timeline and specifies whether the new Clock is controllable. If this Timeline has children, a tree of clocks is created with this Timeline as the root. |
| GetEffectiveDuration() | Calculated as TotalDuration / SpeedRatio + BeginTime |
| GetIterationDuration() | Gets duration of a complete pass (with the reverse, if applicable) |
| GetNaturalDuration(clock) | Gets the duration of the timeline when duration is set to automatic |
| GetSinglePassDuration() | Gets duration of a single pass (without the reverse) |
| GetTotalDuration() | Gets total duration of the animation (with repetitions and autoreverse, but without BeginTime nor SpeedRatio) |
| IsTotalDurationAbsolute() | Indicates that the total duration is not affected by SpeedRatio |

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

### Own Methods

| Method | Description |
|--------|-------------|
| Begin() | Applies the animations associated with this Storyboard to their targets and initiates them |
| IsPaused() | Indicates if a controllable storyboard is paused |
| IsPlaying() | Indicates if a controllable storyboard is playing |
| Pause() | Pauses the Clock of the specified FrameworkElement associated with this Storyboard |
| Remove() | Removes the Clock objects that were created for this Storyboard. Animations that belong to this Storyboard no longer affect the properties they once animated, regardless of their FillBehavior setting |
| Resume() | Resumes the Clock that was created for this Storyboard |
| Seek(offset) | Seeks this Storyboard to the specified position on the next clock tick. The offset param is a positive or negative value that describes the amount by which the timeline should move forward or backward |
| Stop() | Stops the Clock that was created for this Storyboard |

## Events

### From [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html)

| Event | Description |
|-------|-------------|
| Completed | Occurs when the Storyboard object has completed playing |