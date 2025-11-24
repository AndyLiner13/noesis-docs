Source: https://www.noesisengine.com/docs/Gui.Core._DataTemplate.html

# DataTemplate Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.datatemplate.aspx)

Describes the visual structure of a data object.

# Inheritance Hierarchy

• [FrameworkTemplate](/Gui.Core/_FrameworkTemplate.md)

• *DataTemplate*

• [HierarchicalDataTemplate](/Gui.Core/_HierarchicalDataTemplate.md)

# Properties

| Name | Description |
| --- | --- |
| ○ *DataType* | Gets or sets the type for which this [DataTemplate](/Gui.Core/_DataTemplate.md) is intended |
| ○ *Triggers* | Gets a collection of triggers that apply property values or perform actions based on one or more conditions. |

● Dependency Property   ○ Reflection Property

## From [FrameworkTemplate](/Gui.Core/_FrameworkTemplate.md)

| Name | Description |
| --- | --- |
| ○ *Resources* | Gets or sets the collection of resources that can be used within the scope of this template |
| ○ *VisualTree* | Gets or sets the root node of the template |

● Dependency Property   ○ Reflection Property

# Attached Properties

DataTemplate has no attached properties

# Methods

## From [FrameworkTemplate](/Gui.Core/_FrameworkTemplate.md)

| Name | Description |
| --- | --- |
|  *Apply(templatedParent)* | Applies current template to the specified element |
|  *FindName(name, templatedParent)* | Finds the element associated with the specified name defined within this template |
|  *FindName(name)* | Returns an object that has the provided identifying name |
|  *FindObject(object)* | Finds if element is a named object registered in the template. Returns null if not found |
|  *GetAvailableTriggers()* | Gets template triggers if available |
|  *RegisterName(name, object)* | Registers the provided name into the current XAML namescope |
|  *UnregisterName(name)* | Unregisters the provided name from the current XAML namescope |
|  *UpdateName(name, object)* | Updates previously registered item with new one. This is required to refresh Binginds when freezables are cloned during animations |

# Events

DataTemplate has no events