Source: https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html

# DependencyObject Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.dependencyobject.aspx)

Represents an object that participates in the dependency property system.

The [DependencyObject](/Gui.DependencySystem/_DependencyObject.md) class enables the property system services on its many derived classes. The property system's primary function is to compute the values of properties, and to provide system notification about values that have changed. Another key class that participates in the property system is [DependencyProperty](/Gui.DependencySystem/_DependencyProperty.md). [DependencyProperty](/Gui.DependencySystem/_DependencyProperty.md) enables the registration of dependency properties into the property system, and provides identification and information about each dependency property, whereas [DependencyObject](/Gui.DependencySystem/_DependencyObject.md) as a base class enables objects to use the dependency properties.

# Inheritance Hierarchy

• [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

• *DependencyObject*

• [BaseTrigger](/Gui.Core/_BaseTrigger.md)

• [CollectionViewSource](/Gui.Core/_CollectionViewSource.md)

• [Freezable](/Gui.DependencySystem/_Freezable.md)

• [TriggerAction](/Gui.Core/_TriggerAction.md)

• [Visual](/Gui.Core/_Visual.md)

• [VisualState](/Gui.Animation/_VisualState.md)

• [VisualStateGroup](/Gui.Animation/_VisualStateGroup.md)

• [VisualStateManager](/Gui.Animation/_VisualStateManager.md)

• [VisualTransition](/Gui.Animation/_VisualTransition.md)

# Properties

## From [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

| Name | Description |
| --- | --- |
| ○ *ThreadId* | Gets the thread this [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) is associated with. Returns NoThreadId when this object is not attached to any thread. |

● Dependency Property   ○ Reflection Property

# Attached Properties

DependencyObject has no attached properties

# Methods

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

DependencyObject has no events