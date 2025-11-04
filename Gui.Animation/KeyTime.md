# KeyTime Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace)

Specifies the precise timing when a particular key frame should take place

## Inheritance Hierarchy

- KeyTime

## Properties

| Property | Description |
|----------|-------------|
| Percent | Returns the percent value for a KeyTime of type KeyTimeType_Percent |
| TimeSpan | Returns the TimeSpan value for a KeyTime of type KeyTimeType_TimeSpan |
| Type | Gets the KeyTime type |

## Attached Properties

KeyTime has no attached properties

## Methods

| Method | Description |
|--------|-------------|
| FromPercent(value) | Creates a new KeyTime instance, with the KeyTimeType property initialized to the value of the specified parameter |
| FromTimeSpan(timeSpan) | Creates a new KeyTime instance, with the KeyTimeType property initialized to the value of the specified parameter |
| Paced() | Creates a Paced KeyTime which creates timing behavior resulting in an animation that interpolates at a constant rate |
| ToString() | Generates a string representation of the point The string has the following form: "Uniform", "Paced", "21.5%", or a TimeSpan: "0:0:1" |
| TryParse(str, result) | Tries to parse a KeyTime from a string |
| Uniform() | Creates a Uniform KeyTime which divides the allotted time of the animation evenly between key frames |
| operator==(other) | Compares two KetTime objects |

## Events

KeyTime has no events