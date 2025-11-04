# AnimationClock Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.animation.animationclock.aspx)

Maintains the run-time state of an [AnimationTimeline](https://www.noesisengine.com/docs/Gui.Animation._AnimationTimeline.html) and processes its output values.

## Inheritance Hierarchy

- [Clock](https://www.noesisengine.com/docs/Gui.Animation._Clock.html)
- AnimationClock

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

AnimationClock has no attached properties

## Methods

### Own Methods

| Method | Description |
|--------|-------------|
| Start(object, dp, timeManager, handoff) | Starts the animation for the specified object and property |

### From [Clock](https://www.noesisengine.com/docs/Gui.Animation._Clock.html)

| Method | Description |
|--------|-------------|
| GetCurrentState() | Gets a value indicating whether the clock is currently Active, Filling or Stopped |
| HasControllableRoot() | Gets a value that indicates whether this Clock is part of a controllable clock tree |

## Events

### From [Clock](https://www.noesisengine.com/docs/Gui.Animation._Clock.html)

| Event | Description |
|-------|-------------|
| Completed | Occurs when this clock has completely finished playing |