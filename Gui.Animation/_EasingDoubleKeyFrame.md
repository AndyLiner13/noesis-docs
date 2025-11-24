Source: https://www.noesisengine.com/docs/Gui.Animation._EasingDoubleKeyFrame.html

# EasingDoubleKeyFrame Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.animation.easingdoublekeyframe.aspx)

A class that enables you to associate easing functions with a [DoubleAnimationUsingKeyFrames](/Gui.Animation/_DoubleAnimationUsingKeyFrames.md) key frame animation.

The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling), and then bounces to a stop.

```
<Rectangle Name="myRectangle" Width="200" Height="200" Fill="Blue">
  <Rectangle.Triggers>
    <EventTrigger RoutedEvent="Rectangle.MouseDown">
      <BeginStoryboard>
        <Storyboard>
          <DoubleAnimationUsingKeyFrames
            Storyboard.TargetProperty="Height"
            Storyboard.TargetName="myRectangle">

            <!-- This keyframe animates the ellipse up to the crest
                             where it slows down and stops. -->
            <EasingDoubleKeyFrame Value="30" KeyTime="00:00:02">
              <EasingDoubleKeyFrame.EasingFunction>
                <CubicEase EasingMode="EaseOut"/>
              </EasingDoubleKeyFrame.EasingFunction>
            </EasingDoubleKeyFrame>

            <!-- This keyframe animates the ellipse back down and makes
                             it bounce. -->
            <EasingDoubleKeyFrame Value="200" KeyTime="00:00:06">
              <EasingDoubleKeyFrame.EasingFunction>
                <BounceEase Bounces="5" EasingMode="EaseOut"/>
              </EasingDoubleKeyFrame.EasingFunction>
            </EasingDoubleKeyFrame>

          </DoubleAnimationUsingKeyFrames>
        </Storyboard>
      </BeginStoryboard>
    </EventTrigger>
  </Rectangle.Triggers>
</Rectangle>
```

This class is used as part of a [DoubleKeyFrameCollection](/Gui.Animation/_DoubleKeyFrameCollection.md) in conjunction with a [DoubleAnimationUsingKeyFrames](/Gui.Animation/_DoubleAnimationUsingKeyFrames.md) to animate a Double property value along a set of key frames. This [DoubleKeyFrame](/Gui.Animation/_DoubleKeyFrame.md) interpolates between the Double value of the previous key frame and its own value linearly with an easing function to produce its output value.

# Inheritance Hierarchy

• [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](/Gui.DependencySystem/_DependencyObject.md)

• [Freezable](/Gui.DependencySystem/_Freezable.md)

• [BaseKeyFrame](/Gui.Animation/_BaseKeyFrame.md)

• [DoubleKeyFrame](/Gui.Animation/_DoubleKeyFrame.md)

• *EasingDoubleKeyFrame*

# Properties

| Name | Description |
| --- | --- |
| ● *EasingFunction* | Gets or sets the easing function applied to the key frame |

● Dependency Property   ○ Reflection Property

## From [DoubleKeyFrame](/Gui.Animation/_DoubleKeyFrame.md)

| Name | Description |
| --- | --- |
| ● *Value* | Gets or sets the key frame's target value |

● Dependency Property   ○ Reflection Property

## From [BaseKeyFrame](/Gui.Animation/_BaseKeyFrame.md)

| Name | Description |
| --- | --- |
| ● *KeyTime* | Gets or sets the time at which the key frame's target *Value* should be reached |

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

EasingDoubleKeyFrame has no attached properties

# Methods

## From [DoubleKeyFrame](/Gui.Animation/_DoubleKeyFrame.md)

| Name | Description |
| --- | --- |
|  *InterpolateValue(baseValue, keyFrameProgress)* | Returns the interpolated value of a specific key frame at the progress increment provided |

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

EasingDoubleKeyFrame has no events