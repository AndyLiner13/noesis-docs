Source: https://www.noesisengine.com/docs/App.Interactivity._InvokeCommandAction.html

# InvokeCommandAction Class

## namespace [NoesisApp](/Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

Executes the specified *ICommand* when invoked.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors">
  <Button Content="Close">
    <b:Interaction.Triggers>
      <b:EventTrigger EventName="Click">
        <b:InvokeCommandAction Command="{Binding CloseCommand}" CommandParameter="Force"/>
      </b:EventTrigger>
    </b:Interaction.Triggers>
  </Button>
</Grid>
```

The command can use the CommandParameter specified in the action (as shown in the example above) or you can indicate that it should use the parameter coming from the trigger invocation.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors">
  <Button Content="Close">
    <b:Interaction.Triggers>
      <b:KeyTrigger Key="A" ActiveOnFocus="True">
        <b:InvokeCommandAction Command="{Binding KeyPressCommand}" PassEventArgsToCommand="True"/>
      </b:KeyTrigger>
    </b:Interaction.Triggers>
  </Button>
</Grid>
```

In the last case the event args will be boxed as the parameter and can be obtained like this:

```
void OnKeyPressCommand(BaseComponent* param)
{
    const EventArgs* args = Boxing::Unbox<const EventArgs*>(param);
    const KeyEventArgs& e = *(const KeyEventArgs*)args;
    // ...
}
```

# Inheritance Hierarchy

• [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](/Gui.DependencySystem/_DependencyObject.md)

• [Freezable](/Gui.DependencySystem/_Freezable.md)

• [Animatable](/Gui.Core/_Animatable.md)

• [AttachableObject](/App.Interactivity/_AttachableObject.md)

• [TriggerAction](/App.Interactivity/_TriggerAction.md)

• [TriggerActionT](/App.Interactivity/_TriggerActionT.md)

• *InvokeCommandAction*

# Properties

| Name | Description |
| --- | --- |
| ● *Command* | Gets or sets the command this action should invoke. Has more priority than *CommandName* |
| ○ *CommandName* | Gets or sets the name of the command this action should invoke |
| ● *CommandParameter* | Gets or sets the command parameter |
| ● *EventArgsConverter* | Gets or sets the IValueConverter that is used to convert the EventArgs passed to the Command as a parameter. If the CommandParameter or EventArgsParameterPath properties are set, this property is ignored |
| ● *EventArgsConverterParameter* | Gets or sets the parameter that is passed to the EventArgsConverter |
| ● *EventArgsParameterPath* | Gets or sets the property path used to extract a value from the EventArgs to pass to the Command as a parameter. If the CommandParameter propert is set, this property is ignored |
| ○ *PassEventArgsToCommand* | Specifies whether the EventArgs of the event that triggered this action should be passed to the Command as a parameter. If the Command, EventArgsParameterPath, or EventArgsConverter properties are set, this property is ignored |

● Dependency Property   ○ Reflection Property

## From [TriggerAction](/App.Interactivity/_TriggerAction.md)

| Name | Description |
| --- | --- |
| ● *IsEnabled* | Gets or sets a value indicating whether this action will run when invoked |

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

InvokeCommandAction has no attached properties

# Methods

## From [TriggerAction](/App.Interactivity/_TriggerAction.md)

| Name | Description |
| --- | --- |
|  *CallInvoke(parameter)* | Attempts to invoke the action |

## From [AttachableObject](/App.Interactivity/_AttachableObject.md)

| Name | Description |
| --- | --- |
|  *Attach(associatedObject)* | Attaches to the specified object |
|  *Detach()* | Detaches this instance from its associated object |

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

InvokeCommandAction has no events