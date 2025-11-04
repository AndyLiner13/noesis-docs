# Binding

[http://msdn.microsoft.com/en-us/library/system.windows.data.binding.aspx](http://msdn.microsoft.com/en-us/library/system.windows.data.binding.aspx)

Binding allows the connection of an object's property to any data source (property from other object, database, XML file, etc...).
Current implementation only supports the connection between object properties.

| Name | Sup | Comments |
|------|-----|----------|
| ShouldSerializePath | No |  |
| ShouldSerializeSource | No |  |
| ShouldSerializeValidationRules | No |  |

| Name | Att | Sup | Comments |
|------|-----|-----|----------|
| XamlNamespaceManagerPropert | Yes | No |  |

| Name | Sup | Comments |
|------|-----|----------|
| AsyncState | No |  |
| BindsDirectlyToSource | No |  |
| Converter | Yes |  |
| ConverterCulture | No |  |
| ConverterParameter | Yes |  |
| ElementName | Yes |  |
| IsAsync | No |  |
| Mode | Yes |  |
| NotifyOnSourceUpdated | No |  |
| NotifyOnTargetUpdated | No |  |
| NotifyOnValidationError | No |  |
| Path | Yes |  |
| RelativeSource | Yes |  |
| Source | Yes |  |
| UpdateSourceExceptionFilter | No |  |
| UpdateSourceTrigger | No |  |
| ValidatesOnDataErrors | No |  |
| ValidatesOnExceptions | No |  |
| ValidationRules | No |  |
| XPath | No |  |

| Name | Att | Sup | Comments |
|------|-----|-----|----------|
| SourceUpdatedEvent | Yes | No |  |
| TargetUpdatedEvent | Yes | No |  |

In a binding there are 3 main elements: a Target, a Source and a Path to the value in the Binding Source

- The **Target** is always a Dependency Property
- The **Source** can be a Dependency Property, or a "normal" property from an object that implements the INotifyChange interface
- The **Path** is created from a string that tells how to reach the binding value in the Source

The Binding object is stored in the Target as an expression, so a call to DependencyObject::ReadLocalValue over a local binding will return an object that can be casted to BindingExpression.

## Source

The source of a Binding can be expressed in several ways:

- **ElementName**: The source search traverses the tree upwards looking in the namescopes until the root is reached
- **Source**: Explicit set of the source, for example using a DynamicResource extension
- **RelativeSource**: Useful when the source is relative (an ancestor) to the target object. The relative source can be:
  - **Self**: Set the source equal to the target object
  - **AncestorType**: Gets an ancestor matching the specified type
  - **AncestorLevel**: To know how many ancestors (of type AncestorType if indicated) have to skipped to reach the desired source
  - **TemplatedParent**: To get the source from the target's templated parent.
- **DataContext**: Is explained later in this document

```xml
<Button Background="Red" Foreground="{Binding RelativeSource={RelativeSource Self}, Path=Background}"/>
<Button Background="{Binding RelativeSource={RelativeSource AncestorType={x:Type Border}, AncestorLevel=2}, Path=Background}"/>
<Button Background="{Binding RelativeSource={RelativeSource TemplatedParent}, Path=Background}"/>
```

## Return value

When a binding can't be resolved for any reason (invalid property path, source not found, converter not available, etc...) it returns the FallbackValue if set. If there is no FallbackValue, the binding returns a DependencyProperty::UnsetValue and when this value is evaluated in the DependencyObject, the default value of the target property is stored.

## Binding modes

Data flow in a binding can be modified with the Binding::Mode property. There are 4 flow modes:

- **OneWay**: Updates the binding target property when the binding source changes
- **TwoWay**: Updates either the source property or the target property when the other changes
- **OneWayToSource**: Updates the source property when the target property changes
- **OneTime**: Updates the binding target when the application starts or when the data context changes

## Update timing

For TwoWay or OneWayToSource bindings the moment when the target is updated can be controller with the UpdateSourceTrigger property. It has 3 possible values:

- **PropertyChanged**: It's the most common. The source is updated immediately after a target property change
- **LostFocus**: The update is done when the target object loses focus. It's the default behavior for TextBox::Text property
- **Explicit**: The update is done by code, calling BindingExpression::UpdateSource method
- **Default**: The value is read from the target property Metadata (FrameworkPropertyMetaData::DefaultUpdateSourceTrigger)

## Type Converters

Target and Source values can have different types. To allow the assignment of values of different types, an intermediate conversion is done by a converter (an object that implements IValueConverter interface).

The converter can be specified by the user (even when target and source types are the same).
If the types are different and the user doesn't specify a converter, the binding object instantiates a DefaultValueConverter which internally uses Core::TypeConverters from source and target types. Internally, the DefaultValueConverter first instantiates the target type converter, and if the conversion can't be done it makes a second try with the source type converter; if the second one also fails, then the binding can't resolve.

## String Format

When the target property is a String, the user can also specify a StringFormat property to indicate how to format the bound value (the StringFormat is only applied in the Source to Target data flow). If StringFormat is specified, the DefaultValueConverter is not utilized in the Source to Target data flow, but for user setted converters the converter is evaluated first and then the StringFormat is applied to the resulting value.

There are several formatting types for StringFormat:

- Numeric format
  - Standard format ([http://msdn.microsoft.com/en-us/library/dwhawy9k.aspx](http://msdn.microsoft.com/en-us/library/dwhawy9k.aspx))
    - Currency **C**: Implemented as number + 2 decimals + Euro symbol, but number is lacking thousands separator
    - Decimal **D**: Implemented
    - Scientific **E**: Implemented
    - Fixed Point **F**: Implemented
    - General **G**: Implemented
    - Number **N**: Implemented as Fixed Point
    - Percent **P**: Implemented
    - Round Trip **R**: Currently not implemented
    - Hexadecimal **H**: Implemented
  - Custom format ([http://msdn.microsoft.com/en-us/library/0c899ak8.aspx](http://msdn.microsoft.com/en-us/library/0c899ak8.aspx)). Currently not implemented
- Date and Time format: currently not implemented
- Enum format: currently not implemented

## DataContext

When several properties are binding to a common source the DataContext property of FrameworkElement and FrameworkContentElement can be set to allow the children in the same tree to resolve using the same source.

```xml
<DockPanel DataContext="{Binding Source={StaticResource Blog}}">
  <Label Content="{Binding Path=Name}"/>
  <Label Content="{Binding Path=Author}"/>
</DockPanel>
```

## TemplateBinding

[http://msdn.microsoft.com/en-us/library/system.windows.templatebindingextension.aspx](http://msdn.microsoft.com/en-us/library/system.windows.templatebindingextension.aspx)

TemplateBinding is an ligthweight Binding version equivalent to using RelativeSource=TemplatedParent

| Name | Sup | Comments |
|------|-----|----------|
| Converter | No |  |
| ConverterParameter | No |  |
| Property | Yes |  |

```xml
<Button Background="{Binding RelativeSource={RelativeSource TemplatedParent}, Path=Background}"/>
<Button Background="{TemplateBinding Background}"/>
```

## Table of Contents

- [Source](#source)
- [Return value](#return-value)
- [Binding modes](#binding-modes)
- [Update timing](#update-timing)
- [Type Converters](#type-converters)
- [String Format](#string-format)
- [DataContext](#datacontext)
- [TemplateBinding](#templatebinding)