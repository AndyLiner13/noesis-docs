Source: https://www.noesisengine.com/docs/Gui.Animation._RepeatBehavior.html

# RepeatBehavior Class

## namespace [Noesis](../Gui.Core/_ClassHierarchy.md#noesis-namespace)

Describes how a [Timeline](_Timeline.md) repeats its simple duration. Examples:
:   RepeatBehavior="2x" ---> Repeats 2 times
    RepeatBehavior="1.2:30:15.500" ---> [days.]hours:minutes:seconds[.fractionalSeconds]
    RepeatBehavior="2.1:20" ---> [days.]hours:minutes
    RepeatBehavior="5" ---> days
    RepeatBehavior="Forever" ---> Repeats forever

# Inheritance Hierarchy

• *RepeatBehavior*

# Properties

| Name | Description |
| --- | --- |
| ○ *Count* | Gets repeat count. Only valid for repeat mode *Count* |
| ○ *Duration* | Gets repeat time duration. Only valid for repeat mode *Duration* |
| ○ *RepeatMode* | Gets repeat mode |

● Dependency Property   ○ Reflection Property

# Attached Properties

RepeatBehavior has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *Forever()* | Creates a [RepeatBehavior](_RepeatBehavior.md) object that specifies an infinite number of repetitions |
|  *ToString()* | Generates a string representation of the point The string has the following form: "Forever", "2x", or a [TimeSpan](_TimeSpan.md): "0:0:1" |
|  *TryParse(txt, result)* | Tries to parse a [RepeatBehavior](_RepeatBehavior.md) from a string |

# Events

RepeatBehavior has no events