Source: https://www.noesisengine.com/docs/Gui.Core._Condition.html

# Condition Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.condition.aspx)

Represents a condition for the [MultiTrigger](_MultiTrigger.md) and the [MultiDataTrigger](_MultiDataTrigger.md), which apply changes to property values based on a set of conditions.

# Inheritance Hierarchy

• *Condition*

# Properties

| Name | Description |
| --- | --- |
| ○ *Binding* | Gets or sets the binding that produces the property value of the data object. This is only applicable to [MultiDataTrigger](_MultiDataTrigger.md) objects |
| ○ *Property* | Gets or sets the property of the condition. This is only applicable to [MultiTrigger](_MultiTrigger.md) objects |
| ○ *SourceName* | Gets or sets the name of the object with the property that causes the associated setters to be applied. This is only applicable to [MultiTrigger](_MultiTrigger.md) objects |
| ○ *Value* | Gets or sets the value of the condition |

● Dependency Property   ○ Reflection Property

# Attached Properties

Condition has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *Seal()* | Seals this condition |

# Events

Condition has no events