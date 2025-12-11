Source: https://www.noesisengine.com/docs/Gui.Core._ContextMenuService.html

# ContextMenuService Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](https://msdn.microsoft.com/en-us/library/system.windows.controls.contextmenuservice.aspx)

Provides the system implementation for displaying a [ContextMenu](_ContextMenu.md).

The following example shows how to use the service to display a [ContextMenu](_ContextMenu.md) on a disabled button. Notice that you set the ShowOnDisabled property on the button that is the parent of the context menu.

XAML

```
<Button Height="30" Content="Disabled Button" IsEnabled="False"
     ContextMenuService.ShowOnDisabled="True">
  <Button.ContextMenu>
    <ContextMenu>
      <MenuItem Header="Item 1"/>
      <MenuItem Header="Item 2"/>
      <MenuItem Header="Item 3"/>
    </ContextMenu>
  </Button.ContextMenu>
</Button>
```

# Inheritance Hierarchy

• *ContextMenuService*

# Properties

ContextMenuService has no properties

# Attached Properties

| Name | Description |
| --- | --- |
| ● *ContextMenu* | Gets or sets the value of the [ContextMenu](_ContextMenu.md) property of the specified object |
| ● *HasDropShadow* | Gets or sets a value that indicates whether the context menu appears with a dropped shadow |
| ● *HorizontalOffset* | Gets or sets the horizontal distance between the target origin and the popup alignment point |
| ● *IsEnabled* | Gets or sets a value that indicates whether the [ContextMenu](_ContextMenu.md) can be shown |
| ● *Placement* | Gets or sets a value that specifies the placement of the [ContextMenu](_ContextMenu.md) relative to the PlacementTarget or PlacementRectangle |
| ● *PlacementRectangle* | Gets or sets the area relative to which the context menu is positioned when it opens |
| ● *PlacementTarget* | Gets or sets the parent control of the [ContextMenu](_ContextMenu.md). |
| ● *ShowOnDisabled* | Gets or sets a value that indicates whether the [ContextMenu](_ContextMenu.md) should be shown when its parent is grayed out |
| ● *VerticalOffset* | Gets or sets a value that indicates where along the y-direction to place the [ContextMenu](_ContextMenu.md) with respect to the parent control |

# Methods

ContextMenuService has no methods

# Events

ContextMenuService has no events