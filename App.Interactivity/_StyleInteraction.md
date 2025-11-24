Source: https://www.noesisengine.com/docs/App.Interactivity._StyleInteraction.html

# StyleInteraction Class

## namespace [NoesisApp](/Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

Allows setting a collection of *Interactivity* behaviors and triggers in a [Style](/Gui.Core/_Style.md), so they are applied to all instances of the styled control.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <Grid.Resources>
    <Style TargetType="Button" BasedOn="{StaticResource {x:Type Button}}">
      <Setter Property="noesis:StyleInteraction.Triggers">
        <Setter.Value>
          <noesis:StyleTriggerCollection>
            <b:EventTrigger EventName="Click">
              <b:PlaySoundAction Source="Sounds/ButtonClick.wav" />
            </b:EventTrigger>
          </noesis:StyleTriggerCollection>
        </Setter.Value>
      </Setter>
    </Style>
  </Grid.Resources>
  ...
</Grid>
```

# Inheritance Hierarchy

• *StyleInteraction*

# Properties

StyleInteraction has no properties

# Attached Properties

StyleInteraction has no attached properties

# Methods

StyleInteraction has no methods

# Events

StyleInteraction has no events