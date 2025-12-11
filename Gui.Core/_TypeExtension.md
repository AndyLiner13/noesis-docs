Source: https://www.noesisengine.com/docs/Gui.Core._TypeExtension.html

# TypeExtension Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.markup.typeextension.aspx)

Implements a markup extension that returns a *Type* based on a string input.

Type references are commonly used for style, template, and databinding feature areas in Noesis, when these features are referenced by XAML.

```
<Style TargetType="{x:Type RepeatButton}"/>
```

# Inheritance Hierarchy

• [MarkupExtension](_MarkupExtension.md)

• *TypeExtension*

# Properties

| Name | Description |
| --- | --- |
| ○ *Type* | Gets or sets the type information for this extension |
| ○ *TypeName* | Gets or sets the type name represented by this markup extension |

● Dependency Property   ○ Reflection Property

# Attached Properties

TypeExtension has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *GetEffectiveType(typeName)* | Gets the effective Noesis type from XAML system types |

## From [MarkupExtension](_MarkupExtension.md)

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that is provided as the value of the target property for this extension |

# Events

TypeExtension has no events