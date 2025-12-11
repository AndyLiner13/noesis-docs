Source: https://www.noesisengine.com/docs/Gui.Core._BaseValueConverter.html

# BaseValueConverter Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace)

Base class for value converters used in Bindings.

# Inheritance Hierarchy

• *BaseValueConverter*

• [AlternationConverter](_AlternationConverter.md)

• [BooleanToVisibilityConverter](_BooleanToVisibilityConverter.md)

# Properties

BaseValueConverter has no properties

# Attached Properties

BaseValueConverter has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *TryConvert(value, targetType, parameter, result)* | The data binding engine calls this method when it propagates a value from the binding source to the binding target.  Return *DependencyProperty.UnsetValue* to indicate that the converter produced no value and that the fallback (if available) or default value should be used instead.  Return *Binding.DoNothing* to indicate that the binding should not transfer the value or use the fallback or default value. |
|  *TryConvertBack(value, targetType, parameter, result)* | The data binding engine calls this method when it propagates a value from the binding target to the binding source.  Return *Binding.DoNothing* to indicate that no value should be set on the source property.  Return *DependencyProperty.UnsetValue* to indicate that the converter is unable to provide a value for the source property, and no value will be set to it. |

# Events

BaseValueConverter has no events