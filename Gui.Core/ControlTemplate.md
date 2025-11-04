# ControlTemplate Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.controls.controltemplate.aspx)

Specifies the visual structure and behavioral aspects of a [Control](https://www.noesisengine.com/docs/Gui.Core._Control.html) that can be shared across multiple instances of the control.

# Inheritance Hierarchy

 • [FrameworkTemplate](https://www.noesisengine.com/docs/Gui.Core._FrameworkTemplate.html) • ControlTemplate

# Properties

| Property | Description |
|----------|-------------|
| TargetType | Gets or sets the type for which this template is intended |
| Triggers | Gets a collection of TriggerBase objects that apply property changes or perform actions based on specified conditions |

## From [FrameworkTemplate](https://www.noesisengine.com/docs/Gui.Core._FrameworkTemplate.html)

| Property | Description |
|----------|-------------|
| Resources | Gets or sets the collection of resources that can be used within the scope of this template |
| VisualTree | Gets or sets the root node of the template |

# Attached Properties

ControlTemplate has no attached properties

# Methods

## From [FrameworkTemplate](https://www.noesisengine.com/docs/Gui.Core._FrameworkTemplate.html)

| Method | Description |
|--------|-------------|
| Apply(templatedParent) | Applies current template to the specified element |
| FindName(name, templatedParent) | Finds the element associated with the specified name defined within this template |
| FindName(name) | Returns an object that has the provided identifying name |
| FindObject(object) | Finds if element is a named object registered in the template. Returns null if not found |
| GetAvailableTriggers() | Gets template triggers if available |
| RegisterName(name, object) | Registers the provided name into the current XAML namescope |
| UnregisterName(name) | Unregisters the provided name from the current XAML namescope |
| UpdateName(name, object) | Updates previously registered item with new one. This is required to refresh Binginds when freezables are cloned during animations |

# Events

ControlTemplate has no events