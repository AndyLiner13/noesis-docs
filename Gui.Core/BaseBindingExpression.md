# BaseBindingExpression Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](https://msdn.microsoft.com/en-us/library/system.windows.data.bindingexpressionbase.aspx)

Represents the base class for all [Binding](https://www.noesisengine.com/docs/Gui.Core._Binding.html) Expressions.

## Inheritance Hierarchy

- [Expression](https://www.noesisengine.com/docs/Gui.DependencySystem._Expression.html)
- BaseBindingExpression
- [BindingExpression](https://www.noesisengine.com/docs/Gui.Core._BindingExpression.html)
- [MultiBindingExpression](https://www.noesisengine.com/docs/Gui.Core._MultiBindingExpression.html)

## Properties

| Property | Description |
|----------|-------------|
| ParentBindingBase | Gets the BaseBinding object from which this BaseBindingExpression object is created |
| Target | Gets the element to which this BindingExpression is attached |
| TargetProperty | Gets the property to which this BindingExpression is attached |

## Attached Properties

BaseBindingExpression has no attached properties

## Methods

| Method | Description |
|--------|-------------|
| UpdateSource() | Sends the current value back to the source. Does nothing when binding's Mode is not TwoWay or OneWayToSource |
| UpdateTarget() | Forces a data transfer from source to target |

### From Expression

| Method | Description |
|--------|-------------|
| AfterSet(obj, dp, value, valueHasChanged) | Executed after set is completed and the property changed has been notified |
| BeforeSet(obj, dp, value, valueHasChanged) | Executes the set |
| Evaluate() | Evaluates expression when applied to the specified target object |
| Reapply(targetObject, targetProperty) | Applies expression to a new target, cloning the expression itself if necessary |

## Events

BaseBindingExpression has no events