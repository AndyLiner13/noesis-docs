Source: https://www.noesisengine.com/docs/Gui.Core._ItemContainerGenerator.html

# ItemContainerGenerator Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.controls.itemcontainergenerator.aspx)

Generates the user interface on behalf of its host, such as an [ItemsControl](_ItemsControl.md).

# Inheritance Hierarchy

• *ItemContainerGenerator*

# Properties

| Name | Description |
| --- | --- |
| ○ *Status* | Gets the status of the generator |

● Dependency Property   ○ Reflection Property

# Attached Properties

ItemContainerGenerator has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *ContainerFromIndex(index)* | Returns the container corresponding to the item at the given index within the Items |
|  *ContainerFromItem(item)* | Returns the container corresponding to the given item. Returns null if the item does not belong to the item collection, or if no container has been generated for it |
|  *GenerateNext()* | Returns the container element used to display the next item |
|  *GenerateNext(isNewlyRealized)* | Returns the container element used to display the next item. The parameter *isNewlyRealized* will return true if the returned container is newly generated (realized); otherwise, false |
|  *GeneratorPositionFromIndex(itemIndex)* | Returns the GeneratorPosition object that maps to the item at the specified index |
|  *GetItemContainerGeneratorForPanel(panel)* | Return the [ItemContainerGenerator](_ItemContainerGenerator.md) appropriate for use by the given panel |
|  *IndexFromContainer(container)* | Given a generated container, returns the index of the corresponding item within the Items |
|  *IndexFromGeneratorPosition(position)* | Returns the index that maps to the specified GeneratorPosition |
|  *ItemFromContainer(container)* | Returns the item corresponding to the given container. If the element was not generated as a container for this generator's host, the method returns [DependencyProperty](../Gui.DependencySystem/_DependencyProperty.md).UnsetValue |
|  *PrepareItemContainer(container)* | Prepares the specified element as the container for the corresponding item |
|  *Recycle(position, count)* | Recycle generated elements. Equivalent to *Remove()* except that the generator retains this container in a list. This container will be handed back in a future call to *GenerateNext()*. The *position* must refer to a previously generated item, which means its position offset must be 0. The parameter *count* is the number of elements to recycle, starting at *position* |
|  *Remove(position, count)* | Removes one or more generated (realized) items. The *position* must refer to a previously generated item, which means its position offset must be 0. The parameter *count* indicates the number of elements to remove, starting at specified *position* |
|  *RemoveAll()* | Removes all generated (realized) items |
|  *StartAt(position, direction)* | Prepare the generator to generate, starting at the given position and direction. This method must be called before calling *GenerateNext()*. This method sets the generator's status to *GeneratingContainers*; when generation is stopped, the status changes to *ContainersGenerated* or *Error*, as appropriate |
|  *StartAt(position, direction, allowStartAtRealizedItem)* | Prepare the generator to generate, starting at the given position and direction. This method must be called before calling *GenerateNext()*. This method sets the generator's status to *GeneratingContainers*; when generation is stopped, the status changes to *ContainersGenerated* or *Error*, as appropriate. The parameter *allowStartAtRealizedItem* specifies whether to start at a generated item or not |
|  *StartBatch()* | Starts a container generation batch |
|  *Stop()* | Stops generation of containers |
|  *StopBatch()* | Stops current container generation batch |

# Events

| Name | Description |
| --- | --- |
| ◆ *ItemsChanged* | Raised by a [ItemContainerGenerator](_ItemContainerGenerator.md) to inform layouts that the items collection has changed |
| ◆ *StatusChanged* | Raised to inform controls that [ItemContainerGenerator](_ItemContainerGenerator.md) status has changed |

▸ Routed Event    Non-routed Event   ◆ Delegate Event