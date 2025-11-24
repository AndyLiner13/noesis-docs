Source: https://www.noesisengine.com/docs/Gui.Core._BaseCommand.html

# BaseCommand Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace)

Base class for commands.

*Commands* allows you to define actions in one place and then refer to them from all your user interface controls like menu items, toolbar or buttons. Examples of commands are the *Copy*, *Cut*, and *Paste* operations found on many applications. Applications often expose these actions through many mechanisms simultaneously: *MenuItems* in a [Menu](/Gui.Core/_Menu.md), *MenuItems* on a [ContextMenu](/Gui.Core/_ContextMenu.md), *Buttons* on a [ToolBar](/Gui.Core/_ToolBar.md), *keyboard shortcuts* and so on.

# Inheritance Hierarchy

• *BaseCommand*

• [RoutedCommand](/Gui.Core/_RoutedCommand.md)

# Properties

BaseCommand has no properties

# Attached Properties

BaseCommand has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *CanExecute(param)* | Determines whether the command can execute in its current state |
|  *CanExecuteChanged()* | Occurs when something changes that affects whether or not the command should execute |
|  *Execute(param)* | This method is called when command is invoked |

# Events

BaseCommand has no events