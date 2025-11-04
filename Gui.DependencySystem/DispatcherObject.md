# DispatcherObject Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](https://msdn.microsoft.com/en-us/library/system.windows.threading.dispatcherobject.aspx)

Represents an object with thread affinity.

# Inheritance Hierarchy

 • DispatcherObject • [DependencyObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html)

# Properties

| Property | Description |
|----------|-------------|
| ThreadId | Gets the thread this DispatcherObject is associated with. Returns NoThreadId when this object is not attached to any thread. |

# Attached Properties

DispatcherObject has no attached properties

# Methods

| Method | Description |
|--------|-------------|
| CheckAccess() | Determines whether the calling thread has access to this DispatcherObject |
| VerifyAccess() | Enforces that the calling thread has access to this DispatcherObject |

# Events

DispatcherObject has no events