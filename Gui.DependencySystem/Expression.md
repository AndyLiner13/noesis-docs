# Expression Class

## namespace Noesis | MSDN

Base implementation for all expressions.

# Inheritance Hierarchy

 • Expression • BaseBindingExpression • TemplateBindingExpression

# Properties

Expression has no properties

# Attached Properties

Expression has no attached properties

# Methods

| Method | Description |
|--------|-------------|
| AfterSet(obj, dp, value, valueHasChanged) | Executed after set is completed and the property changed has been notified |
| BeforeSet(obj, dp, value, valueHasChanged) | Executes the set |
| Evaluate() | Evaluates expression when applied to the specified target object |
| Reapply(targetObject, targetProperty) | Applies expression to a new target, cloning the expression itself if necessary |

# Events

Expression has no events