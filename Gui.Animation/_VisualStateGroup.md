Source: https://www.noesisengine.com/docs/Gui.Animation._VisualStateGroup.html

# VisualStateGroup Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.visualstategroup.aspx)

Contains mutually exclusive [VisualState](/Gui.Animation/_VisualState.md) objects and [VisualTransition](/Gui.Animation/_VisualTransition.md) objects that are used to go from one state to another.

# Inheritance Hierarchy

• [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](/Gui.DependencySystem/_DependencyObject.md)

• *VisualStateGroup*

# Properties

| Name | Description |
| --- | --- |
| ○ *Name* | Gets the name of the [VisualStateGroup](/Gui.Animation/_VisualStateGroup.md). |
| ○ *States* | Gets the collection of mutually exclusive [VisualState](/Gui.Animation/_VisualState.md) objects |
| ○ *Transitions* | Gets the collection of [VisualTransition](/Gui.Animation/_VisualTransition.md) objects |

● Dependency Property   ○ Reflection Property

## From [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

| Name | Description |
| --- | --- |
| ○ *ThreadId* | Gets the thread this [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) is associated with. Returns NoThreadId when this object is not attached to any thread. |

● Dependency Property   ○ Reflection Property

# Attached Properties

VisualStateGroup has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *CreateTransitionStoryboard(root, newState, transition)* | Creates a [Storyboard](/Gui.Animation/_Storyboard.md) that animates changes from current state to the specifed new state |
|  *FindState(name)* | Finds a matching state with the same name (can be null or empty) |
|  *FindTransition(from, to)* | Finds a matching transition for the provided *from* and "to\* [VisualState](/Gui.Animation/_VisualState.md) objects |
|  *GetCurrentState(fe)* | Gets or the state that is currently active |
|  *UpdateAnimations(fe, storyboard1, storyboard2)* | Updates element animations with the specified storyboards |

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
| ◆ *CurrentStateChanged* | Occurs after a control transitions to a different state |
| ◆ *CurrentStateChanging* | Occurs when a control starts transitioning to a different state |

▸ Routed Event    Non-routed Event   ◆ Delegate Event