Source: https://www.noesisengine.com/docs/Gui.Animation._AnimationClock.html

# AnimationClock Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.animation.animationclock.aspx)

Maintains the run-time state of an [AnimationTimeline](/Gui.Animation/_AnimationTimeline.md) and processes its output values.

# Inheritance Hierarchy

• [Clock](/Gui.Animation/_Clock.md)

• *AnimationClock*

# Properties

## From [Clock](/Gui.Animation/_Clock.md)

| Name | Description |
| --- | --- |
| ○ *CurrentIteration* | Get the current iteration of this clock within its current active period, or -1 if this clock is stopped |
| ○ *CurrentProgress* | Gets the current progress of [Clock](/Gui.Animation/_Clock.md) within its current iteration. This is a value between 0.0 and 1.0 |
| ○ *CurrentTime* | Gets this clock's current time within its current iteration |
| ○ *Parent* | Gets or sets the clock that is the parent of this clock |
| ○ *Timeline* | Gets the [Timeline](/Gui.Animation/_Timeline.md) from which this [Clock](/Gui.Animation/_Clock.md) was created |

● Dependency Property   ○ Reflection Property

# Attached Properties

AnimationClock has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *Start(object, dp, timeManager, handoff)* | Starts the animation for the specified object and property |

## From [Clock](/Gui.Animation/_Clock.md)

| Name | Description |
| --- | --- |
|  *GetCurrentState()* | Gets a value indicating whether the clock is currently *Active*, *Filling* or *Stopped* |
|  *HasControllableRoot()* | Gets a value that indicates whether this [Clock](/Gui.Animation/_Clock.md) is part of a controllable clock tree |

# Events

## From [Clock](/Gui.Animation/_Clock.md)

| Name | Description |
| --- | --- |
| ◆ *Completed* | Occurs when this clock has completely finished playing |

▸ Routed Event    Non-routed Event   ◆ Delegate Event