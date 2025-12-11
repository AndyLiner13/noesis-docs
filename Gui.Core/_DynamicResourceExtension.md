Source: https://www.noesisengine.com/docs/Gui.Core._DynamicResourceExtension.html

# DynamicResourceExtension Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.dynamicresourceextension.aspx)

Implements a markup extension that supports dynamic resource references made from XAML.

Dynamic resource references are necessary when referencing content that might change at run-time. The reasons for the content change might be application-initiated or might be external. One example is if you are including styles that rely on system resources that report user-configured preferences, such as themes, font settings and so on.

```
<Setter Property="BorderBrush" Value="{DynamicResource DefaultedBorderBrush}"/>
```

# Inheritance Hierarchy

• [MarkupExtension](_MarkupExtension.md)

• *DynamicResourceExtension*

# Properties

| Name | Description |
| --- | --- |
| ○ *ResourceKey* | Gets or sets the key specified by this dynamic resource reference. The key is used to lookup a resource in resource dictionaries, by means of an intermediate expression |

● Dependency Property   ○ Reflection Property

# Attached Properties

DynamicResourceExtension has no attached properties

# Methods

## From [MarkupExtension](_MarkupExtension.md)

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that is provided as the value of the target property for this extension |

# Events

DynamicResourceExtension has no events