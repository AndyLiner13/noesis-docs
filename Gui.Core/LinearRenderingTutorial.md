Source: https://www.noesisengine.com/docs/Gui.Core.LinearRenderingTutorial.html

# Linear Rendering

In linear rendering mode, calculations are performed in a way that is physically and mathematically correct. This means that colors in textures and render targets, which are typically encoded in sRGB space, are converted to linear space before performing operations such as blending and interpolation. After the calculations are performed, the results are converted back to sRGB space so that they can be displayed on a monitor or other output device.

Linear rendering helps to ensure that the resulting colors are more accurate and consistent with how colors would appear in the real world. More information about this topic can be found in the following articles:

- [What every coder should know about gamma](https://blog.johnnovak.net/2016/09/21/what-every-coder-should-know-about-gamma/)
- [The Importance of Being Linear](https://developer.nvidia.com/gpugems/gpugems3/part-iv-image-effects/chapter-24-importance-being-linear)

# Enabling Linear Mode

By default, NoesisGUI renderers do not operate in linear space. However, many of our reference render devices can be configured to operate in linear mode during construction. For example:

```
ID3D11DeviceContext* context = GetActiveDeviceContext();
Ptr<RenderDevice> renderer = MakePtr<D3D11RenderDevice>(context, true /* Linear Rendering */);
```

Note

In Unity, linear rendering can be enabled in 'Player => Rendering => Color Space'

When linear mode is enabled, shaders expect inputs and outputs in linear space by using [sRGB colorspace](https://www.khronos.org/opengl/wiki/Image_Format#sRGB_colorspace) textures. If you are creating your own textures, make sure to use these formats.

Using linear rendering has significant implications for the final output. By accurately representing colors in a more physically and mathematically correct way, the resulting images will appear more realistic and consistent with how they would look in the real world. However, it is important to note that to achieve these benefits, artists and designers must adjust their values and techniques for proper rendering in linear space. This adjustment is necessary because the way colors and opacity are perceived and blended is different in linear space compared to non-linear spaces like sRGB.

# Alpha blending

In linear mode, opacity values are no longer perceived in a linear manner. This means that setting opacity to 50% no longer results in an output that is half as bright as when opacity is set to 100%. In linear space, the values are perceived linearly in terms of emitted light intensity (before gamma conversion). For example:

![LinearRenderingTutorialImg0.png](https://www.noesisengine.com/docs/LinearRenderingTutorialImg0.png)

[RUN ▶](https://www.noesisengine.com/xamltoy/5beb5353f136b7564f7ab15d0c5f99e0)

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  Background="White">

  <StackPanel Orientation="Horizontal">
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="1.00"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.95"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.90"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.85"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.80"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.75"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.70"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.65"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.60"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.55"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.50"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.45"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.40"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.35"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.30"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.25"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.20"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.15"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.10"/>
    <Rectangle Width="30" Height="100" Fill="Black" Opacity="0.05"/>
  </StackPanel>
</Grid>
```

This has important implications for alpha blending. In the following example, a few coloured rectangles are mixed together using opacity. The image on the left mimics more closely how light would behave in real life while the non-linear one on the right exhibits some weird hue and brightness shifts.

![LinearRenderingTutorialImg1.png](https://www.noesisengine.com/docs/LinearRenderingTutorialImg1.png)

[RUN ▶](https://www.noesisengine.com/xamltoy/af45aead41a28905d1c54b51e2e96a47)

```
<Canvas
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  Background="White">

  <Canvas Margin="10">
    <Rectangle Canvas.Left="80" Width="80" Height="350" Fill="#18EA22" />
    <Rectangle Canvas.Left="180" Width="80" Height="350" Fill="#EAE818" />
    <Rectangle Canvas.Left="280" Width="80" Height="350" Fill="#18EAC8" />
    <Rectangle Canvas.Left="380" Width="80" Height="350" Fill="#EE46A6" />

    <Rectangle Canvas.Top="50" Width="540" Height="25" Fill="#FF0000" />
    <Rectangle Canvas.Top="75" Width="540" Height="25" Fill="#7FFF0000" />

    <Rectangle Canvas.Top="150" Width="540" Height="25" Fill="#007FFF" />
    <Rectangle Canvas.Top="175" Width="540" Height="25" Fill="#7F007FFF" />

    <Rectangle Canvas.Top="250" Width="540" Height="25" Fill="#93FF00" />
    <Rectangle Canvas.Top="275" Width="540" Height="25" Fill="#7F93FF00" />
  </Canvas>
</Canvas>
```

# Gradients

In Noesis, to prevent significant changes in the output when linear mode is enabled, gradients are still interpolated in sRGB space instead of linear space. To enable linear interpolation, the property *ColorInterpolationMode* must be set to *ScRgbLinearInterpolation*. In the following XAML, for each gradient-pair, the top gradient is a linear interpolation between two colors in linear space, then the result is converted to sRGB. The bottom gradients are the results of interpolating between the exact same colors but directly in sRGB space.

![LinearRenderingTutorialImg2.png](https://www.noesisengine.com/docs/LinearRenderingTutorialImg2.png)

[RUN ▶](https://www.noesisengine.com/xamltoy/7763efa2d3333f9653679a3f019302db)

```
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  Background="White">

  <StackPanel>
    <StackPanel Margin="10">
      <Rectangle Width="600" Height="30">
        <Rectangle.Fill>
          <LinearGradientBrush EndPoint="1,0" ColorInterpolationMode="ScRgbLinearInterpolation">
            <GradientStop Color="#FF0000" Offset="0.0" />
            <GradientStop Color="#00FF00" Offset="1.0" />
          </LinearGradientBrush>
        </Rectangle.Fill>
      </Rectangle>
      <Rectangle Width="600" Height="30">
        <Rectangle.Fill>
          <LinearGradientBrush EndPoint="1,0">
            <GradientStop Color="#FF0000" Offset="0.0" />
            <GradientStop Color="#00FF00" Offset="1.0" />
          </LinearGradientBrush>
        </Rectangle.Fill>
      </Rectangle>
    </StackPanel>
    <StackPanel Margin="10">
      <Rectangle Width="600" Height="30">
        <Rectangle.Fill>
          <LinearGradientBrush EndPoint="1,0" ColorInterpolationMode="ScRgbLinearInterpolation">
            <GradientStop Color="#00FF00" Offset="0.0" />
            <GradientStop Color="#0000FF" Offset="1.0" />
          </LinearGradientBrush>
        </Rectangle.Fill>
      </Rectangle>
      <Rectangle Width="600" Height="30">
        <Rectangle.Fill>
          <LinearGradientBrush EndPoint="1,0">
            <GradientStop Color="#00FF00" Offset="0.0" />
            <GradientStop Color="#0000FF" Offset="1.0" />
          </LinearGradientBrush>
        </Rectangle.Fill>
      </Rectangle>
    </StackPanel>
    <StackPanel Margin="10">
      <Rectangle Width="600" Height="30">
        <Rectangle.Fill>
          <LinearGradientBrush EndPoint="1,0" ColorInterpolationMode="ScRgbLinearInterpolation">
            <GradientStop Color="#0000FF" Offset="0.0" />
            <GradientStop Color="#FF0000" Offset="1.0" />
          </LinearGradientBrush>
        </Rectangle.Fill>
      </Rectangle>
      <Rectangle Width="600" Height="30">
        <Rectangle.Fill>
          <LinearGradientBrush EndPoint="1,0">
            <GradientStop Color="#0000FF" Offset="0.0" />
            <GradientStop Color="#FF0000" Offset="1.0" />
          </LinearGradientBrush>
        </Rectangle.Fill>
      </Rectangle>
    </StackPanel>
    <StackPanel Margin="10">
      <Rectangle Width="600" Height="30">
        <Rectangle.Fill>
          <LinearGradientBrush EndPoint="1,0" ColorInterpolationMode="ScRgbLinearInterpolation">
            <GradientStop Color="#FF00FF" Offset="0.0" />
            <GradientStop Color="#FFFF00" Offset="1.0" />
          </LinearGradientBrush>
        </Rectangle.Fill>
      </Rectangle>
      <Rectangle Width="600" Height="30">
        <Rectangle.Fill>
          <LinearGradientBrush EndPoint="1,0">
            <GradientStop Color="#FF00FF" Offset="0.0" />
            <GradientStop Color="#FFFF00" Offset="1.0" />
          </LinearGradientBrush>
        </Rectangle.Fill>
      </Rectangle>
    </StackPanel>
    <StackPanel Margin="10">
      <Rectangle Width="600" Height="30">
        <Rectangle.Fill>
          <LinearGradientBrush EndPoint="1,0" ColorInterpolationMode="ScRgbLinearInterpolation">
            <GradientStop Color="#FFFF00" Offset="0.0" />
            <GradientStop Color="#00FFFF" Offset="1.0" />
          </LinearGradientBrush>
        </Rectangle.Fill>
      </Rectangle>
      <Rectangle Width="600" Height="30">
        <Rectangle.Fill>
          <LinearGradientBrush EndPoint="1,0">
            <GradientStop Color="#FFFF00" Offset="0.0" />
            <GradientStop Color="#00FFFF" Offset="1.0" />
          </LinearGradientBrush>
        </Rectangle.Fill>
      </Rectangle>
    </StackPanel>
  </StackPanel>
</Grid>
```