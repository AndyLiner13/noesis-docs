Source: https://www.noesisengine.com/docs/App.Interactivity._DataEventTrigger.html

# DataEventTrigger Class

## namespace [NoesisApp](/Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

Represents a trigger which fires when an event is raised on an object. Can be used to trigger from events on the data context, as opposed to a standard [EventTrigger](/App.Interactivity/_EventTrigger.md) which uses routed events on a [FrameworkElement](/Gui.Core/_FrameworkElement.md).

```
 <Grid
   xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
   xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
   xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <TextBlock Text="Download Finished!" Visibility="Collapsed">
    <b:Interaction.Triggers>
      <noesis:DataEventTrigger Source="{Binding}" EventName="DownloadFinished">
        <b:ChangePropertyAction PropertyName="Visibility" Value="Visible"/>
      </noesis:DataEventTrigger>
    </b:Interaction.Triggers>
  </TextBlock>
</Grid>
```

Previous xaml expects that data context exposes an event named *DownloadFinished*:

C++

```
struct ViewModel: public BaseComponent
{
  ...

  void OnDownloadFinished()
  {
    _downloadFinished(this, EventArgs::Empty);
  }

  EventHandler _downloadFinished;

  NS_IMPLEMENT_INLINE_REFLECTION(ViewModel, BaseComponent)
  {
    NsEvent("DownloadFinished", &ViewModel::_downloadFinished);
  }
};
```

C#

```
public class ViewModel
{
  ...

  private void OnDownloadFinished()
  {
    DownloadFinished?.Invoke(this, System.EventArgs.Empty);
  }

  public event System.EventHandler DownloadFinished;
}
```

# Inheritance Hierarchy

• [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](/Gui.DependencySystem/_DependencyObject.md)

• [Freezable](/Gui.DependencySystem/_Freezable.md)

• [Animatable](/Gui.Core/_Animatable.md)

• [AttachableObject](/App.Interactivity/_AttachableObject.md)

• [TriggerBase](/App.Interactivity/_TriggerBase.md)

• [TriggerBaseT](/App.Interactivity/_TriggerBaseT.md)

• *DataEventTrigger*

# Properties

| Name | Description |
| --- | --- |
| ● *EventName* | Gets or sets the name of the event which fires the trigger |
| ● *Source* | Gets or sets the source object for the event |

● Dependency Property   ○ Reflection Property

## From [TriggerBase](/App.Interactivity/_TriggerBase.md)

| Name | Description |
| --- | --- |
| ● *Actions* | Gets the actions associated with this trigger |

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

DataEventTrigger has no attached properties

# Methods

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

## From [TriggerBase](/App.Interactivity/_TriggerBase.md)

| Name | Description |
| --- | --- |
| ◆ *PreviewInvoke* | Raised just before invoking all associated actions |

▸ Routed Event    Non-routed Event   ◆ Delegate Event