# FrameworkTemplate Class

## namespace Noesis | MSDN

Enables the instantiation of a tree of elements for a template.

# Inheritance Hierarchy

 • FrameworkTemplate • ControlTemplate • DataTemplate • ItemsPanelTemplate

# Properties

| Property | Description |
|----------|-------------|
| Resources | Gets or sets the collection of resources that can be used within the scope of this template |
| VisualTree | Gets or sets the root node of the template |

# Attached Properties

FrameworkTemplate has no attached properties

# Methods

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

FrameworkTemplate has no events