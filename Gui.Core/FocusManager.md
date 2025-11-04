# FocusManager Class

## namespace Noesis | MSDN

Provides a set of static methods, attached properties, and events for determining and setting focus scopes and for setting the focused element within the scope.

There are two concepts concerning focus: keyboard focus and logical focus.

Keyboard focus pertains to the element that is currently receiving keyboard input. There can be only one element with keyboard focus. This element with keyboard focus has IsKeyboardFocused set to true. Keyboard.FocusedElement returns the element with keyboard focus.

Logical focus pertains to the FocusManager.FocusedElement within a specific focus scope.

There can be multiple elements with logical focus, but there can only be one element with logical focus within a single focus scope. An element with logical focus has IsFocused set to true, but does not necessarily have keyboard focus. However, an element with keyboard focus will have logical focus.

It is possible to define a focus scope within a focus scope. In this case, both the parent focus scope and the child focus scope can have a FocusManager.FocusedElement.

# Inheritance Hierarchy

 • FocusManager

# Properties

FocusManager has no properties

# Attached Properties

| Property | Description |
|----------|-------------|
| FocusedElement | Determines whether the element this property is attached to has logical focus |
| IsFocusScope | Determines whether the element this property is attached to is a focus scope |

# Methods

| Method | Description |
|--------|-------------|
| AddGotFocusHandler(element, handler) | Adds a handler for the GotFocus attached event |
| AddLostFocusHandler(element, handler) | Adds a handler for the LostFocus attached event |
| GetFocusScope(element) | Determines the closest ancestor of the specified element that has IsFocusScope set to true |
| RemoveGotFocusHandler(element, handler) | Removes a handler for the GotFocus attached event |
| RemoveLostFocusHandler(element, handler) | Removes a handler for the LostFocus attached event |

# Events

FocusManager has no events