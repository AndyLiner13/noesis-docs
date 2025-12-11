Source: https://www.noesisengine.com/docs/Gui.Core._ControlTemplate.html

# ControlTemplate Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.controls.controltemplate.aspx)

Specifies the visual structure and behavioral aspects of a [Control](_Control.md) that can be shared across multiple instances of the control.

# Inheritance Hierarchy

• [FrameworkTemplate](_FrameworkTemplate.md)

• *ControlTemplate*

# Properties

| Name | Description |
| --- | --- |
| ○ *TargetType* | Gets or sets the type for which this template is intended |
| ○ *Triggers* | Gets a collection of [TriggerBase](../App.Interactivity/_TriggerBase.md) objects that apply property changes or perform actions based on specified conditions |

● Dependency Property   ○ Reflection Property

## From [FrameworkTemplate](_FrameworkTemplate.md)

| Name | Description |
| --- | --- |
| ○ *Resources* | Gets or sets the collection of resources that can be used within the scope of this template |
| ○ *VisualTree* | Gets or sets the root node of the template |

● Dependency Property   ○ Reflection Property

# Attached Properties

ControlTemplate has no attached properties

# Methods

## From [FrameworkTemplate](_FrameworkTemplate.md)

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

ControlTemplate has no events