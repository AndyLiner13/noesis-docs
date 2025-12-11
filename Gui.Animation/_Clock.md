Source: https://www.noesisengine.com/docs/Gui.Animation._Clock.html

# Clock Class

## namespace [Noesis](../Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.animation.clock.aspx)

Maintains run-time timing state for a [Timeline](_Timeline.md).

A [Timeline](_Timeline.md), by itself, doesn't actually do anything other than describe a segment of time. It's the timeline's [Clock](_Clock.md) object that does the real work: it maintains timing-related run-time state for the timeline.

# Inheritance Hierarchy

• *Clock*

• [AnimationClock](_AnimationClock.md)

• [ClockGroup](_ClockGroup.md)

# Properties

| Name | Description |
| --- | --- |
| ○ *CurrentIteration* | Get the current iteration of this clock within its current active period, or -1 if this clock is stopped |
| ○ *CurrentProgress* | Gets the current progress of [Clock](_Clock.md) within its current iteration. This is a value between 0.0 and 1.0 |
| ○ *CurrentTime* | Gets this clock's current time within its current iteration |
| ○ *Parent* | Gets or sets the clock that is the parent of this clock |
| ○ *Timeline* | Gets the [Timeline](_Timeline.md) from which this [Clock](_Clock.md) was created |

● Dependency Property   ○ Reflection Property

# Attached Properties

Clock has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *GetCurrentState()* | Gets a value indicating whether the clock is currently *Active*, *Filling* or *Stopped* |
|  *HasControllableRoot()* | Gets a value that indicates whether this [Clock](_Clock.md) is part of a controllable clock tree |

# Events

| Name | Description |
| --- | --- |
| ◆ *Completed* | Occurs when this clock has completely finished playing |

▸ Routed Event    Non-routed Event   ◆ Delegate Event