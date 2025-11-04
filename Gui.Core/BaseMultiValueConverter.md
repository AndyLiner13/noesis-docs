# BaseMultiValueConverter Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace)

Base class for value converters used in MultiBindings.

## Inheritance Hierarchy

- BaseMultiValueConverter

## Properties

BaseMultiValueConverter has no properties

## Attached Properties

BaseMultiValueConverter has no attached properties

## Methods

| Method | Description |
|--------|-------------|
| TryConvert(values, targetType, parameter, result) | Converts source values to a value for the binding target. The data binding engine calls this method when it propagates the values from source bindings to the binding target. Return DependencyProperty.UnsetValue to indicate that the converter produced no value and that the fallback (if available) or default value should be used instead. Return Binding.DoNothing to indicate that the binding should not transfer the value to the target property or use the fallback or default value. |
| TryConvertBack(value, targetTypes, parameter, results) | Converts a binding target value to the source binding values. The data binding engine calls this method when it propagates a value from the binding to the sources. If there are more return values than source bindings, the excess portion of return values will be ignored. If there are more source bindings than return values, the remaining source bindings will not have any value set to them. Types of return values are not verified against targetTypes; the values will be set to source bindings directly. Returning Binding.DoNothing in position i indicates that no value should be set on the source binding at index i. Returning DependencyProperty.UnsetValue in position i indicates that the converter is unable to provide a value to the source binding at index i, and no value will be set to it. Returning null indicates that the conversion could not be performed at all, or that the backward conversion direction is not supported by the converter. |

## Events

BaseMultiValueConverter has no events