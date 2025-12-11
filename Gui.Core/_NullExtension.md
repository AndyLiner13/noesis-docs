Source: https://www.noesisengine.com/docs/Gui.Core._NullExtension.html

# NullExtension Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.markup.nullextension.aspx)

Implements a XAML markup extension in order to return a null object.

In XAML, null and empty string are generally not equivalent. You use the {x:Null} extension usage in order to set an attribute that sets the underlying property to null.

```
<Button Background="{x:Null}"/>
```

# Inheritance Hierarchy

• [MarkupExtension](_MarkupExtension.md)

• *NullExtension*

# Properties

NullExtension has no properties

# Attached Properties

NullExtension has no attached properties

# Methods

## From [MarkupExtension](_MarkupExtension.md)

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that is provided as the value of the target property for this extension |

# Events

NullExtension has no events