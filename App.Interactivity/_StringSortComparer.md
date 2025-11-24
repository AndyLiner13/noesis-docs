Source: https://www.noesisengine.com/docs/App.Interactivity._StringSortComparer.html

# StringSortComparer Class

## namespace [NoesisApp](/Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

Compares the text representation of two items for sorting.

# Inheritance Hierarchy

• [SortComparer](/App.Interactivity/_SortComparer.md)

• *StringSortComparer*

# Properties

## From [SortComparer](/App.Interactivity/_SortComparer.md)

| Name | Description |
| --- | --- |
| ○ *ItemsSource* | Gets or sets the source collection of items |

● Dependency Property   ○ Reflection Property

# Attached Properties

StringSortComparer has no attached properties

# Methods

## From [SortComparer](/App.Interactivity/_SortComparer.md)

| Name | Description |
| --- | --- |
|  *Compare(i0, i1)* | Compares two objects indicating whether one is less than (< 0), equal to (== 0), or greater than the other (> 0) |
|  *NeedsRefresh(item, propertyName)* | Indicates if sort should be re-evaluated after an item property change |
|  *Refresh()* | Triggers a new sort of the list |

# Events

## From [SortComparer](/App.Interactivity/_SortComparer.md)

| Name | Description |
| --- | --- |
| ◆ *SortRequired* | Indicates that conditions changed and sort needs to be re-evaluated |

▸ Routed Event    Non-routed Event   ◆ Delegate Event