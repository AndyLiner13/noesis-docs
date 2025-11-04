# ClockGroup Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.animation.clockgroup.aspx)

An assemblage of [Clock](https://www.noesisengine.com/docs/Gui.Animation._Clock.html) types with behavior based off of a [TimelineGroup](https://www.noesisengine.com/docs/Gui.Animation._TimelineGroup.html).

## Inheritance Hierarchy

- [Clock](https://www.noesisengine.com/docs/Gui.Animation._Clock.html)
- ClockGroup

## Properties

### From [Clock](https://www.noesisengine.com/docs/Gui.Animation._Clock.html)

| Property | Description |
|----------|-------------|
| CurrentIteration | Get the current iteration of this clock within its current active period, or -1 if this clock is stopped |
| CurrentProgress | Gets the current progress of Clock within its current iteration. This is a value between 0.0 and 1.0 |
| CurrentTime | Gets this clock's current time within its current iteration |
| Parent | Gets or sets the clock that is the parent of this clock |
| Timeline | Gets the Timeline from which this Clock was created |

## Attached Properties

ClockGroup has no attached properties

## Methods

### From [Clock](https://www.noesisengine.com/docs/Gui.Animation._Clock.html)

| Method | Description |
|--------|-------------|
| GetCurrentState() | Gets a value indicating whether the clock is currently Active, Filling or Stopped |
| HasControllableRoot() | Gets a value that indicates whether this Clock is part of a controllable clock tree |

### Own Methods

| Method | Description |
|--------|-------------|
| Add(clock) | Gets the children collection of this ClockGroup |
| GetChild(index) | Get child at index position |
| GetChildrenCount() | Get number of children |
| GetTimeline() | Gets the TimelineGroup object that dictates the behavior of this ClockGroup instance |

## Events

### From [Clock](https://www.noesisengine.com/docs/Gui.Animation._Clock.html)

| Event | Description |
|-------|-------------|
| Completed | Occurs when this clock has completely finished playing |