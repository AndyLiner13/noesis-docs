Source: https://www.noesisengine.com/docs/Gui.Core._MarkupExtension.html

# MarkupExtension Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.markup.markupextension.aspx)

Provides a base class for XAML markup extension implementations.

Markup extensions return objects in a more sophisticated way than type converters alone can accomplish. Markup extensions use the known character sequence of an opening curly brace { to enter the markup extension scope, and a closing curly brace } to exit.

```
<Path Fill="{StaticResource GlyphBrush}"
      Data="{Binding Path=Content, RelativeSource={RelativeSource TemplatedParent}}"/>
```

# Inheritance Hierarchy

• *MarkupExtension*

• [BaseBinding](_BaseBinding.md)

• [DynamicResourceExtension](_DynamicResourceExtension.md)

• [LocExtension](../App.ApplicationLauncher/_LocExtension.md)

• [NullExtension](_NullExtension.md)

• [RelativeSource](_RelativeSource.md)

• [StaticExtension](_StaticExtension.md)

• [StaticResourceExtension](_StaticResourceExtension.md)

• [TemplateBindingExtension](_TemplateBindingExtension.md)

• [TypeExtension](_TypeExtension.md)

# Properties

MarkupExtension has no properties

# Attached Properties

MarkupExtension has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that is provided as the value of the target property for this extension |

# Events

MarkupExtension has no events