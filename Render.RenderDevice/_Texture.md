Source: https://www.noesisengine.com/docs/Render.RenderDevice._Texture.html

# Texture Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace)

Base class for 2D textures

# Inheritance Hierarchy

• *Texture*

# Properties

Texture has no properties

# Attached Properties

Texture has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *GetHeight()* | Returns the height of the texture, in pixels |
|  *GetWidth()* | Returns the width of the texture, in pixels |
|  *HasAlpha()* | Returns true if the texture has an alpha channel that is not completely white. Just a hint to optimize rendering as alpha blending can be disabled when there is no transparency. |
|  *HasMipMaps()* | Returns true if the texture has mipmaps |
|  *IsInverted()* | Returns true when texture must be vertically inverted when mapped. This is true for surfaces on platforms (OpenGL) where texture V coordinate is zero at the "bottom of the texture" |
|  *SetPrivateData(data)* | Stores custom private data |

# Events

Texture has no events