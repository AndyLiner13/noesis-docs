Source: https://www.noesisengine.com/docs/Gui.Core._RelativeSource.html

# RelativeSource Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.data.relativesource.aspx)

Implements a markup extension that describes the location of the binding source relative to the position of the binding target.

# Inheritance Hierarchy

• [MarkupExtension](/Gui.Core/_MarkupExtension.md)

• *RelativeSource*

# Properties

| Name | Description |
| --- | --- |
| ○ *AncestorLevel* | Gets or sets the level of ancestor to look for, in FindAncestor mode. Use 1 to indicate the one nearest to the binding target element |
| ○ *AncestorType* | Gets or sets the type of ancestor to look for |
| ○ *Mode* | Gets or sets relative source mode |
| ○ *PreviousData* | Gets a static value that is used to return a [RelativeSource](/Gui.Core/_RelativeSource.md) constructed for the *PreviousData* mode |
| ○ *Self* | Gets a static value that is used to return a [RelativeSource](/Gui.Core/_RelativeSource.md) constructed for the *Self* mode |
| ○ *TemplatedParent* | Gets a static value that is used to return a [RelativeSource](/Gui.Core/_RelativeSource.md) constructed for the *TemplatedParent* mode |

● Dependency Property   ○ Reflection Property

# Attached Properties

RelativeSource has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that should be set as the value on the target object's property for this markup extension. For [RelativeSource](/Gui.Core/_RelativeSource.md), this is another [RelativeSource](/Gui.Core/_RelativeSource.md), using the appropriate source for the specified mode |

## From [MarkupExtension](/Gui.Core/_MarkupExtension.md)

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that is provided as the value of the target property for this extension |

# Events

RelativeSource has no events