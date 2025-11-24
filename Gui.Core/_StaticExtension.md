Source: https://www.noesisengine.com/docs/Gui.Core._StaticExtension.html

# StaticExtension Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.markup.staticextension.aspx)

Implements a markup extension that returns static field and property references.

You typically use static references to obtain static values from types, including from types that cannot be instantiated in XAML because the type is static. Common examples of cases where {x:Static} is useful include values that can be thought of as constants, such as fixed math values or unique keys for states

```
<Style x:Key="{x:Static MenuItem.SeparatorStyleKey}">
  <Setter Property="Foreground" Value="{x:Static SystemColors.ControlTextBrushKey}"/>
</Style>
```

# Inheritance Hierarchy

• [MarkupExtension](/Gui.Core/_MarkupExtension.md)

• *StaticExtension*

# Properties

| Name | Description |
| --- | --- |
| ○ *Member* | Gets or sets a member name string that is used to resolve a static field or property based on the service-provided type resolver |

● Dependency Property   ○ Reflection Property

# Attached Properties

StaticExtension has no attached properties

# Methods

## From [MarkupExtension](/Gui.Core/_MarkupExtension.md)

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that is provided as the value of the target property for this extension |

# Events

StaticExtension has no events