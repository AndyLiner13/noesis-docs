Source: https://www.noesisengine.com/docs/Gui.Core._VisualTreeHelper.html

# VisualTreeHelper Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/System.Windows.Media.VisualTreeHelper.aspx)

Provides utility methods that perform common tasks involving nodes in a visual tree.

# Inheritance Hierarchy

• *VisualTreeHelper*

# Properties

VisualTreeHelper has no properties

# Attached Properties

VisualTreeHelper has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *GetChild(visual, childIndex)* | Returns the child visual object of a parent at the specified index |
|  *GetChildrenCount(visual)* | Returns the number of children that a parent visual contains |
|  *GetClip(visual)* | Returns the clip geometry of the visual |
|  *GetContentBounds(visual)* | Returns the cached bounding box rectangle for the visual |
|  *GetDescendantBounds(visual)* | Returns the union of all the content bounding boxes for all visual object descendants, which includes the content bounding box of the visual itself |
|  *GetDescendantBoundsMaxZ(visual)* | Returns the maximum z value of the union of all the content bounding boxes for all visual object descendants, which includes the content bounding box of the visual itself |
|  *GetDescendantBoundsMinZ(visual)* | Returns the minimum z value of the union of all the content bounding boxes for all visual object descendants, which includes the content bounding box of the visual itself |
|  *GetOffset(visual)* | Returns the offset of the visual |
|  *GetParent(visual)* | Returns the parent of the visual object |
|  *GetRoot(visual)* | Returns the root of the visual tree where the specified visual is connected to |
|  *GetSize(visual)* | Returns the size of the visual |
|  *HitTest(visual, point)* | Returns the top-most visual object of a hit test. The coordinate value you pass as the point parameter has to be relative to the coordinate space of the visual object |
|  *HitTest(visual, point, hitTestFilter, hitTestResult)* | Returns the top-most visual object of a hit test. The coordinate value you pass as the point parameter has to be relative to the coordinate space of the visual object. The specified callback will be called each time a visual is hit while traversing the tree |
|  *HitTest3D(visual, point, direction)* | Returns the top-most visual object of a hit test. The coordinate values you pass as the point and direction parameters have to be relative to the coordinate space of the visual object |
|  *HitTest3D(visual, point, direction, hitTestFilter, hitTestResult)* | Returns the top-most visual object of a hit test. The coordinate values you pass as the point and direction parameters have to be relative to the coordinate space of the visual object. The specified callback will be called each time a visual is hit while traversing the tree |
|  *IntersectPlane(visual, point, direction, outPoint)* | Returns the intersection of the given ray with the plane corresponding to the passed visual Input and output coordinates are expressed in world-space False is returned if there is no intersection |

# Events

VisualTreeHelper has no events