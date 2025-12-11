Source: https://www.noesisengine.com/docs/Gui.Animation._ClockGroup.html

# ClockGroup Class

## namespace [Noesis](../Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.animation.clockgroup.aspx)

An assemblage of [Clock](_Clock.md) types with behavior based off of a [TimelineGroup](_TimelineGroup.md).

# Inheritance Hierarchy

• [Clock](_Clock.md)

• *ClockGroup*

# Properties

## From [Clock](_Clock.md)

| Name | Description |
| --- | --- |
| ○ *CurrentIteration* | Get the current iteration of this clock within its current active period, or -1 if this clock is stopped |
| ○ *CurrentProgress* | Gets the current progress of [Clock](_Clock.md) within its current iteration. This is a value between 0.0 and 1.0 |
| ○ *CurrentTime* | Gets this clock's current time within its current iteration |
| ○ *Parent* | Gets or sets the clock that is the parent of this clock |
| ○ *Timeline* | Gets the [Timeline](_Timeline.md) from which this [Clock](_Clock.md) was created |

● Dependency Property   ○ Reflection Property

# Attached Properties

ClockGroup has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *Add(clock)* | Gets the children collection of this [ClockGroup](_ClockGroup.md) |
|  *GetChild(index)* | Get child at index position |
|  *GetChildrenCount()* | Get number of children |
|  *GetTimeline()* | Gets the [TimelineGroup](_TimelineGroup.md) object that dictates the behavior of this [ClockGroup](_ClockGroup.md) instance |

## From [Clock](_Clock.md)

| Name | Description |
| --- | --- |
|  *GetCurrentState()* | Gets a value indicating whether the clock is currently *Active*, *Filling* or *Stopped* |
|  *HasControllableRoot()* | Gets a value that indicates whether this [Clock](_Clock.md) is part of a controllable clock tree |

# Events

## From [Clock](_Clock.md)

| Name | Description |
| --- | --- |
| ◆ *Completed* | Occurs when this clock has completely finished playing |

▸ Routed Event    Non-routed Event   ◆ Delegate Event