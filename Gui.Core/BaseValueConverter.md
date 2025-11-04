# BaseValueConverter Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace)

Base class for value converters used in Bindings.

## Inheritance Hierarchy

- BaseValueConverter
- [AlternationConverter](https://www.noesisengine.com/docs/Gui.Core._AlternationConverter.html)
- [BooleanToVisibilityConverter](https://www.noesisengine.com/docs/Gui.Core._BooleanToVisibilityConverter.html)

## Properties

BaseValueConverter has no properties

## Attached Properties

BaseValueConverter has no attached properties

## Methods

### Own Methods

| Method | Description |
|--------|-------------|
| TryConvert(value, targetType, parameter, result) | The data binding engine calls this method when it propagates a value from the binding source to the binding target. Return DependencyProperty.UnsetValue to indicate that the converter produced no value and that the fallback (if available) or default value should be used instead. Return Binding.DoNothing to indicate that the binding should not transfer the value or use the fallback or default value. |
| TryConvertBack(value, targetType, parameter, result) | The data binding engine calls this method when it propagates a value from the binding target to the binding source. Return Binding.DoNothing to indicate that no value should be set on the source property. Return DependencyProperty.UnsetValue to indicate that the converter is unable to provide a value for the source property, and no value will be set to it. |

## Events

BaseValueConverter has no events