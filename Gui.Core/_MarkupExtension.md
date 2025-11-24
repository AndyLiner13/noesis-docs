Source: https://www.noesisengine.com/docs/Gui.Core._MarkupExtension.html

# MarkupExtension Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.markup.markupextension.aspx)

Provides a base class for XAML markup extension implementations.

Markup extensions return objects in a more sophisticated way than type converters alone can accomplish. Markup extensions use the known character sequence of an opening curly brace { to enter the markup extension scope, and a closing curly brace } to exit.

```
<Path Fill="{StaticResource GlyphBrush}"
      Data="{Binding Path=Content, RelativeSource={RelativeSource TemplatedParent}}"/>
```

# Inheritance Hierarchy

• *MarkupExtension*

• [BaseBinding](/Gui.Core/_BaseBinding.md)

• [DynamicResourceExtension](/Gui.Core/_DynamicResourceExtension.md)

• [LocExtension](/App.ApplicationLauncher/_LocExtension.md)

• [NullExtension](/Gui.Core/_NullExtension.md)

• [RelativeSource](/Gui.Core/_RelativeSource.md)

• [StaticExtension](/Gui.Core/_StaticExtension.md)

• [StaticResourceExtension](/Gui.Core/_StaticResourceExtension.md)

• [TemplateBindingExtension](/Gui.Core/_TemplateBindingExtension.md)

• [TypeExtension](/Gui.Core/_TypeExtension.md)

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