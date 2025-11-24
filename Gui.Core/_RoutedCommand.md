Source: https://www.noesisengine.com/docs/Gui.Core._RoutedCommand.html

# RoutedCommand Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.input.routedcommand.aspx)

A command that is routed through the element tree.

# Inheritance Hierarchy

• [BaseCommand](/Gui.Core/_BaseCommand.md)

• *RoutedCommand*

• [RoutedUICommand](/Gui.Core/_RoutedUICommand.md)

# Properties

| Name | Description |
| --- | --- |
| ○ *InputGestures* | Gets the collection of [InputGesture](/Gui.Core/_InputGesture.md) objects that are associated with this command |
| ○ *Name* | Gets the name of the command as it is registered in the CommandManager |
| ○ *OwnerType* | Gets the class type of the object that defines the command |

● Dependency Property   ○ Reflection Property

# Attached Properties

RoutedCommand has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *CanExecute(param, target)* | Determines whether this [RoutedCommand](/Gui.Core/_RoutedCommand.md) can execute in its current state |
|  *Execute(param, target)* | Executes the [RoutedCommand](/Gui.Core/_RoutedCommand.md) on the current command target |

## From [BaseCommand](/Gui.Core/_BaseCommand.md)

| Name | Description |
| --- | --- |
|  *CanExecute(param)* | Determines whether the command can execute in its current state |
|  *CanExecuteChanged()* | Occurs when something changes that affects whether or not the command should execute |
|  *Execute(param)* | This method is called when command is invoked |

# Events

RoutedCommand has no events