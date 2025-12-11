Source: https://www.noesisengine.com/docs/Gui.Core._DataTrigger.html

# DataTrigger Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.datatrigger.aspx)

Represents a trigger that applies property values or performs actions when the bound data meets a specified condition.

[Style](_Style.md), [ControlTemplate](_ControlTemplate.md), and [DataTemplate](_DataTemplate.md) all have a triggers collection. A [DataTrigger](../App.Interactivity/_DataTrigger.md) allows you to set property values when the property value of the data object matches a specified Value. For example, if you are displaying a list of *Employee* objects, you may want the foreground color to be different based on each *Employee's* current attendance. In some scenarios it may be more suitable to create a converter or to use a [DataTemplateSelector](_DataTemplateSelector.md).

# Inheritance Hierarchy

• [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](../Gui.DependencySystem/_DependencyObject.md)

• [BaseTrigger](_BaseTrigger.md)

• *DataTrigger*

# Properties

| Name | Description |
| --- | --- |
| ○ *Binding* | Gets or sets the binding that produces the property value of the data object. |
| ○ *Setters* | Gets a collection of [Setter](_Setter.md) objects, which describe the property values to apply when the data item meets the specified condition. |
| ○ *Value* | Gets or sets the value to be compared with the property value of the data object. |

● Dependency Property   ○ Reflection Property

## From [BaseTrigger](_BaseTrigger.md)

| Name | Description |
| --- | --- |
| ○ *EnterActions* | Gets a collection of [TriggerAction](../App.Interactivity/_TriggerAction.md) objects to apply when the trigger object becomes active. This property does not apply to the [EventTrigger](../App.Interactivity/_EventTrigger.md) class |
| ○ *ExitActions* | Gets a collection of [TriggerAction](../App.Interactivity/_TriggerAction.md) objects to apply when the trigger object becomes inactive. This property does not apply to the [EventTrigger](../App.Interactivity/_EventTrigger.md) class |

● Dependency Property   ○ Reflection Property

## From [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md)

| Name | Description |
| --- | --- |
| ○ *ThreadId* | Gets the thread this [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md) is associated with. Returns NoThreadId when this object is not attached to any thread. |

● Dependency Property   ○ Reflection Property

# Attached Properties

DataTrigger has no attached properties

# Methods

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

DataTrigger has no events