Source: https://www.noesisengine.com/docs/App.Interactivity._SortComparer.html

# SortComparer Class

## namespace [NoesisApp](/Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

Base class for Comparer object used by [CollectionSortBehavior](/App.Interactivity/_CollectionSortBehavior.md). It compares 2 items.

# Inheritance Hierarchy

• *SortComparer*

• [StringSortComparer](/App.Interactivity/_StringSortComparer.md)

# Properties

| Name | Description |
| --- | --- |
| ○ *ItemsSource* | Gets or sets the source collection of items |

● Dependency Property   ○ Reflection Property

# Attached Properties

SortComparer has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *Compare(i0, i1)* | Compares two objects indicating whether one is less than (< 0), equal to (== 0), or greater than the other (> 0) |
|  *NeedsRefresh(item, propertyName)* | Indicates if sort should be re-evaluated after an item property change |
|  *Refresh()* | Triggers a new sort of the list |

# Events

| Name | Description |
| --- | --- |
| ◆ *SortRequired* | Indicates that conditions changed and sort needs to be re-evaluated |

▸ Routed Event    Non-routed Event   ◆ Delegate Event