Source: https://www.noesisengine.com/docs/Gui.Core._StaticResourceExtension.html

# StaticResourceExtension Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.staticresourceextension.aspx)

Implements a markup extension that supports static resource references made from XAML.

Provides a value for any XAML property attribute by looking up a reference to an already defined resource. Lookup behavior for that resource is analogous to load-time lookup, which will look for resources that were previously loaded from the markup of the current XAML page as well as other application sources, and will generate that resource value as the property value in the run-time objects.

```
<Setter Property="FocusVisualStyle" Value="{StaticResource CheckRadioFocusVisual}"/>
```

# Inheritance Hierarchy

• [MarkupExtension](_MarkupExtension.md)

• *StaticResourceExtension*

# Properties

| Name | Description |
| --- | --- |
| ○ *ResourceKey* | Gets or sets the key value passed by this static resource reference. They key is used to return the object matching that key in resource dictionaries |

● Dependency Property   ○ Reflection Property

# Attached Properties

StaticResourceExtension has no attached properties

# Methods

## From [MarkupExtension](_MarkupExtension.md)

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that is provided as the value of the target property for this extension |

# Events

StaticResourceExtension has no events