# AlternationConverter Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.alternationconverter)

Converts an integer to/from an object by applying the integer as an index to a list of objects.

```xaml
<Grid
 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

    <Grid.Resources>
        <AlternationConverter x:Key="backgroundConverter">
            <SolidColorBrush>Silver</SolidColorBrush>
            <SolidColorBrush>Gray</SolidColorBrush>
        </AlternationConverter>
        <Style x:Key="listItemStyle" TargetType="{x:Type ListBoxItem}">
            <Setter Property="Background"
                Value="{Binding Path=(ItemsControl.AlternationIndex),
                    RelativeSource={RelativeSource Self},
                    Converter={StaticResource backgroundConverter}}"/>
        </Style>
    </Grid.Resources>
    ...
    <ListBox AlternationCount="2" ItemsSource="{Binding Items}"
        ItemContainerStyle="{StaticResource listItemStyle}"/>

</Grid>
```

## Inheritance Hierarchy

- [BaseValueConverter](https://www.noesisengine.com/docs/Gui.Core._BaseValueConverter.html)
- AlternationConverter

## Properties

| Property | Description |
|----------|-------------|
| Values | Gets a list of objects that the AlternationConverter returns when an integer is passed to the Convert() method |

## Attached Properties

AlternationConverter has no attached properties

## Methods

### From [BaseValueConverter](https://www.noesisengine.com/docs/Gui.Core._BaseValueConverter.html)

| Method | Description |
|--------|-------------|
| TryConvert(value, targetType, parameter, result) | The data binding engine calls this method when it propagates a value from the binding source to the binding target. Return DependencyProperty.UnsetValue to indicate that the converter produced no value and that the fallback (if available) or default value should be used instead. Return Binding.DoNothing to indicate that the binding should not transfer the value or use the fallback or default value. |
| TryConvertBack(value, targetType, parameter, result) | The data binding engine calls this method when it propagates a value from the binding target to the binding source. Return Binding.DoNothing to indicate that no value should be set on the source property. Return DependencyProperty.UnsetValue to indicate that the converter is unable to provide a value for the source property, and no value will be set to it. |

## Events

AlternationConverter has no events