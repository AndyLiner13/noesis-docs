Source: https://www.noesisengine.com/docs/App.Shaders._PixelateEffect.html

# PixelateEffect Class

## namespace [NoesisApp](../Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

[ShaderEffect](../Gui.Core/_ShaderEffect.md) that pixelates a visual.

```
<StackPanel
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions"
  Orientation="Horizontal">
  <Image Source="Images/tulip.png"/>
  <Image Source="Images/tulip.png">
    <Image.Effect>
     <noesis:PixelateEffect Size="5"/>
    </Image.Effect>
  </Image>
</StackPanel>
```

![Pixelate.jpg](https://www.noesisengine.com/docs/Pixelate.jpg)

# Inheritance Hierarchy

• [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](../Gui.DependencySystem/_DependencyObject.md)

• [Freezable](../Gui.DependencySystem/_Freezable.md)

• [Animatable](../Gui.Core/_Animatable.md)

• [Effect](../Gui.Core/_Effect.md)

• [ShaderEffect](../Gui.Core/_ShaderEffect.md)

• *PixelateEffect*

# Properties

| Name | Description |
| --- | --- |
| ● *Size* | Gets or sets the amount of pixelation inside the shader |

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

PixelateEffect has no attached properties

# Methods

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

PixelateEffect has no events