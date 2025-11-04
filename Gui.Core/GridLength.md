# GridLength Class

## namespace Noesis

Represents the length of elements that explicitly support Star unit types. Elements such as ColumnDefinition and RowDefinition use this type to describe width and height in order to support variable distribution of available space.

## Inheritance Hierarchy

- GridLength

## Properties

| Property | Description |
|----------|-------------|
| GridUnitType | Associated GridUnitType for the GridLength |
| IsAbsolute | Indicates whether the GridLength holds a value that is expressed in pixels |
| IsAuto | Indicates whether the GridLength holds a value whose size is determined by the size properties of the content object |
| IsStar | Indicates whether the GridLength holds a value that is expressed as a weighted proportion of available space |
| Value | Gets a float that represents the value of the GridLength |

## Attached Properties

GridLength has no attached properties

## Methods

| Method | Description |
|--------|-------------|
| ToString() | Creates a string representation of this structure |
| TryParse(str, result) | Tries to parse a GridLength from a string |

## Events

GridLength has no events