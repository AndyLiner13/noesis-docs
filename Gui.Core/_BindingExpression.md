Source: https://www.noesisengine.com/docs/Gui.Core._BindingExpression.html

# BindingExpression Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](https://msdn.microsoft.com/en-us/library/system.windows.data.bindingexpression.aspx)

Contains information about a single instance of a [Binding](/Gui.Core/_Binding.md).

# Inheritance Hierarchy

• [Expression](/Gui.DependencySystem/_Expression.md)

• [BaseBindingExpression](/Gui.Core/_BaseBindingExpression.md)

• *BindingExpression*

# Properties

| Name | Description |
| --- | --- |
| ○ *ParentBinding* | [Binding](/Gui.Core/_Binding.md) from which this expression was created |
| ○ *ResolvedSource* | Gets the binding source object for this [BindingExpression](/Gui.Core/_BindingExpression.md) |

● Dependency Property   ○ Reflection Property

## From [BaseBindingExpression](/Gui.Core/_BaseBindingExpression.md)

| Name | Description |
| --- | --- |
| ○ *ParentBindingBase* | Gets the [BaseBinding](/Gui.Core/_BaseBinding.md) object from which this [BaseBindingExpression](/Gui.Core/_BaseBindingExpression.md) object is created |
| ○ *Target* | Gets the element to which this [BindingExpression](/Gui.Core/_BindingExpression.md) is attached |
| ○ *TargetProperty* | Gets the property to which this [BindingExpression](/Gui.Core/_BindingExpression.md) is attached |

● Dependency Property   ○ Reflection Property

# Attached Properties

BindingExpression has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *AfterSet(obj, prop, value, valueChanged)* | Executed after set is completed and the property changed has been notified |
|  *BeforeSet(obj, prop, value, valueChanged)* | Executes the set |
|  *Evaluate()* | Evaluates expression when applied to the specified target object |
|  *Reapply(targetObject, targetProperty)* | Applies expression to a new target, cloning the expression itself if necessary |

## From [BaseBindingExpression](/Gui.Core/_BaseBindingExpression.md)

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

BindingExpression has no events