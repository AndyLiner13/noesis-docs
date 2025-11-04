# Clock Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.animation.clock.aspx)

Maintains run-time timing state for a [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html).

A [Timeline](https://www.noesisengine.com/docs/Gui.Animation._Timeline.html), by itself, doesn't actually do anything other than describe a segment of time. It's the timeline's Clock object that does the real work: it maintains timing-related run-time state for the timeline.

## Inheritance Hierarchy

- Clock
  - [AnimationClock](https://www.noesisengine.com/docs/Gui.Animation._AnimationClock.html)
  - [ClockGroup](https://www.noesisengine.com/docs/Gui.Animation._ClockGroup.html)

## Properties

| Property | Description |
|----------|-------------|
| CurrentIteration | Get the current iteration of this clock within its current active period, or -1 if this clock is stopped |
| CurrentProgress | Gets the current progress of Clock within its current iteration. This is a value between 0.0 and 1.0 |
| CurrentTime | Gets this clock's current time within its current iteration |
| Parent | Gets or sets the clock that is the parent of this clock |
| Timeline | Gets the Timeline from which this Clock was created |

## Attached Properties

Clock has no attached properties

## Methods

| Method | Description |
|--------|-------------|
| GetCurrentState() | Gets a value indicating whether the clock is currently Active, Filling or Stopped |
| HasControllableRoot() | Gets a value that indicates whether this Clock is part of a controllable clock tree |

## Events

| Event | Description |
|-------|-------------|
| Completed | Occurs when this clock has completely finished playing |