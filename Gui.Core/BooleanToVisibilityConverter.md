# BooleanToVisibilityConverter Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](https://msdn.microsoft.com/en-us/library/system.windows.controls.booleantovisibilityconverter)

Represents the converter that converts Boolean values to and from Visibility enumeration values.

The Convert method returns Visibility.Visible when true is passed in or Visibility.Collapsed when false is passed in. Note that the Visibility.Collapsed value hides the control and does not reserve space for it in a layout. When you call the ConvertBack method and specify a reference to an object, it returns true if the object is Visible; otherwise, it returns false.

```xaml
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Background="Gray">

    <Grid.Resources>
        <BooleanToVisibilityConverter x:Key="converter"/>
    </Grid.Resources>

    <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
        <CheckBox x:Name="checkBox" Content="Show Button" Width="100"/>
        <Button Content="Click" Margin="5" Visibility="{Binding ElementName=checkBox,
            Path=IsChecked, Converter={StaticResource converter}}"/>
    </StackPanel>

</Grid>
```

## Inheritance Hierarchy

 • [BaseValueConverter](https://www.noesisengine.com/docs/Gui.Core._BaseValueConverter.html) • BooleanToVisibilityConverter

## Properties

BooleanToVisibilityConverter has no properties

## Attached Properties

BooleanToVisibilityConverter has no attached properties

## Methods

### From [BaseValueConverter](https://www.noesisengine.com/docs/Gui.Core._BaseValueConverter.html)

| Method | Description |
|--------|-------------|
| TryConvert(value, targetType, parameter, result) | The data binding engine calls this method when it propagates a value from the binding source to the binding target. Return DependencyProperty.UnsetValue to indicate that the converter produced no value and that the fallback (if available) or default value should be used instead. Return Binding.DoNothing to indicate that the binding should not transfer the value or use the fallback or default value. |
| TryConvertBack(value, targetType, parameter, result) | The data binding engine calls this method when it propagates a value from the binding target to the binding source. Return Binding.DoNothing to indicate that no value should be set on the source property. Return DependencyProperty.UnsetValue to indicate that the converter is unable to provide a value for the source property, and no value will be set to it. |

## Events

BooleanToVisibilityConverter has no events