Source: https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html

# DispatcherObject Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](https://msdn.microsoft.com/en-us/library/system.windows.threading.dispatcherobject.aspx)

Represents an object with thread affinity.

This object can be accessed only from the thread on which it was created. Subclasses of [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) that need to enforce thread safety can do so by calling *VerifyAccess* on all public methods. This guarantees the calling thread is the thread that the [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) was created on.

# Inheritance Hierarchy

• *DispatcherObject*

• [DependencyObject](/Gui.DependencySystem/_DependencyObject.md)

# Properties

| Name | Description |
| --- | --- |
| ○ *ThreadId* | Gets the thread this [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) is associated with. Returns NoThreadId when this object is not attached to any thread. |

● Dependency Property   ○ Reflection Property

# Attached Properties

DispatcherObject has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *CheckAccess()* | Determines whether the calling thread has access to this [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) |
|  *VerifyAccess()* | Enforces that the calling thread has access to this [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) |

# Events

DispatcherObject has no events