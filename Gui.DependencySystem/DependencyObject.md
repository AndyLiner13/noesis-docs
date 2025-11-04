# DependencyObject Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.dependencyobject.aspx)

Represents an object that participates in the dependency property system.

# Inheritance Hierarchy

 • [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html) • DependencyObject • [BaseTrigger](https://www.noesisengine.com/docs/Gui.Core._BaseTrigger.html) • [CollectionViewSource](https://www.noesisengine.com/docs/Gui.Core._CollectionViewSource.html) • [Freezable](https://www.noesisengine.com/docs/Gui.DependencySystem._Freezable.html) • [TriggerAction](https://www.noesisengine.com/docs/Gui.Core._TriggerAction.html) • [Visual](https://www.noesisengine.com/docs/Gui.Core._Visual.html) • [VisualState](https://www.noesisengine.com/docs/Gui.Animation._VisualState.html) • [VisualStateGroup](https://www.noesisengine.com/docs/Gui.Animation._VisualStateGroup.html) • [VisualStateManager](https://www.noesisengine.com/docs/Gui.Animation._VisualStateManager.html) • [VisualTransition](https://www.noesisengine.com/docs/Gui.Animation._VisualTransition.html) • ...

# Properties

## From [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html)

| Property | Description |
|----------|-------------|
| ThreadId | Gets the thread this DispatcherObject is associated with. Returns NoThreadId when this object is not attached to any thread. |

# Attached Properties

DependencyObject has no attached properties

# Methods

## From [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html)

| Method | Description |
|--------|-------------|
| CheckAccess() | Determines whether the calling thread has access to this DispatcherObject |
| VerifyAccess() | Enforces that the calling thread has access to this DispatcherObject |

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

# Events

DependencyObject has no events