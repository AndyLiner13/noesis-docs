Source: https://www.noesisengine.com/docs/Gui.Animation._KeyTime.html

# KeyTime Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace)

Specifies the precise timing when a particular key frame should take place

# Inheritance Hierarchy

• *KeyTime*

# Properties

| Name | Description |
| --- | --- |
| ○ *Percent* | Returns the percent value for a [KeyTime](/Gui.Animation/_KeyTime.md) of type KeyTimeType\_Percent |
| ○ *TimeSpan* | Returns the [TimeSpan](/Gui.Animation/_TimeSpan.md) value for a [KeyTime](/Gui.Animation/_KeyTime.md) of type KeyTimeType\_TimeSpan |
| ○ *Type* | Gets the [KeyTime](/Gui.Animation/_KeyTime.md) type |

● Dependency Property   ○ Reflection Property

# Attached Properties

KeyTime has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *FromPercent(value)* | Creates a new [KeyTime](/Gui.Animation/_KeyTime.md) instance, with the KeyTimeType property initialized to the value of the specified parameter |
|  *FromTimeSpan(timeSpan)* | Creates a new [KeyTime](/Gui.Animation/_KeyTime.md) instance, with the KeyTimeType property initialized to the value of the specified parameter |
|  *Paced()* | Creates a Paced [KeyTime](/Gui.Animation/_KeyTime.md) which creates timing behavior resulting in an animation that interpolates at a constant rate |
|  *ToString()* | Generates a string representation of the point The string has the following form: "Uniform", "Paced", "21.5%", or a [TimeSpan](/Gui.Animation/_TimeSpan.md): "0:0:1" |
|  *TryParse(str, result)* | Tries to parse a [KeyTime](/Gui.Animation/_KeyTime.md) from a string |
|  *Uniform()* | Creates a Uniform [KeyTime](/Gui.Animation/_KeyTime.md) which divides the allotted time of the animation evenly between key frames |
|  *operator==(other)* | Compares two KetTime objects |

# Events

KeyTime has no events