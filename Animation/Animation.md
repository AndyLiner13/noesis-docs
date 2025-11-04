# Animation

The animation system in the Gui allows changing the values of dependency properties over time.
As in WPF, animations can be instantiated from a XAML file or directly from code.

## Important concepts

Animations can only be applied to dependency properties in dependency objects, because the design of the later allows to store and represent an animated value without losing the original value in the property. For example, if a NsFloat32 property is set to a value of 10, and later there is an animation that modifies this value to get an eye-candy effect when the user clicks a button, the original value of 10 is preserved and can be obtained at any moment.

In the animation system, there are three important objects that are needed for the magic to work:

### Timeline

Is the object that describes how a value changes over time.

A single timeline can be applied to many properties, and there are many types of timelines that vary from simple linear interpolations to the composition of several timelines using non-linear functions like splines.

The timeline hierarchy is the most important concept in the animation package, so a detailed explanation is here: [Timeline](https://www.noesisengine.com/docs/Gui.Animation.Timeline.html)

### Clock

Every active timeline has al least one clock associated to it.

The clock is the responsible of computing the current time, call the timeline to get the updated value, and assign the resulting value to the target property.

A single clock can be applied to many properties in different objects. See more here [Clocks](https://www.noesisengine.com/docs/Gui.Animation.Clocks.html)

### Time Manager

Manages the running clocks, updating them in every tick.

The time manager should not be accessed directly by the programmer, because there are methods in the timeline classes that allows the management of clocks from them.

## Table of Contents

- [Important concepts](#important-concepts)
  - [Timeline](#timeline)
  - [Clock](#clock)
  - [Time Manager](#time-manager)