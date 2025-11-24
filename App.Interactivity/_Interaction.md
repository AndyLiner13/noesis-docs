Source: https://www.noesisengine.com/docs/App.Interactivity._Interaction.html

# Interaction Class

## namespace [NoesisApp](/Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

Manages a collection of behaviors and triggers that expand the object functionality from XAML.

```
<UserControl
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors">
  <b:Interaction.Behaviors>
    <b:MouseDragElementBehavior />
  <b:Interaction.Behaviors>
  <b:Interaction.Triggers>
    <b:EventTrigger EventName="Loaded">
      <b:GoToStateAction StateName="Init" />
    </b:EventTrigger>
  <b:Interaction.Triggers>
</UserControl>
```

# Inheritance Hierarchy

• *Interaction*

# Properties

Interaction has no properties

# Attached Properties

| Name | Description |
| --- | --- |
| ● *Behaviors* | Gets the value of the Behaviors attached property |
| ● *Triggers* | Gets the value of the Triggers attached property |

# Methods

Interaction has no methods

# Events

Interaction has no events