Source: https://www.noesisengine.com/docs/Gui.Core.Transform3DTutorial.html

# 3D Transforms

In NoesisGUI, UI elements are not limited to flat, two-dimensional layouts. You can manipulate them in three dimensions by rotating, scaling, and translating them just like objects in a 3D engine. A perspective projection applied at the root of the scene gives the interface depth, making distant elements appear smaller and providing a more immersive and dynamic visual experience.

# Element Transforms

In NoesisGUI, 3D effects are achieved using the *Transform3D* property. This property applies a 3D transformation matrix to a XAML element, allowing two-dimensional UI elements to appear in three-dimensional space relative to the viewer. *Transform3D* behaves like *RenderTransform*, but operates in three dimensions instead of just two.

There are two subclasses of [Transform3D](/Gui.Core/_Transform3D.md) that can be assigned to the *Transform3D* property:

- [CompositeTransform3D](/Gui.Core/_CompositeTransform3D.md)
- [MatrixTransform3D](/Gui.Core/_MatrixTransform3D.md)

Both represent a group of affine 3D transforms that can be used to position elements in 3D space. *CompositeTransform3D* provides 3D scale, rotation, and translation transforms, while *MatrixTransform3D* exposes the full transformation matrix. *MatrixTransform3D* is especially convenient for [binding](/Gui.Core/DataBindingTutorial.md) transformations to properties of the *Model*.

NOTE

Although these properties are not part of WPF, NoesisGUI implements them as an [extension](/Gui.Core/ExtensionsTutorial.md#transform3d) in the 'noesis' namespace.

Here is an example of *CompositeTransform3D* to achieve a 3D effect in the UI:

[RUN ▶](https://www.noesisengine.com/xamltoy/8d97a6c7bab94b0a5ed260b2a3dc46eb)Transform3D.xaml

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">

  <StackPanel Orientation="Horizontal">
    <Rectangle Width="300" Height="200" Fill="CornflowerBlue" />
    <Rectangle Width="300" Height="200" Fill="CadetBlue" Margin="10">
      <noesis:Element.Transform3D>
        <noesis:CompositeTransform3D RotationY="-30" TranslateZ="-75" CenterX="150" />
      </noesis:Element.Transform3D>
    </Rectangle>
    <Rectangle Width="300" Height="200" Fill="OrangeRed">
      <noesis:Element.Transform3D>
        <noesis:CompositeTransform3D TranslateZ="-150" />
      </noesis:Element.Transform3D>
    </Rectangle>
  </StackPanel>

</Grid>
```

![Transform3DTutorialImg1.png](/Transform3DTutorialImg1/png.md)

NOTE

Transform3D does not affect the order in which elements are drawn. Elements further away from the viewer along the Z-axis might still be rendered above elements that are closer. 'Canvas.ZIndex' attached property and the position of elements in the XAML visual tree can be used in this case to manage the drawing order of elements in your UI.

# View Projection

Views by default apply a perspective transform to the root element to provide a common viewport for all the elements. Under this perspective transform, elements further away from the user appear to shrink towards a common vanishing point. This effect preserves coordinates in the Z=0 plane, where UI elements reside by default.

To change this default projection matrix, *SetProjectionMatrix* is exposed as part of the *IView* interface. Being 'width' and 'height' the dimensions of the view, the projection matrix converts to a homogeneous clip space limited by [0, width] in the x-direction and [0, height] in y-direction. The limits of the z-direction are 0 for the front plane and 1 for the back plane. To seamlessly inter-mix UI elements with other 3D game objects the same projection matrix must be used for the UI and for the 3D world.

The following table compares the clip space used by OpenGL and D3D in comparison with NoesisGUI. Take this into account when adapting projection matrices from other similar systems.

| System | X Range | Y Range | Z Range |
| --- | --- | --- | --- |
| **OpenGL** | [-1...+1] | [-1...+1] | [-1...+1] |
| **Direct3D** | [-1...+1] | [-1...+1] | [0...1] |
| **NoesisGUI** | [0...width] | [0...height] | [0...1] |

# Stereo Rendering in VR

When rendering UI in Virtual Reality, each eye requires a slightly different perspective to create the stereoscopic 3D effect. NoesisGUI supports two main approaches for stereo rendering:

1. **Multi-Pass Stereo:** Each eye is rendered separately. This method is straightforward and allows fine-grained control per eye, but it requires traversing and rendering the visual tree twice.
2. **Single-Pass Stereo:** Both eyes are rendered simultaneously. This approach is more efficient because the visual tree is traversed and culled only once, sharing most of the workload between the eyes.

The sections below describe how to implement each approach, including how to manage projection matrices and offscreen rendering of UI elements.

## Multi-Pass stereo

NoesisGUI allows setting the projection matrix separately for each eye when rendering in Virtual Reality. In VR, each eye requires a different perspective. However, note that culling is still performed using the projection matrix set in the *View*. This projection must fully encompass the frustums of both eyes to ensure correct visibility.

```
// Set a projection for culling that fully encompasses both eye frustums
uiView->SetProjectionMatrix(projection);

// UI Offscreen texture for both eyes
uiView->GetRenderer()->RenderOffscreen();

// Render Scene and UI to each eye buffer
for (int eye = 0; eye < 2; ++eye)
{
   // Clear and set up render target
   DIRECTX.SetAndClearRenderTarget(color, depth);
   DIRECTX.SetViewport(eyeX, eyeY, eyeWidth, eyeHeight);

   // Render 3D scene
   roomScene->Render(&prod, 1, 1, 1, 1, true);

   // Render UI with the eye-specific projection matrix
   uiView->GetRenderer()->RenderStereo(eyeMtx);

   // Commit rendering to the swap chain
   pEyeRenderTexture[eye]->Commit();
}
```

NOTE

We provide an [example](https://github.com/Noesis/Tutorials/tree/master/Samples/OculusVR) using OculusSDK as part of our C++ SDK.

## Single-Pass Stereo

Single-Pass Stereo renders both eyes simultaneously instead of separately. This approach is more efficient for the CPU because both eyes share the work of traversing and culling the visual tree.

```
// Set a projection for culling that fully encompasses both eye frustums
const Matrix4& projection = GetCullingMatrix();
uiView->SetProjectionMatrix(projection);

// Retrieve projection matrices
const Matrix4& leftEyeProjection = GetLeftEyeMatrix();
const Matrix4& rightEyeProjection = GetRightEyeMatrix();

/// Render UI to offscreen textures for both eyes
uiView->GetRenderer()->RenderOffscreen();

// Render the 3D scene using Single-Pass Stereo
roomScene->Render(projection, leftEyeProjection, rightEyeProjection);

// Render UI with both eye projections
uiView->GetRenderer()->RenderStereo(leftEyeProjection, rightEyeProjection);
```