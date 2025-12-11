Source: https://www.noesisengine.com/docs/Gui.Core._MultiBinding.html

# MultiBinding Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](https://docs.microsoft.com/en-us/dotnet/api/system.windows.data.multibinding)

Describes a collection of [Binding](_Binding.md) objects attached to a single binding target property.

Example:

```
<Border>
  <Border.Width>
    <MultiBinding Converter="{StaticResource AddConverter}">
      <Binding ElementName="source1" Path="Width"/>
      <Binding ElementName="source2" Path="Width"/>
    </MultiBinding>
  </Border.Width>
</Border>
<TextBlock>
  <TextBlock.Text>
    <MultiBinding StringFormat="{}{0} x {1}">
      <Binding Path="Width" />
      <Binding Path="Height" />
    </MultiBinding>
  </TextBlock.Text>
</TextBlock>
```

# Inheritance Hierarchy

• [MarkupExtension](_MarkupExtension.md)

• [BaseBinding](_BaseBinding.md)

• *MultiBinding*

# Properties

| Name | Description |
| --- | --- |
| ○ *Bindings* | Gets the collection of [Binding](_Binding.md) objects within this [MultiBinding](_MultiBinding.md) instance |
| ○ *Converter* | Gets or sets the converter to use to convert the source values to or from the target value |
| ○ *ConverterParameter* | Gets or sets the parameter to pass to the Converter |
| ○ *Mode* | Gets or sets the binding mode. It can be set to one of the following values of the *BindingMode* enumeration:   - *OneWay*: The target is updated whenever the source changes. - *TwoWay*: A change to either the target or source updates the other. - *OneWayToSource*: The opposite of *OneWay*. The source is updated whenever the targetchanges. - *OneTime*: This works just like *OneWay*, except changes to the source are notreflected at the target. The target retains a snapshot of the source at the time the *Binding* is initiated. |
| ○ *UpdateSourceTrigger* | Gets or sets a value that determines the timing of binding source updates:   - *Default*: The default UpdateSourceTrigger value of the binding target property. Thedefault value for most dependency properties is *PropertyChanged*, while the *Text* property has a default value of *LostFocus*. - *PropertyChanged*: The source is updated whenever the target property value changes. - *LostFocus*: When the target property value changes, the source is only updated afterthe target element loses focus. - *Explicit*: The source is only updated when you make an explicit call to\*BindingExpression.UpdateSource\*. |

● Dependency Property   ○ Reflection Property

## From [BaseBinding](_BaseBinding.md)

| Name | Description |
| --- | --- |
| ○ *Delay* | Gets or sets the amount of time, in milliseconds, to wait before updating the binding source after the value on the target changes |
| ○ *FallbackValue* | Gets or sets the value to use when the binding is unable to return a value |
| ○ *StringFormat* | Gets or sets a string that specifies how to format the binding if it displays the bound value as a string.  Examples:  ``` <TextBlock Text="{Binding Amount, StringFormat=F2}" /> <TextBlock Text="{Binding Amount, StringFormat={}{0:F2}}" /> <TextBlock Text="{Binding Amount, StringFormat=Value is {0:F2} units}" /> ``` |
| ○ *TargetNullValue* | Gets or sets the value to use when final target value is null |

● Dependency Property   ○ Reflection Property

# Attached Properties

MultiBinding has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Can return 0 when the source object is not resolvable (doesn't throw exception) |

## From [MarkupExtension](_MarkupExtension.md)

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that is provided as the value of the target property for this extension |

# Events

MultiBinding has no events