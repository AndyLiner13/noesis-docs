Source: https://www.noesisengine.com/docs/Gui.Core._KeyboardNavigation.html

# KeyboardNavigation Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.input.keyboardnavigation.aspx)

Provides logical and directional navigation between focusable objects.

XAML

```
<Menu KeyboardNavigation.TabNavigation="Cycle">
  <MenuItem Header="Menu Item 1" />
  <MenuItem Header="Menu Item 2" />
  <MenuItem Header="Menu Item 3" />
  <MenuItem Header="Menu Item 4" />
</Menu>
```

The [KeyboardNavigation](/Gui.Core/_KeyboardNavigation.md) class is responsible for implementing default keyboard focus navigation when one of the navigation keys is pressed.

# Inheritance Hierarchy

• *KeyboardNavigation*

# Properties

| Name | Description |
| --- | --- |
| ○ *Root* | Gets View root |

● Dependency Property   ○ Reflection Property

# Attached Properties

| Name | Description |
| --- | --- |
| ● *AcceptsReturn* | Gets or sets a value indicating whether the Return character is accepted by a control |
| ● *ControlTabNavigation* | Gets or sets the logical control tab navigation behavior for the children of the element that this property is set on |
| ● *DirectionalNavigation* | Gets or sets the directional navigation behavior for the children of the element that this property is set on |
| ● *IsTabStop* | Gets or sets a value indicating whether the element that this property is set on is a tab stop |
| ● *TabIndex* | Gets or sets the tab index for the element that this property is set on |
| ● *TabNavigation* | Gets or sets the logical tab navigation behavior for the children of the element that this property is set on |

# Methods

| Name | Description |
| --- | --- |
|  *MoveFocus(source, request)* | Request to move the focus from source element in the specified direction. Returns true if focus is moved successfully, returns false if there is no next element. Note: Internally used by [FrameworkElement](/Gui.Core/_FrameworkElement.md) to implement *MoveFocus()* |
|  *PredictFocus(source, direction)* | Returns the element that would receive focus for a specified focus traversal direction, without actually moving focus to that element. Note: Internally used by [FrameworkElement](/Gui.Core/_FrameworkElement.md) to implement *PredictFocus()* |

# Events

KeyboardNavigation has no events