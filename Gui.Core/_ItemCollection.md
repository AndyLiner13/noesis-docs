Source: https://www.noesisengine.com/docs/Gui.Core._ItemCollection.html

# ItemCollection Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](https://msdn.microsoft.com/en-us/library/system.windows.controls.itemcollection.aspx)

Holds the list of items that constitute the content of an [ItemsControl](/Gui.Core/_ItemsControl.md).

# Inheritance Hierarchy

• *ItemCollection*

# Properties

| Name | Description |
| --- | --- |
| ○ *CanFilter* | Gets a value that indicates whether this view supports filtering via the Filter property |
| ○ *CanGroup* | Gets a value that indicates whether this view supports grouping via GroupDescriptions |
| ○ *CanSort* | Gets a value that indicates whether this view supports sorting via SortDescriptions |
| ○ *CurrentItem* | Gets the current item in the view |
| ○ *CurrentPosition* | Gets the ordinal position of the CurrentItem within the view |
| ○ *IsCurrentAfterLast* | Gets a value that indicates whether the CurrentItem of the view is beyond the end of the collection |
| ○ *IsCurrentBeforeFirst* | Gets a value that indicates whether the CurrentItem of the view is beyond the beginning of the collection |
| ○ *IsEmpty* | Returns a value that indicates whether the resulting view is empty. |

● Dependency Property   ○ Reflection Property

# Attached Properties

ItemCollection has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *Add(item)* | Adds an item to the collection. Returns The position into which the new element was inserted, or -1 to indicate that the item was not inserted into the collection |
|  *AddComponent(item)* | Adds an item to the collection. Returns The position into which the new element was inserted, or -1 to indicate that the item was not inserted into the collection |
|  *Clear()* | Removes all items from the collection |
|  *CollectionChanged()* | Occurs when the collection changes |
|  *Contains(item)* | Returns a value that indicates whether a given item belongs to this collection view |
|  *Count()* | Gets the number of items in the collection |
|  *CurrentChanged()* | Occurs after the CurrentItem has changed |
|  *GetComponent(index)* | Gets the item at the specified index |
|  *GetItemAt(index)* | Gets the item at the specified index |
|  *IndexOf(item)* | Determines the index of a specific item in the collection. Returns -1 if not found |
|  *IndexOfComponent(item)* | Determines the index of a specific item in the collection. Returns -1 if not found |
|  *Insert(index, item)* | Inserts an item to the collection at the specified index |
|  *InsertComponent(index, item)* | Inserts an item to the collection at the specified index |
|  *IsReadOnly()* | Check if the itemcollection is related to an external collection, and so it is readonly |
|  *MoveCurrentTo(item)* | Sets the specified item to be the CurrentItem in the view |
|  *MoveCurrentToFirst()* | Sets the first item in the view as the CurrentItem |
|  *MoveCurrentToLast()* | Sets the last item in the view as the CurrentItem |
|  *MoveCurrentToNext()* | Sets the item after the CurrentItem in the view as the CurrentItem |
|  *MoveCurrentToPosition(position)* | Sets the item at the specified index to be the CurrentItem in the view |
|  *MoveCurrentToPrevious()* | Sets the item before the CurrentItem in the view as the CurrentItem |
|  *Refresh()* | Recreates the view |
|  *Remove(item)* | Removes the first occurrence of a specific object from the collection. Returns true if item was removed, false to indicate that the item was not found in the collection |
|  *RemoveAt(index)* | Removes the item at the specified index |
|  *Set(index, item)* | Sets the item at the specified index |
|  *SetComponent(index, item)* | Sets the item at the specified index |
|  *SetView(view)* | To be called from [ItemsControl](/Gui.Core/_ItemsControl.md) when the ItemsSource is assigned with a [CollectionView](/Gui.Core/_CollectionView.md) |

# Events

ItemCollection has no events