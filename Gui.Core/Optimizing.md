Source: https://www.noesisengine.com/docs/Gui.Core.Optimizing.html

# Optimizing NoesisGUI Performance

This section is intended as a reference guide for ways to improve the performance of NoesisGUI.

# Rendering Performance

Note

![Optimizing1.png](https://www.noesisengine.com/docs/Optimizing1.png)

For optimizing graphics performance [XamlPlayer](FirstSteps.md) has a Statistics panel that can be toggled on with CTRL + F. This information is also available programmatically in the IView interface.

## Antialiasing

NoesisGUI implements a very fast antialiasing algorithm that can be used instead of GPU full-scene antialiasing. To use it you have to activate the PPAA (per-primitive algorithm) algorithm in the view. PPAA implements antialiasing by extruding the contours of the triangles smoothing them. The paths are slightly altered though.

Although it depends on the hardware, *PPAA* is normally a lot faster than GPU MSAA. We recommend using it whenever possible. Our [application framework](ApplicationTutorial.md) enables *PPAA* by default.

## Opacity Groups

Whenever possible element's *Opacity* property must be avoided because it can cause the use of offscreen surfaces. The number of offscreen surfaces used is indicated in the stats panel by the counter *SetRT*.

For example, in the following XAML:

```
<StackPanel xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            Background="Aqua" Width="500" Height="500">

    <Rectangle Fill="#FFFF0000" Width="100" Height="100" Opacity="0.50"/>
    <Rectangle Fill="#80FF0000" Width="100" Height="100"/>

</StackPanel>
```

Although the aspect of both rectangles is the same, the first one is being rendered to an offscreen texture and later being copied to the main surface. It is very important not using this kind of opacity when there is only a single node (like in this example). In these cases is better transferring the alpha to the brush, like shown in the second example. We could detect and optimize this case in the future but it is better not relying on it.

When you use a [Brush](_Brush.md) to set the *Fill* or *Stroke* of an element, it is better to set the *Brush.Opacity* value rather than the setting the element's *Opacity* property.

Tip

> In XamlPlayer, the Overdraw debug mode (CTRL + O) displays opacities in red color.

## Batching

As a general rule, the minimal number of paths must be used. If you can collapse several paths in the same one, it will improve render performance because the number of drawcalls (batches) sent to the GPU is minimized. Do this whenever your content allows it. Even if you don't do it, NoesisGUI is able to optimize the number of batches by following these rules:

- **Solid color** brushes always batch together. Solid brushes are the fastest ones. Use it whenever possible.
- **Linear** brushes also batch together. The corresponding shader is a bit more complex than the one for solid colors. If possible switch linear gradients to solid colors.
- **Radial** gradients only batch when using the same parameters (radius and focus). Minimize the number of radial gradients whenever possible.
- **Image** brushes batch when images are located in the same texture (atlas).

The statistics panel display the percentage of triangles for each kind of brush. You can also activate the *Batching Debug Mode* (CTRL + B) in XamlPlayer to display each batch with a different color.

## Share Resources

Use [dictionaries](_ResourceDictionary.md) to share resources whenever possible. This is key to reducing memory usage but it is also important to increase rendering performance because it allow us to improve batching. Using resources in [Blend](BlendTutorial.md) is very easy, you only have to click on the white dot of the resource and select "Convert to New Resource...".

```
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <Grid.Resources>
    <GradientStopCollection x:Key="grad">
      <GradientStop Offset="0" Color="Red"/>
      <GradientStop Offset="1" Color="Yellow"/>
    </GradientStopCollection>
  </Grid.Resources>

  <StackPanel>
    <Rectangle Width="200" Height="100" Margin="10">
      <Rectangle.Fill>
        <LinearGradientBrush StartPoint="0,0" EndPoint="0,1"
          GradientStops="{StaticResource grad}"/>
      </Rectangle.Fill>
    </Rectangle>
    <Rectangle Width="200" Height="100" Margin="10">
      <Rectangle.Fill>
        <LinearGradientBrush StartPoint="0,0" EndPoint="1,0"
          GradientStops="{StaticResource grad}"/>
      </Rectangle.Fill>
    </Rectangle>
  </StackPanel>
</Grid>
```

# Loading times

Using several resource dictionaries to organize styles and resources is a good practice. But keep in mind that every time you reference a resource dictionary in a XAML, that dictionary is loaded and all its resources created again. Therefore, as described in the [styling](StylingTutorial.md) guide, it is recommended to include those dictionaries, if they are used along your whole application, in the global dictionary, so they are loaded only once and are always accessible.