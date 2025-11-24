Source: https://www.noesisengine.com/docs/Gui.Core._BaseBinding.html

# BaseBinding Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.data.bindingbase.aspx)

Defines the common features for [Binding](/Gui.Core/_Binding.md).

# Inheritance Hierarchy

• [MarkupExtension](/Gui.Core/_MarkupExtension.md)

• *BaseBinding*

• [Binding](/Gui.Core/_Binding.md)

• [MultiBinding](/Gui.Core/_MultiBinding.md)

# Properties

| Name | Description |
| --- | --- |
| ○ *Delay* | Gets or sets the amount of time, in milliseconds, to wait before updating the binding source after the value on the target changes |
| ○ *FallbackValue* | Gets or sets the value to use when the binding is unable to return a value |
| ○ *StringFormat* | Gets or sets a string that specifies how to format the binding if it displays the bound value as a string.  Examples:  ``` <TextBlock Text="{Binding Amount, StringFormat=F2}" /> <TextBlock Text="{Binding Amount, StringFormat={}{0:F2}}" /> <TextBlock Text="{Binding Amount, StringFormat=Value is {0:F2} units}" /> ``` |
| ○ *TargetNullValue* | Gets or sets the value to use when final target value is null |

● Dependency Property   ○ Reflection Property

# Attached Properties

BaseBinding has no attached properties

# Methods

## From [MarkupExtension](/Gui.Core/_MarkupExtension.md)

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that is provided as the value of the target property for this extension |

# Events

BaseBinding has no events