Source: https://www.noesisengine.com/docs/Gui.Core._TemplateBindingExtension.html

# TemplateBindingExtension Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.templatebindingextension.aspx)

Implements a markup extension that supports the binding between the value of a property in a template and the value of some other exposed property on the templated control.

Using a TemplateBinding is equivalent to using a [Binding](/Gui.Core/_Binding.md) with the Source property set to *RelativeSource.TemplatedParent*.

The method ProvideValue returns a [TemplateBindingExpression](/Gui.Core/_TemplateBindingExpression.md).

Example:

```
<ControlTemplate Key="buttonTemplate" TargetType="{x:Type Button}">
  <Border Background="{TemplateBinding Background}"/>
</ControlTemplate>
```

# Inheritance Hierarchy

• [MarkupExtension](/Gui.Core/_MarkupExtension.md)

• *TemplateBindingExtension*

# Properties

| Name | Description |
| --- | --- |
| ○ *Property* | Gets or sets the source property being bound to |

● Dependency Property   ○ Reflection Property

# Attached Properties

TemplateBindingExtension has no attached properties

# Methods

## From [MarkupExtension](/Gui.Core/_MarkupExtension.md)

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that is provided as the value of the target property for this extension |

# Events

TemplateBindingExtension has no events