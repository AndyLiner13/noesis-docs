# BaseBinding Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.data.bindingbase.aspx)

Defines the common features for [Binding](https://www.noesisengine.com/docs/Gui.Core._Binding.html).

## Inheritance Hierarchy

- [MarkupExtension](https://www.noesisengine.com/docs/Gui.Core._MarkupExtension.html)
- BaseBinding
- [Binding](https://www.noesisengine.com/docs/Gui.Core._Binding.html)
- [MultiBinding](https://www.noesisengine.com/docs/Gui.Core._MultiBinding.html)

## Properties

| Property | Description |
|----------|-------------|
| Delay | Gets or sets the amount of time, in milliseconds, to wait before updating the binding source after the value on the target changes |
| FallbackValue | Gets or sets the value to use when the binding is unable to return a value |
| StringFormat | Gets or sets a string that specifies how to format the binding if it displays the bound value as a string. Examples: <TextBlock Text="{Binding Amount, StringFormat=F2}" /> <TextBlock Text="{Binding Amount, StringFormat={}{0:F2}}" /> <TextBlock Text="{Binding Amount, StringFormat=Value is {0:F2} units}" /> |
| TargetNullValue | Gets or sets the value to use when final target value is null |

## Attached Properties

BaseBinding has no attached properties

## Methods

### From MarkupExtension

| Method | Description |
|--------|-------------|
| ProvideValue(provider) | Returns an object that is provided as the value of the target property for this extension |

## Events

BaseBinding has no events