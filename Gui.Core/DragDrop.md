Source: https://www.noesisengine.com/docs/Gui.Core.DragDrop.html

# Drag-and-Drop Overview

![github](https://www.noesisengine.com/docs/github.png) [Tutorial Data](https://github.com/Noesis/Tutorials/tree/master/Samples/Inventory)

This tutorial provides an overview of drag-and-drop support in NoesisGUI. Drag-and-drop commonly refers to a method of data transfer that involves using a mouse (or some other pointing device) to select one or more objects, dragging these objects over some desired drop target in the user interface, and dropping them.

> ![DragDropImg1.png](https://www.noesisengine.com/docs/DragDropImg1.png)

# Drag-and-Drop Support

Drag-and-drop operations typically involve two parties: a *drag source* from which the dragged object originates and a *drop target* which receives the dropped object. The drag source and drop target must be UI elements in the same application.

The type and number of objects that can be manipulated with drag-and-drop is completely arbitrary. For example, files, folders, and selections of content are some of the more common objects manipulated through drag-and-drop operations.

The particular actions performed during a drag-and-drop operation are application specific, and often determined by context. For example, dragging a selection of files from one folder to another on the same storage device moves the files by default, whereas dragging files from another device to a local folder copies the files by default.

In NoesisGUI, any [UIElement](_UIElement.md) can participate in drag-and-drop. The events and methods required for drag-and-drop operations are defined in the [DragDrop](_DragDrop.md) class. The *UIElement* classes contain aliases for the *DragDrop* attached events so that the events appear in the class members list when a *UIElement* is inherited as a base element. Event handlers that are associated to these events are connected to the underlying *DragDrop* attached event and receive the same event data instance. For more information, see the [UIElement](_UIElement.md) *Drop* event.

# Data Transfer

A drag-and-drop operation is analogous to a copy-and-paste operation that is used to transfer data from one object to another. Both types of operations require:

- A source object that provides the data.
- A way to temporarily store the transferred data.
- A target object that receives the data.

In a copy-and-paste operation, the system clipboard is used to temporarily store the transferred data; in a drag-and-drop operation, an object is used to store the data.

The drag source initiates a drag-and-drop operation by calling the static [DragDrop](_DragDrop.md) *DoDragDrop* method and passing the transferred data to it. The drop target should know how to obtain the desired information from the data object received in the event.

The source and target of a drag-and-drop operation are UI elements; however, the data that is actually being transferred typically does not have a visual representation. You can write code to provide a visual representation of the data that is dragged, such as occurs when dragging files in Windows Explorer. By default, feedback is provided to the user by changing the cursor to represent the effect that the drag-and-drop operation will have on the data, such as whether the data will be moved or copied.

## Drag-and-Drop Effects

Drag-and-drop operations can have different effects on the transferred data. For example, you can copy the data or you can move the data. NoesisGUI defines a *DragDropEffects* enumeration that you can use to specify the effect of a drag-and-drop operation.

In the drag source, you can specify the effects that the source will allow in the *DoDragDrop* method. In the drop target, you can specify the effect that the target intends in the *Effects* property of the *DragEventArgs* class. When the drop target specifies its intended effect in the *DragOver* event, that information is passed back to the drag source in the *GiveFeedback* event. The drag source uses this information to inform the user what effect the drop target intends to have on the data. When the data is dropped, the drop target specifies its actual effect in the *Drop* event. When the drop operation is completed that information is passed back to the drag source on the callback supplied to the *DoDragDrop* method. If the drop target returns an effect that is not in the drag sources list of *allowedEffects*, the drag-and-drop operation is cancelled without any data transfer occurring.

It is important to remember that in NoesisGUI, the *DragDropEffects* values are only used to provide communication between the drag source and the drop target regarding the effects of the drag-and-drop operation. The actual effect of the drag-and-drop operation depends on you to write the appropriate code in your application.

For example, the drop target might specify that the effect of dropping data on it is to move the data. However, to move the data, it must be both added to the target element and removed from the source element. The source element might indicate that it allows moving the data, but if you do not provide the code to remove the data from the source element, the end result will be that the data is copied, and not moved.

# Drag-and-Drop Events

Drag-and-drop operations support an event driven model. Both the drag source and the drop target use a standard set of events to handle drag-and-drop operations. The following tables summarize the standard drag-and-drop events. These are *attached events* on the [DragDrop](_DragDrop.md) class.

## Drag Source Events

| Event | Summary |
| --- | --- |
| GiveFeedback | This event occurs continuously during a drag-and-drop operation, and enables the drag source to give feedback information to the user. This feedback is commonly given by changing the appearance of the mouse pointer to indicate the effects allowed by the drop target. This is a bubbling event. |
| QueryContinueDrag | This event occurs when there is a change in the keyboard or mouse button states during a drag-and-drop operation, and enables the drop source to cancel the drag-and-drop operation depending on the key/button states. This is a bubbling event. |
| PreviewGiveFeedback | Tunneling version of *GiveFeedback*. |
| PreviewQueryContinueDrag | Tunneling version of *QueryContinueDrag*. |

## Drop Target Events

| Event | Summary |
| --- | --- |
| DragEnter | This event occurs when an object is dragged into the drop target's boundary. This is a bubbling event. |
| DragLeave | This event occurs when an object is dragged out of the drop target's boundary. This is a bubbling event. |
| DragOver | This event occurs continuously while an object is dragged (moved) within the drop target's boundary. This is a bubbling event. |
| Drop | This event occurs when an object is dropped on the drop target. This is a bubbling event. |
| PreviewDragEnter | Tunneling version of *DragEnter*. |
| PreviewDragLeave | Tunneling version of *DragLeave*. |
| PreviewDragOver | Tunneling version of *DragOver*. |
| PreviewDrop | Tunneling version of *Drop*. |

To handle drag-and-drop events for instances of an object, add handlers for the events listed in the preceding tables. To handle drag-and-drop events at the class level, override the corresponding virtual *OnEvent* and *OnPreviewEvent* methods.

# Implementing Drag-and-Drop

A UI element can be a drag source, a drop target, or both. To implement basic drag-and-drop, you write code to initiate the drag-and-drop operation and to process the dropped data. You can enhance the drag-and-drop experience by handling optional drag-and-drop events.

To implement basic drag-and-drop, you will complete the following tasks:

- Identify the element that will be a drag source. A drag source can be any *UIElement*. We recommend using a [behavior](../App.Interactivity/Behaviors.md) for this purpose.

  ```
  class DragItemBehavior final: public NoesisApp::BehaviorT<Noesis::ContentControl> { };
  ```

  ```
  <ItemsControl ItemsSource="{Binding Inventory}">
    <ItemsControl.ItemTemplate>
        <DataTemplate>
          <ContentControl Content="{Binding}" Style="{StaticResource Style.InventorySlot}">
              <b:Interaction.Behaviors>
                <local:DragItemBehavior/>
              </b:Interaction.Behaviors>
          </ContentControl>
      </DataTemplate>
    </ItemsControl.ItemTemplate>
  </ItemsControl>
  ```
- Create an event handler on the drag source that will initiate the drag-and-drop operation. The event is typically the *MouseMove* event.

  ```
  void DragItemBehavior::OnAttached()
  {
    Noesis::ContentControl* control = GetAssociatedObject();
    control->PreviewMouseMove() += Noesis::MakeDelegate(this, &DragItemBehavior::OnMouseMove);
  }
  ```
- In the drag source event handler, call the *DoDragDrop* method to initiate the drag-and-drop operation. In the *DoDragDrop* call, specify the drag source, the data to be transferred, the allowed effects and an optional callback to be notified of the result of the drop operation.

  ```
  void DragItemBehavior::OnMouseMove(Noesis::BaseComponent* sender, const Noesis::MouseEventArgs& e)
  {
    if (_mouseClicked)
    {
      Noesis::ContentControl* control = GetAssociatedObject();

      Slot* slot = Noesis::DynamicCast<Slot*>(control->GetContent());
      if (slot != nullptr && slot->GetItem() != nullptr)
      {
        slot->StartDragging();

        Noesis::DragDrop::DoDragDrop(control, slot, DragDropEffects_Move,
          [](Noesis::DependencyObject* source, Noesis::BaseComponent* data, Noesis::UIElement* target,
             const Noesis::Point& dropPoint, uint32_t effects)
          {
            Slot* slot = (Slot*)data;
            slot->EndDragging();
          });
      }

      _mouseClicked = false;
    }
  }
  ```
- Identify the element that will be a drop target. A drop target can be any *UIElement*. Here we can also use a [behavior](../App.Interactivity/Behaviors.md).

  ```
  class DropItemBehavior final: public NoesisApp::BehaviorT<Noesis::ContentControl> { };
  ```

  ```
  <ItemsControl ItemsSource="{Binding Equipment}">
    <ItemsControl.ItemTemplate>
        <DataTemplate>
          <ContentControl Content="{Binding}" Style="{StaticResource Style.EquipmentSlot}">
              <b:Interaction.Behaviors>
                <local:DropItemBehavior/>
              </b:Interaction.Behaviors>
          </ContentControl>
      </DataTemplate>
    </ItemsControl.ItemTemplate>
  </ItemsControl>
  ```
- On the drop target, set the *AllowDrop* property to true.
- In the drop target, create a *Drop* event handler to process the dropped data.

  ```
  void DropItemBehavior::OnAttached()
  {
    Noesis::ContentControl* control = GetAssociatedObject();
    control->SetAllowDrop(true);
    control->PreviewDrop() += Noesis::MakeDelegate(this, &DropItemBehavior::OnDrop);
  }
  ```
- In the *Drop* event handler, extract the data from the *DragEventArgs*.
- In the *Drop* event handler, use the data to perform the desired drag-and-drop operation.

  ```
  void DropItemBehavior::OnDrop(Noesis::BaseComponent* sender, const Noesis::DragEventArgs& e)
  {
    Noesis::ContentControl* control = GetAssociatedObject();

    Slot* sourceSlot = (Slot*)e.data;
    Slot* targetSlot = Noesis::DynamicCast<Slot*>(control->GetContent());
    if (targetSlot != nullptr)
    {
      if (targetSlot->IsDropAllowed())
      {
        Item* draggedItem = sourceSlot->GetItem();
        sourceSlot->SetItem(targetSlot->GetItem());
        targetSlot->SetItem(draggedItem);
      }
      else
      {
        e.effects = DragDropEffects_None;
      }
    }

    e.handled = true;
  }
  ```

You can enhance your drag-and-drop implementation by handling optional drag source and drop target events, as shown in the following tasks:

- To transfer custom data or multiple data items, create your own data type to pass to the *DoDragDrop* method.
- To perform additional actions during a drag, handle the *DragEnter*, *DragOver*, and *DragLeave* events on the drop target.
- To change the appearance of the mouse pointer, handle the *GiveFeedback* event on the drag source.
- To change how the drag-and-drop operation is canceled, handle the *QueryContinueDrag* event on the drag source.