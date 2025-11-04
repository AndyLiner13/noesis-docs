# DataTrigger Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.datatrigger.aspx)

Represents a trigger that applies property values or performs actions when the bound data meets a specified condition.

# Inheritance Hierarchy

 • [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html) • [DependencyObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html) • [BaseTrigger](https://www.noesisengine.com/docs/Gui.Core._BaseTrigger.html) • DataTrigger

# Properties

| Property | Description |
|----------|-------------|
| Binding | Gets or sets the binding that produces the property value of the data object. |
| Setters | Gets a collection of Setter objects, which describe the property values to apply when the data item meets the specified condition. |
| Value | Gets or sets the value to be compared with the property value of the data object. |

## From [BaseTrigger](https://www.noesisengine.com/docs/Gui.Core._BaseTrigger.html)

| Property | Description |
|----------|-------------|
| EnterActions | Gets a collection of TriggerAction objects to apply when the trigger object becomes active. This property does not apply to the EventTrigger class |
| ExitActions | Gets a collection of TriggerAction objects to apply when the trigger object becomes inactive. This property does not apply to the EventTrigger class |

## From [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html)

| Property | Description |
|----------|-------------|
| ThreadId | Gets the thread this DispatcherObject is associated with. Returns NoThreadId when this object is not attached to any thread. |

# Attached Properties

DataTrigger has no attached properties

# Methods

## From [DependencyObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html)

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

## From [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html)

| Method | Description |
|--------|-------------|
| CheckAccess() | Determines whether the calling thread has access to this DispatcherObject |
| VerifyAccess() | Enforces that the calling thread has access to this DispatcherObject |

# Events

DataTrigger has no events