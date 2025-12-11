Source: https://www.noesisengine.com/docs/Gui.Core._DrawingContext.html

# DrawingContext Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](https://docs.microsoft.com/en-us/dotnet/api/system.windows.media.drawingcontext)

Describes visual content using draw, push, and pop commands during [UIElement](_UIElement.md) *OnRender*.

When you use a [DrawingContext](_DrawingContext.md) object's draw commands, you are actually storing a set of rendering instructions that will later be used by the graphics system; you are not drawing to the screen in real-time.

# Inheritance Hierarchy

• *DrawingContext*

# Properties

DrawingContext has no properties

# Attached Properties

DrawingContext has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *DrawEllipse(brush, pen, center, rX, rY)* | Draws an ellipse with the specified [Brush](_Brush.md) and [Pen](_Pen.md) |
|  *DrawGeometry(brush, pen, geometry)* | Draws the specified [Geometry](_Geometry.md) using the specified [Brush](_Brush.md) and [Pen](_Pen.md) |
|  *DrawImage(imageSource, rect)* | Draws an image into the region defined by the specified Rect |
|  *DrawLine(pen, p0, p1)* | Draws a line between the specified points using the specified [Pen](_Pen.md) |
|  *DrawMesh(brush, mesh)* | Draws the specified triangular mesh using the specified [Brush](_Brush.md) |
|  *DrawRectangle(brush, pen, rect)* | Draws a rectangle with the specified [Brush](_Brush.md) and [Pen](_Pen.md) |
|  *DrawRoundedRectangle(brush, pen, rect, rX, rY)* | Draws a rounded rectangle with the specified [Brush](_Brush.md) and [Pen](_Pen.md) |
|  *DrawText(formattedText, bounds)* | Draws formatted text at the specified location |
|  *Pop()* | Pops the last opacity mask, opacity, clip, effect, or transform operation that was pushed onto the drawing context |
|  *PushBlendingMode(mode)* | Pushes the specified Blending mode |
|  *PushClip(clipGeometry)* | Pushes the specified clip region onto the drawing context |
|  *PushTransform(transform)* | Pushes the specified [Transform](_Transform.md) onto the drawing context |

# Events

DrawingContext has no events