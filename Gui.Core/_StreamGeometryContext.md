Source: https://www.noesisengine.com/docs/Gui.Core._StreamGeometryContext.html

# StreamGeometryContext Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace)

Describes a geometry using drawing commands. This class is used with the [StreamGeometry](/Gui.Core/_StreamGeometry.md) class to create a lightweight geometry that does not support data binding, animation, or modification.

# Inheritance Hierarchy

• *StreamGeometryContext*

# Properties

StreamGeometryContext has no properties

# Attached Properties

StreamGeometryContext has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *ArcTo(point, size, rotationAngleDeg, isLargeArc, sweepDirection)* | Draws an arc to the specified point |
|  *BeginFigure(startPoint, isClosed)* | Specifies the starting point for a new figure |
|  *Close()* | Closes this context and flushes its content so that it can be rendered. Afterwards the stream context can not be used anymore. If Close() is not called then the associated geometry remains unaltered |
|  *CubicTo(point1, point2, point3)* | Draws a cubic Bezier curve to the specified point |
|  *LineTo(point)* | Draws a straight line to the specified Point |
|  *QuadraticTo(point1, point2)* | Draws a quadratic Bezier curve to the specified point |
|  *SetIsClosed(isClosed)* | Overrides the isClosed flag for the current figure |
|  *SmoothCubicTo(point1, point2)* | Draws a G1 smooth cubic Bezier curve to the specified point |
|  *SmoothQuadraticTo(point)* | Draws a G1 smooth quadratic Bezier curve to the specified point |

# Events

StreamGeometryContext has no events