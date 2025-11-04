# BaseCommand Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace)

Base class for commands.

Commands allows you to define actions in one place and then refer to them from all your user interface controls like menu items, toolbar or buttons. Examples of commands are the Copy, Cut, and Paste operations found on many applications. Applications often expose these actions through many mechanisms simultaneously: MenuItems in a [Menu](https://www.noesisengine.com/docs/Gui.Core._Menu.html), MenuItems on a [ContextMenu](https://www.noesisengine.com/docs/Gui.Core._ContextMenu.html), Buttons on a [ToolBar](https://www.noesisengine.com/docs/Gui.Core._ToolBar.html), keyboard shortcuts and so on.

## Inheritance Hierarchy

- BaseCommand
- [RoutedCommand](https://www.noesisengine.com/docs/Gui.Core._RoutedCommand.html)

## Properties

BaseCommand has no properties

## Attached Properties

BaseCommand has no attached properties

## Methods

| Method | Description |
|--------|-------------|
| CanExecute(param) | Determines whether the command can execute in its current state |
| CanExecuteChanged() | Occurs when something changes that affects whether or not the command should execute |
| Execute(param) | This method is called when command is invoked |

## Events

BaseCommand has no events