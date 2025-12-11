Source: https://www.noesisengine.com/docs/App.ApplicationLauncher._RichText.html

# RichText Class

## namespace [NoesisApp](../Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

Adds a *Text* attached property for [TextBlock](../Gui.Core/_TextBlock.md) which formats [BBCode](https://www.bbcode.org/reference.php) into Inlines.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
  <TextBlock noesis:RichText.Text="Plain. [b]Bold, [i]bold italic, [/i]
    [size=60]Size 60 text.[/size] [color=Red]Red text.[/color] [img height=80]disk.png[/img]
    [br/] [url='https://www.noesisengine.com/']NoesisEngine.com[/url]" />
</Grid>
```

NOTE

In Unreal, this class is implemented using Unreal-style markup syntax. More information is
available in this [Localization Tutorial](../Gui.Core/LocalizationTutorial.md#unreal-engine)

Default supported BBCode tags, with their [Inline](../Gui.Core/_Inline.md) output:

- *b*: [Bold](../Gui.Core/_Bold.md),
  "[b]bold.[/b]"
- *i*: [Italic](../Gui.Core/_Italic.md),
  "[i]italic.[/i]"
- *u*: [Underline](../Gui.Core/_Underline.md),
  "[u]underline.[/u]"
- *size*: [Span](../Gui.Core/_Span.md) with FontSize set to the parameter value,
  "[size=60]size 60 text.[/size]"
- *font*: [Span](../Gui.Core/_Span.md) with [FontFamily](../Gui.Core/_FontFamily.md) set to the parameter value,
  "[font='#PT Root UI']PT Root UI font.[/]"
- *color*: [Span](../Gui.Core/_Span.md) with Foreground set to the parameter value (a color name, or ARBG hex),
  "[color=Red]red.[/color][color=#FF0000FF]blue.[/color]"
- *url*: [Hyperlink](../Gui.Core/_Hyperlink.md) with NavigateUri set to the parameter value,
  "[url='https://www.noesisengine.com/']NoesisEngine.com[/url]"
- *br*: A [LineBreak](../Gui.Core/_LineBreak.md),
  "Line one.[br/]Line two."
- *img*: [Image](../Gui.Core/_Image.md) contained in an [InlineUIContainer](../Gui.Core/_InlineUIContainer.md),
  "[img height=80]disk.png[/img]"
- *style*: [Span](../Gui.Core/_Span.md) with the [Style](../Gui.Core/_Style.md) property set to the resource key provided by the parameter value,
  "[style='Header1']Styled text.[/style]"

> ```
> <Grid
>   xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
>   xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
>   <Grid.Resources>
>     <Style x:Key="Header1" TargetType="{x:Type Span}">
>       <Setter Property="FontSize" Value="30"/>
>       <Setter Property="Foreground" Value="Green"/>
>     </Style>
>   </Grid.Resources>
>   <TextBlock noesis:RichText.Text="[style='Header1']Styled text.[/style]" />
> </Grid>
> ```

- *bind*: [Run](../Gui.Core/_Run.md) containing a [Binding](../Gui.Core/_Binding.md) with the [Path](../Gui.Core/_Path.md) property set to the tag contents. This tag
  has an optional "format" parameter which can be used to modify the StringFormat property
  of the Binding,
  "[bind format='{0:0}']Path[/bind]"

> ```
> <Grid
>   xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
>   xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions"
>   xmlns:local="clr-namespace:MyGame">
>   <Grid.DataContext>
>     <local:MyViewModel CurrentHealth="66.75" MaxHealth="100" />
>   </Grid.DataContext>
>   <TextBlock noesis:RichText.Text="Health is [bind format='{0:0}']CurrentHealth[/bind] out of
>     [bind format='{0:0}']MaxHealth[/bind]" />
> </Grid>
> ```

# Inheritance Hierarchy

• *RichText*

# Properties

RichText has no properties

# Attached Properties

| Name | Description |
| --- | --- |
| ● *Text* | Gets or sets the value of an element's [RichText](_RichText.md) Text property |

# Methods

RichText has no methods

# Events

RichText has no events