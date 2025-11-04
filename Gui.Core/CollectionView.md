# CollectionView Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](https://msdn.microsoft.com/en-us/library/system.windows.data.collectionview.aspx)

Represents a view for grouping, sorting, filtering, and navigating a data collection.

## Inheritance Hierarchy

 • CollectionView

## Properties

| Property | Description |
|----------|-------------|
| Count | Gets the number of records in the view |
| CanFilter | Gets a value that indicates whether this view supports filtering via the Filter property |
| CanGroup | Gets a value that indicates whether this view supports grouping via GroupDescriptions |
| CanSort | Gets a value that indicates whether this view supports sorting via SortDescriptions |
| CurrentItem | Gets the current item in the view |
| CurrentPosition | Gets the ordinal position of the CurrentItem within the view |
| IsCurrentAfterLast | Gets a value that indicates whether the CurrentItem of the view is beyond the end of the collection |
| IsCurrentBeforeFirst | Gets a value that indicates whether the CurrentItem of the view is beyond the beginning of the collection |
| IsEmpty | Returns a value that indicates whether the resulting view is empty. |

## Attached Properties

CollectionView has no attached properties

## Methods

| Method | Description |
|--------|-------------|
| CollectionChanged() | Occurs when the collection changes |
| Contains(item) | Returns a value that indicates whether a given item belongs to this collection view |
| CurrentChanged() | Occurs after the CurrentItem has changed |
| GetItemAt(index) | Retrieves the item at the specified zero-based index in the view |
| GetSourceCollection() | Returns the underlying unfiltered collection |
| IndexOf(item) | Returns the index at which the specified item is located; -1 if the item is unknown |
| MoveCurrentTo(item) | Sets the specified item to be the CurrentItem in the view |
| MoveCurrentToFirst() | Sets the first item in the view as the CurrentItem |
| MoveCurrentToLast() | Sets the last item in the view as the CurrentItem |
| MoveCurrentToNext() | Sets the item after the CurrentItem in the view as the CurrentItem |
| MoveCurrentToPosition(position) | Sets the item at the specified index to be the CurrentItem in the view |
| MoveCurrentToPrevious() | Sets the item before the CurrentItem in the view as the CurrentItem |
| Refresh() | Recreates the view |

## Events

CollectionView has no events