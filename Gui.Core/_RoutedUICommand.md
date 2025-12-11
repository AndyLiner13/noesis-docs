Source: https://www.noesisengine.com/docs/Gui.Core._RoutedUICommand.html

# RoutedUICommand Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.input.routeduicommand.aspx)

A command that is routed through the element tree and contains a text property.

The following built-in commands are available in the *ApplicationCommands* class:

- CancelPrint, Close, [ContextMenu](_ContextMenu.md), Copy, CorrectionList, Cut, Delete, Find, Help, New, Open,
  Paste, Print, PrintPreview, Properties, Redo, Replace, Save, SaveAs, SelectAll, Stop, Undo

The following built-in commands are available in the *ComponentCommands* class:

- ExtendSelectionDown, ExtendSelectionLeft, ExtendSelectionRight, ExtendSelectionUp,
  MoveDown, MoveFocusBack, MoveFocusDown, MoveFocusForward, MoveFocusPageDown, MoveFocusPageUp,
  MoveFocusUp, MoveLeft, MoveRight, MoveToEnd, MoveToHome, MoveToPageDown, MoveToPageUp,
  MoveUp, ScrollByLine, ScrollPageDown, ScrollPageLeft, ScrollPageRight, ScrollPageUp,
  SelectToEnd, SelectToHome, SelectToPageDown, SelectToPageUp

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
    <DockPanel Width="300" Height="300" Background="#505860">
        <Menu DockPanel.Dock="Top">
            <MenuItem Header="File"/>
            <MenuItem Header="Edit">
                <MenuItem Header="Copy" Command="ApplicationCommands.Copy"/>
                <MenuItem Header="Cut" Command="ApplicationCommands.Cut"/>
                <MenuItem Header="Paste" Command="ApplicationCommands.Paste"/>
            </MenuItem>
            <MenuItem Header="Help"/>
        </Menu>
    </DockPanel>
</Grid>
```

# Inheritance Hierarchy

• [BaseCommand](_BaseCommand.md)

• [RoutedCommand](_RoutedCommand.md)

• *RoutedUICommand*

# Properties

| Name | Description |
| --- | --- |
| ○ *Text* | Gets or sets the text that describes this command |

● Dependency Property   ○ Reflection Property

## From [RoutedCommand](_RoutedCommand.md)

| Name | Description |
| --- | --- |
| ○ *InputGestures* | Gets the collection of [InputGesture](_InputGesture.md) objects that are associated with this command |
| ○ *Name* | Gets the name of the command as it is registered in the CommandManager |
| ○ *OwnerType* | Gets the class type of the object that defines the command |

● Dependency Property   ○ Reflection Property

# Attached Properties

RoutedUICommand has no attached properties

# Methods

## From [RoutedCommand](_RoutedCommand.md)

| Name | Description |
| --- | --- |
|  *CanExecute(param, target)* | Determines whether this [RoutedCommand](_RoutedCommand.md) can execute in its current state |
|  *Execute(param, target)* | Executes the [RoutedCommand](_RoutedCommand.md) on the current command target |

## From [BaseCommand](_BaseCommand.md)

| Name | Description |
| --- | --- |
|  *CanExecute(param)* | Determines whether the command can execute in its current state |
|  *CanExecuteChanged()* | Occurs when something changes that affects whether or not the command should execute |
|  *Execute(param)* | This method is called when command is invoked |

# Events

RoutedUICommand has no events