# Binding Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.data.binding.aspx)

Provides high-level access to the definition of a binding, which connects the properties of binding target objects and any data source.

Example:

 <TextBlock Text="{Binding Source={StaticResource myDataSource}, Path=PersonName}"/>

## Inheritance Hierarchy

- [MarkupExtension](https://www.noesisengine.com/docs/Gui.Core._MarkupExtension.html)
- [BaseBinding](https://www.noesisengine.com/docs/Gui.Core._BaseBinding.html)
- Binding

## Properties

### From BaseBinding

| Property | Description |
|----------|-------------|
| Delay | Gets or sets the amount of time, in milliseconds, to wait before updating the binding source after the value on the target changes |
| FallbackValue | Gets or sets the value to use when the binding is unable to return a value |
| StringFormat | Gets or sets a string that specifies how to format the binding if it displays the bound value as a string. Examples: <TextBlock Text="{Binding Amount, StringFormat=F2}" /> <TextBlock Text="{Binding Amount, StringFormat={}{0:F2}}" /> <TextBlock Text="{Binding Amount, StringFormat=Value is {0:F2} units}" />  |
| TargetNullValue | Gets or sets the value to use when final target value is null |

### Own Properties

| Property | Description |
|----------|-------------|
| Converter | Gets or sets the converter to use. If you set the Converter and StringFormat properties, the converter is applied to the data value first, and then the StringFormat is applied |
| ConverterParameter | Gets or sets the parameter to pass to the Converter |
| DoNothing | A source property or a converter can return Binding.DoNothing to instruct the binding engine to do nothing when binding gets evaluated |
| ElementName | Gets or sets the name of the element to use as the binding source object. Only one of the three properties, ElementName, Source, or RelativeSource, should be set for each binding, or a conflict can occur. Setting this property shows an error if there is a binding source conflict |
| Mode | Gets or sets the binding mode. It can be set to one of the following values of the BindingMode enumeration: • OneWay: The target is updated whenever the source changes. • TwoWay: A change to either the target or source updates the other. • OneWayToSource: The opposite of OneWay. The source is updated whenever the targetchanges. • OneTime: This works just like OneWay, except changes to the source are notreflected at the target. The target retains a snapshot of the source at the time the Binding is initiated. |
| Path | Gets or sets the path to the binding source property |
| RelativeSource | Gets or sets the binding source by specifying its location relative to the position of the binding target. Only one of the three properties, ElementName, Source, or RelativeSource, should be set for each binding, or a conflict can occur. Setting this property shows an error if there is a binding source conflict |
| Source | Gets or sets the object to use as the binding source. Only one of the three properties, ElementName, Source, or RelativeSource, should be set for each binding, or a conflict can occur. Setting this property shows an error if there is a binding source conflict |
| UpdateSourceTrigger | Gets or sets a value that determines the timing of binding source updates: • Default: The default UpdateSourceTrigger value of the binding target property. Thedefault value for most dependency properties is PropertyChanged, while the Text property has a default value of LostFocus. • PropertyChanged: The source is updated whenever the target property value changes. • LostFocus: When the target property value changes, the source is only updated afterthe target element loses focus. • Explicit: The source is only updated when you make an explicit call to*BindingExpression.UpdateSource*. |

## Attached Properties

Binding has no attached properties

## Methods

### From MarkupExtension

| Method | Description |
|--------|-------------|
| ProvideValue(provider) | Returns an object that is provided as the value of the target property for this extension |

### Own Methods

| Method | Description |
|--------|-------------|
| GetSourceObject(target, targetProperty) | Find data from the appropriate source: Source, ElementName, RelativeSource or DataContext |
| ProvideValue(provider) | Can return 0 when the source object is not resolvable (doesn't throw exception) |

## Events

Binding has no events