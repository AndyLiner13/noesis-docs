Source: https://www.noesisengine.com/docs/Gui.Core._ObservableCollection.html

# ObservableCollection Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace)

Represents a dynamic data collection that provides notifications when items get added or removed.

It is frequently used in data binding to display a collection of records within an *ItemsControl* such as a *ListBox*, *ListView* or *TreeView*.

```
<ListBox Width="200"
    ItemsSource="{Binding Source={StaticResource NameListData}}"
    ItemTemplate="{StaticResource NameItemTemplate}" />
```

# Inheritance Hierarchy

• *ObservableCollection*

# Properties

ObservableCollection has no properties

# Attached Properties

ObservableCollection has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *Add(item)* | Adds an item to the collection. Returns The position into which the new element was inserted, or -1 to indicate that the item was not inserted into the collection |
|  *Contains(item)* | Determines whether the collection contains a specific value |
|  *Get(index)* | Gets the element at the specified index |
|  *IndexOf(item)* | Determines the index of a specific item in the collection. Returns -1 if not found |
|  *Insert(index, item)* | Inserts an item to the collection at the specified index |
|  *Remove(item)* | Removes the first occurrence of a specific object from the collection. Returns true if item was removed, false to indicate that the item was not found in the collection |
|  *Set(index, item)* | Sets the element at the specified index |

# Events

ObservableCollection has no events