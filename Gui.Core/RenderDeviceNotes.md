Source: https://www.noesisengine.com/docs/Gui.Core.RenderDeviceNotes.html

# RenderDevice API

The following sections describe the changes in the API of RenderDevice for each version of NoesisGUI. If you are implementing your own renderer these notes will help you to easily transition to new versions of NoesisGUI.

Many of the changes are straightforward and can be discovered by doing source code diffs between the current version and the new one. Our reference renderers include source code. For its simplicity we recommend using *D3D11RenderDevice* or *MTLRenderDevice* for this purpose.

# NoesisGUI 3.2

- In 3.2.9, UpdateTexture() is guaranteed to never be called during a render pass. A new method, EndUpdatingTextures(), has been added to explicitly mark the end of dynamic texture updates before starting the next render pass.
- Removing BeginTile() and EndTile() in NoesisGUI 3.1 was not a good idea for tile-based GPU architectures. We added them back, but in comparison with NoesisGUI 3.0, these functions must be used only to enable scissoring or more specific optimizations like when using QCOM\_tiled\_rendering. These functions must not clear the rectangle area, this is still done by quads sent to *DrawBatch*. Please, see our reference implementations.

> ```
> void GLRenderDevice::BeginTile(RenderTarget* surface, const Tile& tile)
> {
>   #if GL_QCOM_tiled_rendering
>     if (IsSupported(Extension::QCOM_tiled_rendering))
>     {
>         V(glStartTilingQCOM(tile.x, tile.y, tile.width, tile.height, 0));
>     }
>   #endif
>
>     // On Mali devices, the scissor for each drawcall tells the driver which tiles must be stored
>     // Qualcomm devices ignore the scissor but have "GL_QCOM_tiled_rendering" for the same purpose
>     V(glScissor(tile.x, tile.y, tile.width, tile.height));
> }
>
> void GLRenderDevice::EndTile(RenderTarget* surface)
> {
>   #if GL_QCOM_tiled_rendering
>     if (IsSupported(Extension::QCOM_tiled_rendering))
>     {
>         V(glEndTilingQCOM(GL_COLOR_BUFFER_BIT0_QCOM));
>     }
>   #endif
> }
> ```

- In NoesisGUI 3.1 our reference implementations were expecting the active viewport to be set before rendering. Now, the scissoring rectangle must also be set or disabled before rendering. In D3D11, where there is no API for disabling the scissoring because it is part of the rasterizer state object, we added the following functions:

> ```
> class D3D11RenderDevice final: public Noesis::RenderDevice
> {
>     // Enables the hardware scissor rectangle
>     void EnableScissorRec();
>
>     // Disables the hardware scissor rectangle
>     void DisableScissorRect();
> ```

- New flags added to *DeviceCaps*:

> - DeviceCaps.depthRangeZeroToOne indicates whether the device clip space depth values range from 0 to 1.
> - DeviceCaps.clipSpaceYInverted enabled when the device clip space Y values are inverted (increase from top (-1) to bottom (1)).

- New stencil modes with depth testing added:

> | Stencil Mode | Stencil | Stencil Func | Stencil Pass | Depth | Depth Func |
> | --- | --- | --- | --- | --- | --- |
> | Disabled\_ZTest | Disabled |  |  | Enabled | GREATER\_EQUAL (\*) |
> | Equal\_Keep\_ZTest | Enabled | FUNC\_EQUAL | OP\_KEEP | Enabled | GREATER\_EQUAL (\*) |
>
> (\*) GREATER\_EQUAL is used for Reverse Z, otherwise LESS\_EQUAL must be used.

- New member Batch.singlePassStereo indicating if Single Pass Stereo is enabled and two projection matrices are sent to the vertex shader.

# NoesisGUI 3.1

- A new parameter, *'needsStencil'*, was added to CreateRenderTarget() to indicate if stencil must be created or not.
- BeginRender(bool offscreen) was removed and substituted by BeginOffscreenRender() and BeginOnscreenRender().
- EndRender() removed and substituted by EndOffscreenRender() and EndOnscreenRender().
- BeginTile() and EndTile() functions were removed. The main purpose of these functions was clearing a rectangle area of the render target with a transparent color (#000000). We have simplified and optimized this part by sending these rectangles with the rest of primitives using *DrawBatch*. There is a new shader for this purpose: Shader::Clear and a new stencil mode: StencilMode::Clear.
- Texture base class has a new virtual method: HasAlpha(). It must return true if the texture has an alpha channel that is not completely white. This is just a hint to optimize rendering as alpha blending can be disabled when this function returns false. A new texture format has also been added (TextureFormat::RGBX8) to indicate a 32 bits RGBA texture with unused alpha channel.
- New vertex attributes: Rect, Tile and ImagePos. The attribute Tex2 has been removed. The documentation for each attribute and shaders has been improved in RenderDevice.h.

> | Attr | Format | Bytes | Interpolation | Semantic |
> | --- | --- | --- | --- | --- |
> | Pos | R32G32\_FLOAT | 8 | linear | Position (xy) |
> | Color | R8G8B8A8\_UNORM | 4 | nointerpolation | Color (rgba) |
> | Tex0 | R32G32\_FLOAT | 8 | linear | TexCoord0 (uv) |
> | Tex1 | R32G32\_FLOAT | 8 | linear | TexCoord1 (uv) |
> | Coverage | R32\_FLOAT | 4 | linear | Coverage (alpha) |
> | Rect | R16G16B16A16\_UNORM | 8 | nointerpolation | Rect (x0, y0, x1, y1) |
> | Tile | R32G32B32A32\_FLOAT | 16 | nointerpolation | Rect (x, y, width, height) |
> | ImagePos | R32G32B32A32\_FLOAT | 16 | linear | Position (xy) - Scale(zw) |

- Vertex attribute Color is now always passed in sRGB format (R8G8B8A8). If the device is working in linear mode (DeviceCaps.linearRendering is true) then the vertex shader is in charge of doing the conversion to linear space. See the function *SRGBToLinear()* in our reference shaders.
- The number of vertex shaders has been increased from 11 to 21. They use the same definitions as before.

> | Index | Vertex Shader | Vertex Format |
> | --- | --- | --- |
> | #00 | Pos | #00 |
> | #01 | PosColor | #01 |
> | #02 | PosTex0 | #02 |
> | #03 | PosTex0Rect | #03 |
> | #04 | PosTex0RectTile | #04 |
> | #05 | PosColorCoverage | #05 |
> | #06 | PosTex0Coverage | #06 |
> | #07 | PosTex0CoverageRect | #07 |
> | #08 | PosTex0CoverageRectTile | #08 |
> | #09 | PosColorTex1\_SDF | #09 |
> | #10 | PosTex0Tex1\_SDF | #10 |
> | #11 | PosTex0Tex1Rect\_SDF | #11 |
> | #12 | PosTex0Tex1RectTile\_SDF | #12 |
> | #13 | PosColorTex1 | #09 |
> | #14 | PosTex0Tex1 | #10 |
> | #15 | PosTex0Tex1Rect | #11 |
> | #16 | PosTex0Tex1RectTile | #12 |
> | #17 | PosColorTex0Tex1 | #13 |
> | #18 | PosTex0Tex1\_Downsample | #10 |
> | #19 | PosColorTex1Rect | #14 |
> | #20 | PosColorTex0RectImagePos | #15 |

- New pixel shaders. Blur and Shadow are now single pass and use the result of a gaussian pass performed with Downsample and Upsample shaders. We also added Pattern\_\* variants that clamp in the pixel shader.

> | Pixel Shader | Vertex Shader | Notes |
> | --- | --- | --- |
> | RGBA | #00 | Shader for debug modes |
> | Mask | #00 | Stencil only with null pixel shader |
> | Clear | #00 | Shader used for clearing render target |
> | Path\_Solid | #01 | Shaders for rendering geometry |
> | Path\_Linear | #02 |
> | Path\_Radial | #02 |
> | Path\_Pattern | #02 |
> | Path\_Pattern\_Clamp | #03 |
> | Path\_Pattern\_Repeat | #04 |
> | Path\_Pattern\_MirrorU | #04 |
> | Path\_Pattern\_MirrorV | #04 |
> | Path\_Pattern\_Mirror | #04 |
> | Path\_AA\_Solid | #05 | Shaders for rendering geometry with PPAA |
> | Path\_AA\_Linear | #06 |
> | Path\_AA\_Radial | #06 |
> | Path\_AA\_Pattern | #06 |
> | Path\_AA\_Pattern\_Clamp | #07 |
> | Path\_AA\_Pattern\_Repeat | #08 |
> | Path\_AA\_Pattern\_MirrorU | #08 |
> | Path\_AA\_Pattern\_MirrorV | #08 |
> | Path\_AA\_Pattern\_Mirror | #08 |
> | SDF\_Solid | #09 | Shaders for rendering distance fields |
> | SDF\_Linear | #10 |
> | SDF\_Radial | #10 |
> | SDF\_Pattern | #10 |
> | SDF\_Pattern\_Clamp | #11 |
> | SDF\_Pattern\_Repeat | #12 |
> | SDF\_Pattern\_MirrorU | #12 |
> | SDF\_Pattern\_MirrorV | #12 |
> | SDF\_Pattern\_Mirror | #12 |
> | SDF\_LCD\_Solid | #09 | Shaders for rendering distance fields with subpixel rendering.  SDF\_LCD\_\* shaders are only used when the device reports support for subpixel rendering in *DeviceCaps*. Otherwise SDF\_\* shaders are used |
> | SDF\_LCD\_Linear | #10 |
> | SDF\_LCD\_Radial | #10 |
> | SDF\_LCD\_Pattern | #10 |
> | SDF\_LCD\_Pattern\_Clamp | #11 |
> | SDF\_LCD\_Pattern\_Repeat | #12 |
> | SDF\_LCD\_Pattern\_MirrorU | #12 |
> | SDF\_LCD\_Pattern\_MirrorV | #12 |
> | SDF\_LCD\_Pattern\_Mirror | #12 |
> | Opacity\_Solid | #13 | Shaders for offscreen rendering |
> | Opacity\_Linear | #14 |
> | Opacity\_Radial | #14 |
> | Opacity\_Pattern | #14 |
> | Opacity\_Pattern\_Clamp | #15 |
> | Opacity\_Pattern\_Repeat | #16 |
> | Opacity\_Pattern\_MirrorU | #16 |
> | Opacity\_Pattern\_MirrorV | #16 |
> | Opacity\_Pattern\_Mirror | #16 |
> | Upsample | #17 | Gaussian upsampling step |
> | Downsample | #18 | Gaussian downsampling step |
> | Shadow | #19 | Shadow rendering |
> | Blur | #13 | Blur rendering |
> | Custom\_Effect | #20 | Custom pixel shader |

- New enumerations added. Renderer implementations should use them to be more compatible with future changes:

> - Noesis::Shader::Vertex
> - Noesis::Shader::Vertex::Format
> - Noesis::Shader::Vertex::Format::Attr
> - Noesis::Shader::Vertex::Format::Attr::Type

- New tables are exposed: *VertexForShader[]*, *FormatForVertex[]*, *SizeForFormat[]*, *AttributesForFormat[]*, *TypeForAttr[]*, *SizeForType[]*. They simplify the implementation of new renderers and make them more robust to future changes.
- Support for custom shaders was added. Batch now has an extra member for that purpose: void\* pixelShader.
- Constant buffers are now specified in the Batch structure with data and hashes for each binding. This simplifies the implementation on each renderer.

> ```
> // Uniform shader values. For unused buffers, 'values' is set to null and 'numDwords' is zero.
> // A hash for the content is given to avoid unnecessary constant buffer updates
> struct UniformData
> {
>     const void* values;
>     uint32_t numDwords;
>     uint32_t hash;
> };
> ```

- New blending modes:

> | Blend Mode | Src | Dest | SrcAlpha | DestAlpha |
> | --- | --- | --- | --- | --- |
> | SrcOver\_Multiply | DEST\_COLOR | INV\_SRC\_ALPHA | BLEND\_ONE | INV\_SRC\_ALPHA |
> | SrcOver\_Screen | BLEND\_ONE | INV\_SRC\_COLOR | BLEND\_ONE | INV\_SRC\_ALPHA |
> | SrcOver\_Additive | BLEND\_ONE | BLEND\_ONE | BLEND\_ONE | INV\_SRC\_ALPHA |

- New stencil mode:

> | Stencil Mode | Stencil Func | Stencil Pass |
> | --- | --- | --- |
> | Clear | FUNC\_ALWAYS | OP\_ZERO |

- Scissoring is no longer part of the render state and must be always disabled.
- Our renderer implementations are now using a texture lod bias of -0.75, this helps with the blurriness when using mipmaps (in 3.1 our app framework is generating mipmaps for all textures)