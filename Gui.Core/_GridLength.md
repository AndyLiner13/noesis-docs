Source: https://www.noesisengine.com/docs/Gui.Core._GridLength.html

# GridLength Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](https://msdn.microsoft.com/en-us/library/system.windows.gridlength.aspx)

Represents the length of elements that explicitly support *Star* unit types. Elements such as [ColumnDefinition](/Gui.Core/_ColumnDefinition.md) and [RowDefinition](/Gui.Core/_RowDefinition.md) use this type to describe width and height in order to support variable distribution of available space.

# Inheritance Hierarchy

• *GridLength*

# Properties

| Name | Description |
| --- | --- |
| ○ *GridUnitType* | Associated GridUnitType for the [GridLength](/Gui.Core/_GridLength.md) |
| ○ *IsAbsolute* | Indicates whether the [GridLength](/Gui.Core/_GridLength.md) holds a value that is expressed in pixels |
| ○ *IsAuto* | Indicates whether the [GridLength](/Gui.Core/_GridLength.md) holds a value whose size is determined by the size properties of the content object |
| ○ *IsStar* | Indicates whether the [GridLength](/Gui.Core/_GridLength.md) holds a value that is expressed as a weighted proportion of available space |
| ○ *Value* | Gets a float that represents the value of the [GridLength](/Gui.Core/_GridLength.md) |

● Dependency Property   ○ Reflection Property

# Attached Properties

GridLength has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *ToString()* | Creates a string representation of this structure |
|  *TryParse(str, result)* | Tries to parse a [GridLength](/Gui.Core/_GridLength.md) from a string |

# Events

GridLength has no events