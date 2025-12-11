Source: https://www.noesisengine.com/docs/Gui.Core.AntialiasingTutorial.html

# UI Antialiasing

NoesisGUI offers two methods to reduce aliasing and produce smoother user interfaces. Aliasing is a visual artifact where lines appear jagged or exhibit a "staircase" effect. This typically occurs when the graphics output device lacks sufficient resolution to render perfectly straight lines.

*Antialiasing* mitigates this effect by blending the edges of lines with intermediate colors. While this softens jagged edges, it can also make lines appear slightly blurrier.

![AntialiasingTutorial1.png](https://www.noesisengine.com/docs/AntialiasingTutorial1.png)

NoesisGUI supports the following antialiasing algorithms:

- GPU Multisample Antialiasing (MSAA)
- Per Primitive Antialiasing (PPAA)

# Multisample Antialiasing

MSAA is the default antialiasing mode implemented by the GPU. Most modern GPUs support this technique.

In multisample antialiasing, each pixel along the edge of a polygon is sampled multiple times. For each sample, a slight sub-pixel offset is applied to the screen coordinates, smaller than the pixel size itself. By averaging these samples, the result is a smoother transition of colors along the edges, reducing jaggedness.

Noesis Views always render content in the active render target. Simply binding a render target with MSAA enabled will render the UI with antialiasing.

Our [Application Framework](ApplicationTutorial.md) supports enabling MSAA via the command line switch *'--samples N'*.

If you want MSAA enabled for offscreen render targets as well, you must specify the number of samples *before initializing* each *View* in the render thread. See [Rendering Tutorial](RenderingTutorial.md#render-thread) for details.

```
Ptr<GLRenderDevice> device = *new GLRenderDevice();
device->SetOffscreenSampleCount(8);
view->GetRenderer()->Init(device);
```

Note

We recommend enabling MSAA for offscreen render targets only on high-end devices. MSAA requires render targets to be uncompressed and resolved every frame, which are performance-intensive operations.

## Pros

- MSAA provides better quality compared to PPAA.
- Does not require alpha blending.
- Tile-based architectures can implement MSAA very efficiently, without significant memory usage.

## Cons

- MSAA demands significant memory bandwidth and hardware resources.
- If your app does not use MSAA globally, you must enable it specifically for the UI.

# Per-Primitive Antialiasing

In cases where MSAA cannot be used or is too expensive, Noesis provides a lightweight alternative by extruding the contours of geometry and smoothing them using alpha blending.

PPAA can be enabled for a view by setting the *'RenderFlags\_PPAA'* flag:

```
view->SetFlags(Noesis::RenderFlags_PPAA);
```

This is the default mode used by our [Application Framework](ApplicationTutorial.md).

Enabling this flag activates PPAA globally for the view. However, PPAA can also be selectively disabled on individual nodes by using the extended XAML property *PPAAMode*. Since PPAA generates extra geometry, it is recommended to disable it where it is not necessary, for example, on a rectangle that is never rotated, to save bandwidth.

Two additional extended XAML properties control how the extrusion is performed: *PPAAIn* and *PPAAOut*.

- *PPAAIn* specifies how many pixels the geometry is shrunk inward.
- *PPAAOut* specifies how many pixels vertices are extruded outward.

The region between *PPAAIn* and *PPAAOut* is where alpha transitions from 1.0 to 0.0. The default values are conservative to prevent visual artifacts, but they can be increased depending on the geometry to improve antialiasing quality.

*PPAAMode*, *PPAAIn*, and *PPAAOut* are inherited properties that propagate down the visual tree. However, setting *PPAAMode* to 'Disabled' on the View's *Content* element will not disable PPAA for *Popups* and *ToolTips*, as these elements are rendered on a separate visual layer and are not children of the *Content* element.

Note

Mathematically correct values are *'PPAAIn=0.5'* and *'PPAAOut=0.5'*. Noesis uses more conservative defaults, *'PPAAIn=0.25'* and *'PPAAOut=0.5'*, to avoid glitches that can occur when shrinking the geometry.

Although any non-zero *PPAAIn* value can improve edge smoothing, it may also introduce artifacts. Since *PPAAIn* shrinks the geometry inward, it can cause overlaps, especially when using opaque fills, resulting in visible glitches. If this happens, you can disable the shrinking by setting *''noesis:Element.PPAAIn="0"'* on the affected node.

To increase the quality of antialiasing, consider the following options:

- *'PPAAIn=0.5'*, *'PPAAOut=0.5'*: Mathematically correct and usually effective.
- *'PPAAIn=0.0'*, *'PPAAOut=1.0'*: Maximizes the blended area for stronger antialiasing, at the cost of slightly more overdraw.
- *'PPAAIn=0.25'*, *'PPAAOut=0.75'* (or similar): A balanced compromise between quality and overdraw.

Always test different configurations with your specific geometry to avoid visual artifacts.

![AntialiasingTutorial2.png](https://www.noesisengine.com/docs/AntialiasingTutorial2.png)

```
<Canvas
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions"
  Background="White">

  <StackPanel Orientation="Horizontal">
    <Rectangle noesis:Element.PPAAMode="Disabled" Fill="Black" Width="100" Height="100">
      <Rectangle.RenderTransform>
        <TransformGroup>
          <RotateTransform Angle="60"/>
          <TranslateTransform X="100" Y="10"/>
        </TransformGroup>
      </Rectangle.RenderTransform>
    </Rectangle>
    <Rectangle noesis:Element.PPAAMode="Default" Fill="Black" Width="100" Height="100">
      <Rectangle.RenderTransform>
        <TransformGroup>
          <RotateTransform Angle="60"/>
          <TranslateTransform X="150" Y="10"/>
        </TransformGroup>
      </Rectangle.RenderTransform>
    </Rectangle>
    <Rectangle noesis:Element.PPAAIn="1" noesis:Element.PPAAOut="1" Fill="Black" Width="100" Height="100">
      <Rectangle.RenderTransform>
        <TransformGroup>
          <RotateTransform Angle="60"/>
          <TranslateTransform X="200" Y="10"/>
        </TransformGroup>
      </Rectangle.RenderTransform>
    </Rectangle>
  </StackPanel>
</Canvas>
```

## Pros

- Performance is roughly equivalent to 2x MSAA or less.
- Quality is comparable to 4x to 8x MSAA.
- Can be tweaked per element tree to achieve higher quality.

## Cons

- Geometries are slightly altered; UI should be designed with PPAA in mind.
- Requires alpha blending, which can reduce performance on tile-based architectures that optimize opaque pixel overdraw.
- Generates many extra thin triangles.
- Poor quality when using [3D UI](Transform3DTutorial.md). In such cases, we recommend using MSAA.