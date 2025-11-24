Source: https://www.noesisengine.com/docs/Gui.Core._BaseBindingExpression.html

# BaseBindingExpression Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](https://msdn.microsoft.com/en-us/library/system.windows.data.bindingexpressionbase.aspx)

Represents the base class for all [Binding](/Gui.Core/_Binding.md) Expressions.

# Inheritance Hierarchy

• [Expression](/Gui.DependencySystem/_Expression.md)

• *BaseBindingExpression*

• [BindingExpression](/Gui.Core/_BindingExpression.md)

• [MultiBindingExpression](/Gui.Core/_MultiBindingExpression.md)

# Properties

| Name | Description |
| --- | --- |
| ○ *ParentBindingBase* | Gets the [BaseBinding](/Gui.Core/_BaseBinding.md) object from which this [BaseBindingExpression](/Gui.Core/_BaseBindingExpression.md) object is created |
| ○ *Target* | Gets the element to which this [BindingExpression](/Gui.Core/_BindingExpression.md) is attached |
| ○ *TargetProperty* | Gets the property to which this [BindingExpression](/Gui.Core/_BindingExpression.md) is attached |

● Dependency Property   ○ Reflection Property

# Attached Properties

BaseBindingExpression has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *UpdateSource()* | Sends the current value back to the source. Does nothing when binding's Mode is not TwoWay or OneWayToSource |
|  *UpdateTarget()* | Forces a data transfer from source to target |

## From [Expression](/Gui.DependencySystem/_Expression.md)

| Name | Description |
| --- | --- |
|  *AfterSet(obj, dp, value, valueHasChanged)* | Executed after set is completed and the property changed has been notified |
|  *BeforeSet(obj, dp, value, valueHasChanged)* | Executes the set |
|  *Evaluate()* | Evaluates expression when applied to the specified target object |
|  *Reapply(targetObject, targetProperty)* | Applies expression to a new target, cloning the expression itself if necessary |

# Events

BaseBindingExpression has no events