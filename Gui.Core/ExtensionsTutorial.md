Source: https://www.noesisengine.com/docs/Gui.Core.ExtensionsTutorial.html

# Noesis Extensions

NoesisGUI implements a wide subset of Microsoft WPF, but it also adds some convenient features on top of it to help designers create even more stunning UI for their games and applications. Some of these features include *Text Stroke* and *Placeholders*, *Focus Engagement*, *Element 3D-Transforms* and *Path Trimming*.

To be able to design user interfaces in Blend and include these extensions, a *NuGet* package is provided in the official repository with the name [Noesis.GUI.Extensions](https://www.nuget.org/packages/Noesis.GUI.Extensions). These extensions are available under the *NoesisGUIExtensions* namespace.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
</Grid>
```

# Text Extensions

## CharacterSpacing

In NoesisGUI we incoporated the CharacterSpacing property defined by UWP text elements. It represents the uniform spacing between characters, in units of 1/1000 of an em.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions"
  Background="White">
    <TextBlock Text="This text has extra character spacing" FontSize="24" Foreground="Black"
      noesis:Text.CharacterSpacing="200"/>
</Grid>
```

![ExtensionsTutorialImg0.png](https://www.noesisengine.com/docs/ExtensionsTutorialImg0.png)

## Stroke

In NoesisGUI text can be stroked by using the attached properties *Text.Stroke* and *Text.StrokeThickness*. The first defines the [Brush](_Brush.md) to fill the stroke, and the latter specifies the width in pixels of the stroke. These properties are inherited down the UI tree.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions"
  Background="White">
    <TextBlock Text="This text is stroked" FontSize="24" Foreground="LightBlue"
      noesis:Text.Stroke="#B000407F" noesis:Text.StrokeThickness="2.5"/>
</Grid>
```

![ExtensionsTutorialImg1.png](https://www.noesisengine.com/docs/ExtensionsTutorialImg1.png)

## Placeholder

Some controls like [TextBox](_TextBox.md), [PasswordBox](_PasswordBox.md) and [ComboBox](_ComboBox.md) can show a placeholder text as a hint of their use. Using *Text.Placeholder* attached property in a control template adds placeholder functionality to the control.

```
<ControlTemplate x:Key="Template.TextBox" TargetType="TextBox">
  <Grid Background="{TemplateBinding Background}">
    <Border x:Name="Placeholder"
      Padding="{TemplateBinding Padding}"
      Margin="2,0" Visibility="Collapsed">
      <TextBlock Text="{Binding (noesis:Text.Placeholder), RelativeSource={RelativeSource TemplatedParent}}"/>
    </Border>
    <ScrollViewer x:Name="PART_ContentHost" Focusable="False"
      Padding="{TemplateBinding Padding}"
      Foreground="{TemplateBinding Foreground}"/>
  </Grid>
  <ControlTemplate.Triggers>
    <Trigger Property="Text" Value="">
      <Setter Property="Visibility" Value="Visible" TargetName="Placeholder"/>
    </Trigger>
  </ControlTemplate.Triggers>
</ControlTemplate>
```

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
    <TextBlock Text="Enter your login credentials:"/>
    <TextBox noesis:Text.Placeholder="Username" Width="300" Margin="0,10,0,5"/>
    <PasswordBox noesis:Text.Placeholder="Password" Width="300"/>
  </StackPanel>
</Grid>
```

![ExtensionsTutorialImg2.png](https://www.noesisengine.com/docs/ExtensionsTutorialImg2.png)

## ShowLastCharacterDuration

Specifies the duration in milliseconds that the last character typed in a [PasswordBox](_PasswordBox.md) remains visible before it is converted into the corresponding *PasswordChar*.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
    <TextBlock Text="Enter your login credentials:"/>
    <TextBox noesis:Text.Placeholder="Username" Width="300" Margin="0,10,0,5"/>
    <PasswordBox noesis:Text.Placeholder="Password" noesis:Text.ShowLastCharacterDuration="1500"
                 Width="300"/>
  </StackPanel>
</Grid>
```

![ExtensionsTutorialImg6.png](https://www.noesisengine.com/docs/ExtensionsTutorialImg6.png)

## RichText

This extension adds a new attached property, [RichText.Text](../App.ApplicationLauncher/_RichText.md). It implements a very convenient way to fill the *Inlines* of a [TextBlock](_TextBlock.md) from a *DataContext*.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <TextBlock noesis:RichText.Text="Plain. [b]Bold, [i]bold italic, [/i]
    [size=60]Size 60 text.[/size] [img height=80]disk.png[/img]" />
</Grid>
```

## LocExtension

For localization purposes, this extension implements a new markup extension, [Loc](../App.ApplicationLauncher/_LocExtension.md), to localize text and other elements like images. It provides a value for any XAML property attribute by looking up a reference in a [ResourceDictionary](_ResourceDictionary.md). It can be used in combination with [RichText.Text](../App.ApplicationLauncher/_RichText.md) .

Language\_en-gb.xaml

```
<ResourceDictionary
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <ImageBrush x:Key="Flag" ImageSource="Flag_en-gb.png" Stretch="Fill"/>
  <sys:String x:Key="TitleLabel">[b]LOCALIZATION SAMPLE[/b]</sys:String>
  <sys:String x:Key="SoundLabel">A [i]sound[/i] label</sys:String>
</ResourceDictionary>
```

```
<StackPanel
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions"
  noesis:Loc.Source="Language_en-gb.xaml">
  <Image Source="{noesis:Loc Flag}"/>
  <TextBlock noesis:RichText.Text="{noesis:Loc TitleLabel}"/>
  <TextBlock noesis:RichText.Text="{noesis:Loc SoundLabel}"/>
</StackPanel>
```

# Element Extensions

## PPAA

When using Per-Primitive Antialiasing ([PPAA](AntialiasingTutorial.md#per-primitive-antialiasing)) sometimes it is useful to disable it on a specific element or group of elements. This can be done by setting attached property *Element.PPAAMode* to *Disabled*. This way you can avoid the minor overlappings on contiguous elements produced by the extruded geometry that PPAA generates. It can also be used to improve performance on elements where *PPAA* is not necessary, like aligned rectangles. This property is inherited down the UI tree.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <Grid noesis:Element.PPAAMode="Disabled">
    <Grid.ColumnDefinitions>
      <ColumnDefinition Width="55"/>
      <ColumnDefinition Width="*"/>
      <ColumnDefinition Width="8"/>
    </Grid.ColumnDefinitions>
    <Grid.RowDefinitions>
      <RowDefinition Height="25"/>
      <RowDefinition Height="*"/>
      <RowDefinition Height="32"/>
    </Grid.RowDefinitions>
    <Rectangle Grid.Row="0" Grid.Column="0" Fill="{StaticResource TopLeftImage}"/>
    <Rectangle Grid.Row="0" Grid.Column="1" Fill="{StaticResource TopImage}"/>
    <Rectangle Grid.Row="0" Grid.Column="2" Fill="{StaticResource TopRightImage}"/>
    <Rectangle Grid.Row="1" Grid.Column="0" Fill="{StaticResource CenterLeftImage}"/>
    <Rectangle Grid.Row="1" Grid.Column="1" Fill="{StaticResource CenterImage}"/>
    <Rectangle Grid.Row="1" Grid.Column="2" Fill="{StaticResource CenterRightImage}"/>
    <Rectangle Grid.Row="2" Grid.Column="0" Fill="{StaticResource BottomLeftImage}"/>
    <Rectangle Grid.Row="2" Grid.Column="1" Fill="{StaticResource BottomImage}"/>
    <Rectangle Grid.Row="2" Grid.Column="2" Fill="{StaticResource BottomRightImage}"/>
  </Grid>
</Grid>
```

![ExtensionsTutorialImg3.png](https://www.noesisengine.com/docs/ExtensionsTutorialImg3.png)

In other situations is desirable to modify the extrusion parameters of PPAA to get a better antialiasing. This can be done by setting *Element.PPAAIn* and *Element.PPAAOut* properties on the selected elements. These properties are inherited down the UI tree.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <Rectangle Fill="Black" Width="100" Height="100"
    noesis:Element.PPAAIn="1" noesis:Element.PPAAOut="1">
    <Rectangle.RenderTransform>
      <RotateTransform Angle="60"/>
    </Rectangle.RenderTransform>
  </Rectangle>
</Grid>
```

## Blending

The *Element.BlendingMode* extension allows UI element contents to mix with the background using the well known *Multiply*, *Screen* and *Additive* blend modes.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <Border Background="White" HorizontalAlignment="Center" VerticalAlignment="Center">
    <Grid Margin="20">
      <Ellipse Width="160" Height="160" Fill="Magenta" Margin="0,0,80,80" noesis:Element.BlendingMode="Multiply"/>
      <Ellipse Width="160" Height="160" Fill="Yellow" Margin="80,0,0,80" noesis:Element.BlendingMode="Multiply"/>
      <Ellipse Width="160" Height="160" Fill="Cyan" Margin="0,80,0,0" noesis:Element.BlendingMode="Multiply"/>
    </Grid>
  </Border>
</Grid>
```

![ExtensionsTutorialImg5.png](https://www.noesisengine.com/docs/ExtensionsTutorialImg5.png)

## Transform3D

NoesisGUI provides [3-D transformations](Transform3DTutorial.md) to UI elements trough the attached property *Element.Transform3D*. Two types of 3-D transform objects are available: [CompositeTransform3D](_CompositeTransform3D.md) and [MatrixTransform3D](_MatrixTransform3D.md).

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <StackPanel Orientation="Horizontal">
    <Rectangle Fill="Black" Width="100" Height="100">
      <noesis:Element.Transform3D>
        <noesis:CompositeTransform3D RotationY="30" CenterX="50"/>
      </noesis:Element.Transform3D>
    </Rectangle>
    <Rectangle Fill="Black" Width="100" Height="100">
      <noesis:Element.Transform3D>
        <noesis:MatrixTransform3D Matrix="{Binding Transform}"/>
      </noesis:Element.Transform3D>
    </Rectangle>
  </StackPanel>
</Grid>
```

![ExtensionsTutorialImg4.png](https://www.noesisengine.com/docs/ExtensionsTutorialImg4.png)

## Focus Engagement

To ensure that applications are usable and accessible through [Gamepads](SDKGuide.md#gamepad) it is necessary to handle focus on some controls in a particular way, otherwise focus could get 'trapped' within a control. [Focus engagement](https://docs.microsoft.com/en-us/windows/uwp/design/input/gamepad-and-remote-interactions#focus-engagement) tries to resolve this situation.

The attached property *Element.IsFocusEngagementEnabled* can be set on a control to enable focus engagement. By default focus engagement is enabled on the following controls: [Slider](_Slider.md), [TextBox](_TextBox.md), [PasswordBox](_PasswordBox.md), and [ComboBox](_ComboBox.md). This means that when one of those controls receives focus, user has to press 'Accept' button to activate it and interact with it, and press 'Cancel' button to exit from focus engagement. Attached property *Element.IsFocusEngaged* indicates if the control has focus engaged or not, and can be used to show a visual cue in its template to help users identify that state.

```
<ControlTemplate x:Key="TextBoxTemplate" TargetType="TextBox">
  <Grid>
    <Border Background="{TemplateBinding Background}">
      <ScrollViewer x:Name="PART_ContentHost"/>
    <Border>
    <Border x:Name="FocusBd" BorderBrush="{StaticResource FocusedBrush}"
      BorderThickness="2" Visibility="Collapsed"/>
  </Grid>
  <ControlTemplate.Triggers>
    <Trigger Property="noesis:Element.IsFocusEngaged" Value="True">
      <Setter Property="Visibility" Value="Visible" TargetName="FocusBd"/>
    </Trigger>
  </ControlTemplate.Triggers>
</ControlTemplate>
```

## XY Focus Navigation

If your app supports proper focus navigation for keyboard, this will translate well to gamepad and remote control.

However, there may be some extra work required to support every scenario. Because XY focus navigation limits the user to moving up, down, left, and right, you may end up with scenarios where parts of the UI are inaccessible.

![ExtensionsTutorialImg9.png](https://www.noesisengine.com/docs/ExtensionsTutorialImg9.png)

In that case you can override the default behavior to move the focus on a specific logical item by using the *XYFocus* extension properties:

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <StackPanel>
    <Button x:Name="MyBtnLeft" Content="Search"/>
    <Button x:Name="MyBtnRight" Content="Delete"/>
    <Button x:Name="MyBtnTop" Content="Update"/>
    <Button x:Name="MyBtnDown" Content="Undo"/>
    <Button Content="Home"
            noesis:Element.XYFocusLeft="{Binding ElementName=MyBtnLeft}"
            noesis:Element.XYFocusRight="{Binding ElementName=MyBtnRight}"
            noesis:Element.XYFocusDown="{Binding ElementName=MyBtnDown}"
            noesis:Element.XYFocusUp="{Binding ElementName=MyBtnTop}"/>
  </StackPanel>
</Grid>
```

## Gesture Events

The following [Gesture events](TouchTutorial.md#gesture-events) are taken from UWP:

- [Tapped](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.uielement.tapped)
- [DoubleTapped](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.uielement.doubletapped)
- [RightTapped](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.uielement.righttapped)
- [Holding](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.uielement.holding)

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions"
  noesis:IsRightTapEnabled="True"
  noesis:RightTapped="RootGrid_RightTapped">
</Grid>
```

# Path Extensions

## Trimming

Creating [Vector Animations](https://www.noesisengine.com/xamltoy/6acdc882e5c540f15a7857a884e06a42) usually requires to render only part of a path. This can be achieved sometimes with clipping, but not always. Path trimming is a feature that allows to specify which section of a path will be displayed. NoesisGUI defines attached properties [Path.TrimStart](https://docs.microsoft.com/es-mx/uwp/api/windows.ui.composition.compositiongeometry.trimstart?view=winrt-18362), [Path.TrimEnd](https://docs.microsoft.com/es-mx/uwp/api/windows.ui.composition.compositiongeometry.trimend?view=winrt-18362) and [Path.TrimOffset](https://docs.microsoft.com/es-mx/uwp/api/windows.ui.composition.compositiongeometry.trimoffset?view=winrt-18362) that can be set on any [Shape](_Shape.md) element for that purpose.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions"
  Background="White">
  <Grid.Resources>
    <Storyboard x:Key="anim" RepeatBehavior="Forever">
      <DoubleAnimation Storyboard.TargetName="circle"
        Storyboard.TargetProperty="(noesis:Path.TrimOffset)"
        To="1"/>
      <DoubleAnimation Storyboard.TargetName="circle"
        Storyboard.TargetProperty="(noesis:Path.TrimStart)"
        To="0.25" Duration="0:0:0.5" AutoReverse="True"/>
    </Storyboard>
  </Grid.Resources>
  <Grid.Triggers>
    <EventTrigger RoutedEvent="FrameworkElement.Loaded">
      <BeginStoryboard Storyboard="{StaticResource anim}"/>
    </EventTrigger>
  </Grid.Triggers>
  <Ellipse x:Name="circle" Width="200" Height="200"
    Stroke="Black" StrokeThickness="20" StrokeStartLineCap="Round"
    noesis:Path.TrimStart="0" noesis:Path.TrimEnd="0.5"/>
</Grid>
```

# Brush Extensions

## Shader Brush

[Shader Brushes](ShadersTutorial.md#shader-brushes) provides functionality that allows [ImageBrush](_ImageBrush.md) to be extended by using pixel shaders.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions"
  xmlns:local="clr-namespace:CustomBrushes">

  <Rectangle Width="300" Height="300">
    <Rectangle.Fill>
      <ImageBrush ImageSource="Images/image.jpg">
        <noesis:Brush.Shader>
          <local:WaveBrush Frequency="0.7" />
        </noesis:Brush.Shader>
      </ImageBrush>
    </Rectangle.Fill>
  </Rectangle>
</Grid>
```

![ShadersTutorialImg2.jpg](https://www.noesisengine.com/docs/ShadersTutorialImg2.jpg)

## BoxShadow

The [BoxShadow](../App.Shaders/_BoxShadow.md) primitive is part of the Brush Extensions suite and is designed for high-performance rendering of blurred, rounded rectangles. Internally, it uses a BrushShader to simulate both inner and outer shadows, providing visually rich shadow effects without relying on traditional effect like [DropShadowEffect](_DropShadowEffect.md).

By eliminating offscreen rendering, this primitive offers a significantly more efficient alternative to standard shadow techniques.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions"
  Background="White">
  <StackPanel Orientation="Horizontal">
    <noesis:BoxShadow Width="300" Height="200" BlurRadius="50" />
    <noesis:BoxShadow Width="300" Height="200" BlurRadius="100" />
    <noesis:BoxShadow Width="300" Height="200" BlurRadius="200" />
  </StackPanel>
</Grid>
```

![ExtensionsTutorialImg10.png](https://www.noesisengine.com/docs/ExtensionsTutorialImg10.png)

# Interactivity Extensions

## Styles

[Behaviors](../App.Interactivity/Behaviors.md) architecture allows UI designers to add functionality to the interface using only XAML. NoesisGUI implements almost all behaviors and triggers provided by Blend, but they cannot be specified within [Styles](../App.Interactivity/Behaviors.md#styles) because default [Interaction](../App.Interactivity/_Interaction.md) *Behaviors* and *Triggers* are read-only properties in WPF. To address that limitation we extended this architecture with a couple of attached properties, [StyleInteraction](../App.Interactivity/_StyleInteraction.md) *Behaviors* and *Triggers*, that can be set in a style [Setter](_Setter.md).

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
                <b:PlaySoundAction Source="buttonClick.wav"/>
              </b:EventTrigger>
            </noesis:StyleTriggerCollection>
          </Setter.Value>
        </Setter>
        <Setter Property="noesis:StyleInteraction.Behaviors">
          <Setter.Value>
            <noesis:StyleBehaviorCollection>
              <b:MouseDragElementBehavior/>
            </noesis:StyleBehaviorCollection>
          </Setter.Value>
        </Setter>
      </Style>
    </Grid.Resources>
    <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
      <Button Content="Start"/>
      <Button Content="Options"/>
      <Button Content="Exit"/>
    </StackPanel>
</Grid>
```

## Triggers

To allow users to perform actions in response to gamepad input NoesisGUI provides [GamepadTrigger](../App.Interactivity/_GamepadTrigger.md) .

```
<UserControl
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <b:Interaction.Triggers>
    <noesis:GamepadTrigger FiredOn="ButtonDown" Button="Cancel">
      <b:InvokeCommandAction Command="{Binding ExitCommand}" />
    </noesis:GamepadTrigger>
  <b:Interaction.Triggers>
</UserControl>
```

## Behaviors

When an application requires to sort a collection of items it can use NoesisGUI custom [CollectionSortBehavior](../App.Interactivity/_CollectionSortBehavior.md). If it needs to filter a collection of items then it can use the [CollectionFilterBehavior](../App.Interactivity/_CollectionFilterBehavior.md). Those behaviors can be combined by chaining the output collection of one to the *ItemsSource* input collection of the other behavior.

```
<StackPanel
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <b:Interaction.Behaviors>
    <noesis:CollectionFilterBehavior x:Name="FilterBehavior"
      ItemsSource="{Binding Books}"
      Predicate="{Binding BookFilter}" />
    <noesis:CollectionSortBehavior x:Name="SortBehavior"
      ItemsSource="{Binding FilteredItems, ElementName=FilterBehavior}"
      Comparer="{Binding BookComparer}" />
  </b:Interaction.Behaviors>
  <TextBox Text="{Binding SearchText}"/>
  <ListBox ItemsSource="{Binding SortedItems, ElementName=SortBehavior}" />
</StackPanel>
```

NoesisGUI defines a custom [LineDecorationBehavior](../App.Interactivity/_LineDecorationBehavior.md) that can be attached to any TextBlock to render extra line decorations. The behavior defines a Progress property that can be used to adjust the length of the rendered line.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=NoesisGUI.GUI.Extensions">
  <TextBlock TextWrapping="Wrap" FontSize="32" Foreground="White" Width="400"
      Text="Some long text that will be rendered with an strikethrough line">
    <b:Interaction.Behaviors>
      <noesis:LineDecorationBehavior Offset="-10" Progress="0.8">
        <noesis:LineDecorationBehavior.Pen>
          <Pen Brush="Red" Thickness="3"/>
        </noesis:LineDecorationBehavior.Pen>
      </noesis:LineDecorationBehavior>
    </b:Interaction.Behaviors>
  </TextBlock>
</Grid>
```

![ExtensionsTutorialImg7.png](https://www.noesisengine.com/docs/ExtensionsTutorialImg7.png)

In case the application requires to blur the background of a panel it can use the [BackgroundEffectBehavior](../App.Interactivity/_BackgroundEffectBehavior.md). This behavior can be attached to Panels, Borders and Shapes to render the elements beneath as background with any effect applied.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=NoesisGUI.GUI.Extensions">
  <Image x:Name="img" Source="Images/landscape.jpg" Stretch="UniformToFill"/>
  <Ellipse Width="600" Height="200">
    <b:Interaction.Behaviors>
      <noesis:BackgroundEffectBehavior Source="{Binding ElementName=img}">
        <BlurEffect Radius="20"/>
      </noesis:BackgroundEffectBehavior>
    </b:Interaction.Behaviors>
  </Ellipse>
</Grid>
```

![ExtensionsTutorialImg8.png](https://www.noesisengine.com/docs/ExtensionsTutorialImg8.png)

## Trigger Actions

When a panel gets loaded, sometimes it is necessary to set the keyboard focus on a specific control. NoesisGUI includes the [SetFocusAction](../App.Interactivity/_SetFocusAction.md) to set the focus on the targeted element in response to any interactivity trigger.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <b:Interaction.Triggers>
    <b:EventTrigger EventName="Loaded">
      <noesis:SetFocusAction TargetName="UserName"/>
    </b:EventTrigger>
  </b:Interaction.Triggers>
  <TextBox x:Name="UserName" Text="{Binding UserName}"/>
</Grid>
```

The focus can be moved in a direction instead of a specific named element. To do that NoesisGUI defines the [MoveFocusAction](../App.Interactivity/_MoveFocusAction.md).

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <b:Interaction.Triggers>
    <b:KeyTrigger Key="D">
      <noesis:MoveFocusAction Direction="Right"/>
    </b:KeyTrigger>
  </b:Interaction.Triggers>
</Grid>
```

There are situations that need selecting an item in a list when it gets hovered or any other event happens. This can be done using the [SelectAction](../App.Interactivity/_SelectAction.md), which sets the *Selector.IsSelected* property to true when the action gets execeuted.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <Grid.Resources>
    <Style TargetType="ListBoxItem" BasedOn="{StaticResource {x:Type ListBoxItem}}">
      <Setter Property="noesis:StyleInteraction.Triggers">
        <Setter.Value>
          <noesis:StyleTriggerCollection>
            <b:EventTrigger EventName="MouseEnter">
              <noesis:SelectAction />
            </b:EventTrigger>
          </noesis:StyleTriggerCollection>
        </Setter.Value>
      </Setter>
    </Style>
  </Grid.Resources>
  <ListBox ItemsSource="{Binding Books}"/>
</Grid>
```

When a [TextBox](_TextBox.md) or [PasswordBox](_PasswordBox.md) gets focus, the default behavior is to just position the caret where mouse was clicked, but sometimes it is preferable to select the whole text. To avoid creating a custom control for just that, NoesisGUI offers the [SelectAllAction](../App.Interactivity/_SelectAllAction.md).

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <TextBox Text="{Binding UserName}">
    <b:Interaction.Triggers>
      <b:EventTrigger EventName="GotKeyboardFocus">
        <noesis:SelectAllAction />
      </b:EventTrigger>
    </b:Interaction.Triggers>
  </TextBox>
</Grid>
```

# Unity Extensions

## Xaml Dependencies

In Unity only the assets that are referenced from objects included in the scene are added to the game executable and are then available to load. [NoesisXaml](Unity3DTutorial.md#xaml-assets) asset automatically detects which resources are being used (like resource dictionaries, fonts or images) but there are situations where the application requires other resources to be loaded at runtime (from code for example). For that purpose, *Xaml.Dependencies* attached property is exposed to explicitly add dependencies.

```
<UserControl
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions">

  <noesis:Xaml.Dependencies>
    <noesis:Dependency Source="Language-en.xaml"/>
    <noesis:Dependency Source="Language-fr.xaml"/>
    <noesis:Dependency Source="Language-jp.xaml"/>
  </noesis:Xaml.Dependencies>

</UserControl>
```