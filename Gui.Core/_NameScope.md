Source: https://www.noesisengine.com/docs/Gui.Core._NameScope.html

# NameScope Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](https://learn.microsoft.com/en-us/dotnet/api/system.windows.namescope)

Store relationships between the XAML defined names of objects and their instances.

[NameScope](_NameScope.md) is generally more devoted to supplying infrastructure than for common user code scenarios that involve working with a XAML namescope. For most scenarios, the FindName methods exposed on [FrameworkElement](_FrameworkElement.md) are more appropriate methods to call to search for elements by XAML-defined name. The Name properties exposed by [FrameworkElement](_FrameworkElement.md) are more appropriate properties to use to set the initial name as markup attributes.

The various methods of [NameScope](_NameScope.md) are used by base elements and other classes that maintain XAML namescopes in order to support RegisterName and FindName. You generally use the API in the [NameScope](_NameScope.md) class only if you are replacing or augmenting the base element behavior for how they process XAML namescopes for root elements of a XAML page, and as part of templates (which use a separate XAML namescope from the rest of the page).

# Inheritance Hierarchy

• *NameScope*

# Properties

NameScope has no properties

# Attached Properties

| Name | Description |
| --- | --- |
| ● *NameScope* | Gets or sets the attached [NameScope](_NameScope.md) property |

# Methods

| Name | Description |
| --- | --- |
|  *FindName(name)* | Returns an object that has the provided identifying name |
|  *FindObject(obj)* | Finds the name of an object if it is registered in the [NameScope](_NameScope.md). Returns null if object was not found |
|  *RegisterName(name, obj)* | Registers the provided name into the current XAML namescope |
|  *UnregisterName(name)* | Unregisters the provided name from the current XAML namescope |
|  *UpdateName(name, obj)* | Updates previously registered item with new one. This is required to refresh Binginds when freezables are cloned during animations |

# Events

NameScope has no events