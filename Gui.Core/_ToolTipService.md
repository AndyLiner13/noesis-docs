Source: https://www.noesisengine.com/docs/Gui.Core._ToolTipService.html

# ToolTipService Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.controls.tooltipservice.aspx)

Represents a service that provides properties and events to control the display and behavior of tooltips.

You define a tooltip for an element by setting the [FrameworkElement](_FrameworkElement.md).ToolTip property. The [ToolTip](_ToolTip.md) property takes one child. The content of the child can vary from a simple text string to more complex content such as a [StackPanel](_StackPanel.md) that has embedded text and [Image](_Image.md) elements.

# Inheritance Hierarchy

• *ToolTipService*

# Properties

ToolTipService has no properties

# Attached Properties

| Name | Description |
| --- | --- |
| ● *BetweenShowDelay* | Gets or sets the maximum time between the display of two tooltips where the second tooltip appears without a delay |
| ● *HasDropShadow* | Gets or sets whether the tooltip displays a drop shadow effect |
| ● *HorizontalOffset* | Gets or sets the offset from the left of the area that is specified for the tooltip by the *PlacementRectangle* and *PlacementTarget* properties |
| ● *InitialShowDelay* | Gets or sets the length of time before a tooltip opens |
| ● *IsEnabled* | Gets or sets whether a tooltip appears |
| ● *IsOpen* | Gets or sets whether a tooltip is currently visible |
| ● *Placement* | Gets or sets the orientation of the tooltip when it opens, and specifies how the tooltip behaves when it overlaps screen boundaries |
| ● *PlacementRectangle* | Gets or sets the rectangular area relative to which the tooltip is positioned |
| ● *PlacementTarget* | Gets or sets the object relative to which the tooltip is positioned |
| ● *ShowDuration* | Gets or sets the amount of time that a tooltip remains visible |
| ● *ShowOnDisabled* | Gets or sets whether a tooltip appears for an object that is not enabled |
| ● *ToolTip* | Gets or sets the content of a tooltip |
| ● *VerticalOffset* | Gets or sets the distance from the top of the area that is specified for the tooltip by the *PlacementRectangle* and *PlacementTarget* properties |

# Methods

| Name | Description |
| --- | --- |
|  *FindValidToolTipOwner(obj)* | Finds the first object in the tree from the specified element that can show a tooltip |

# Events

ToolTipService has no events