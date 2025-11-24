Source: https://www.noesisengine.com/docs/Gui.Core.MarkupExtensions.html

# Markup Extensions

Markup extensions are clases that provides values for object properties. When used in XAML, they are usually written in a compact form between curly braces "{}", but this sintax is semantically identical to the more usual Xaml mode of writing objects using nodes. Extensions expressed with {} can be nested.

Markup extensions implement the IMarkupExtension interface, which defines the ProvideValue unique method to return a value to the property that has the markup assigned.

# MarkupExtension

<http://msdn.microsoft.com/en-us/library/system.windows.markup.markupextension.aspx>

| Methods | | --- | --- | --- |
| Name | Sup | Comments |
| ProvideValue | Yes | Defined as IMarkupExtension::ProvideValue |

# NullExtension

<http://msdn.microsoft.com/en-us/library/system.windows.markup.nullextension.aspx>

The NullExtension is used to set a null value to properties that are components of nullables. The NullExtension has no possible attributes.

```
<ToggleButton IsChecked="{x:Null}"/>
```

# StaticExtension

<http://msdn.microsoft.com/en-us/library/system.windows.markup.staticextension.aspx>

It is not fully supported in Noesis.

Current implementation supports only 3 scenarios:

- **Enum type values**

  ```
  <Border Visibility="{x:Static Visibility.Collapsed}"/>
  ```
- **Routed commands**

  ```
  <RepeatButton Command="{x:Static Slider.DecreaseLarge}"/>
  ```
- **DependencyProperty default values:** This is a trick that can be used to simulate static members. You can define a dependency property in a class, and use its default value to expose a static member in xaml.

  ```
  <Border Width="{x:Static local:SizeHelper.BorderWidth}"/>
  ```

  C#

  ```
  public class SizeHelper : DependencyObject
  {
    public static float BorderWidth { get { return 16.0f } };

  #if NOESIS
    public static readonly DependencyProperty BorderWidthProperty = DependencyProperty.Register(
      "BorderWidth", typeof(float), typeof(SizeHelper),
      new PropertyMetadata(SizeHelper.BorderWidth));
  #endif
  }
  ```

| Properties | | --- | --- | --- |
| Name | Sup | Comments |
| Member | Yes | MemberType | No # TypeExtension

<http://msdn.microsoft.com/en-us/library/system.windows.markup.typeextension.aspx>

Returns the type of an object, encapsulated into a ResourceKeyType.

```
<Style TargetType="{x:Type RepeatButton}"/>
```

| Properties | | --- | --- | --- |
| Name | Sup | Comments |
| Type | Yes | TypeName | Yes | Returns a Symbol |

# ArrayExtension

It is not currently supported in Noesis.

# StaticResource

<http://msdn.microsoft.com/en-us/library/system.windows.staticresourceextension.aspx>

Allows searching for an resource in a ResourceDictionary at Xaml load time. The resource is searched in the resource dictionaries of the current parsing tree, looking upwards until the root is reached.

If the resource is not found, an exception is thrown; if the resource is found, the value is returned and the extension is deleted, so if later the resource entry is modified in the ResourceDictionary, the change is not seen by the extension's target object.

Generally, resources can are stored and accessed by name, but Style objects in resources can be accessed by type

```
<Page>
<Page.Resources>
  <SolidColorBrush x:Key="MyBrush" Color="Gold"/>
  <Style x:Key="{x:Type Button}">
</Style>

</Page.Resources>
  <StackPanel>
    <Ellipse Width="100" Height="100" Fill="{StaticResource MyBrush}"/>
    <Button Style="{StaticResource {x:Type Button}}"/>
  </StackPanel>
</Page>
```

| Properties | | --- | --- | --- |
| Name | Sup | Comments |
| ResourceKey | Yes # DynamicResource

<http://msdn.microsoft.com/en-us/library/system.windows.dynamicresourceextension.aspx>

The DynamicResource is similar to the StaticResource, but it maintains an active look to the resource, so it the resource entry changes in the resourceDirectionary (the resource is deleted or changed, or one of the ancestors of the target object changes, for example) the DynamicResource detects the change and reassigns the new value to the target property.

Internally, the DynamicResourceExtension creates a DynamicResourceExpression, which is in charge of detecting the changes and updating the target values, just like a BindingExpression.

```
<Setter Property="BorderBrush" Value="{DynamicResource DefaultedBorderBrush}"/>
```

| Properties | | --- | --- | --- |
| Name | Sup | Comments |
| ResourceKey | Yes # Binding and TemplateBinding

The other usual markup extension is Binding and TemplateBinding, which are explained [here](/Gui.Core/Binding.md)