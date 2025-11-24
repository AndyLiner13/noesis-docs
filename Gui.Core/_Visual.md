Source: https://www.noesisengine.com/docs/Gui.Core._Visual.html

# Visual Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.media.visual.aspx)

Provides rendering support, which includes hit testing, coordinate transformation, and bounding box calculations.

# Inheritance Hierarchy

• [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](/Gui.DependencySystem/_DependencyObject.md)

• *Visual*

• [UIElement](/Gui.Core/_UIElement.md)

# Properties

| Name | Description |
| --- | --- |
| ○ *View* | Gets the view where this visual is connected to |

● Dependency Property   ○ Reflection Property

## From [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

| Name | Description |
| --- | --- |
| ○ *ThreadId* | Gets the thread this [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) is associated with. Returns NoThreadId when this object is not attached to any thread. |

● Dependency Property   ○ Reflection Property

# Attached Properties

Visual has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *EnsureRenderId(updater)* | Ensures that a render node exists for this visual |
|  *FindCommonVisualAncestor(visual)* | Finds the common ancestor of two visuals objects If *visual* is the same object as this, the common ancestor will be the parent |
|  *GetRenderTreeId()* | Gets RenderTree's identifier |
|  *IsAncestorOf(visual)* | Determines whether the visual object is an ancestor of the descendant visual object This object is not considered to be an ancestor of *visual* if they are the same |
|  *IsConnectedToView()* | Indicates if this visual has been connected to a View |
|  *IsDescendantOf(visual)* | Determines whether the visual object is a descendant of the ancestor visual object This object is not considered to be a descendant of *visual* if they are the same |
|  *IsInRenderTree()* | Indicates if a render node has been created in the RenderTree for this visual |
|  *IsInvalidated()* | Indicates if this visual is invalidated and should send updates to the render tree |
|  *PointFromScreen(point)* | Converts a Point in screen coordinates into a Point that represents the current coordinate system of the [Visual](/Gui.Core/_Visual.md) |
|  *PointToScreen(point)* | Converts a Point that represents the current coordinate system of the [Visual](/Gui.Core/_Visual.md) into a Point in screen coordinates |
|  *SubtreeDrawingCommandsChanged()* | Occurs when subtree render commands have changed |
|  *TransformToAncestor(ancestor)* | Returns a transform that can be used to transform coordinates from the [Visual](/Gui.Core/_Visual.md) to the specified ancestor of the visual object |
|  *TransformToDescendant(descendant)* | Returns a transform that can be used to transform coordinates from the [Visual](/Gui.Core/_Visual.md) to the specified visual object descendant |
|  *TransformToVisual(visual)* | Returns a transform that can be used to transform coordinates from the [Visual](/Gui.Core/_Visual.md) to the specified visual object |
|  *UpdateRender(updater)* | Pushes all the layout updates into the UI render thread queue to update render nodes |

## From [DependencyObject](/Gui.DependencySystem/_DependencyObject.md)

| Name | Description |
| --- | --- |
|  *ClearAnimation(dp)* | Clears the animation value of a property |
|  *ClearLocalValue(dp)* | Clears the local value of a property The property to be cleared is specified by a [DependencyProperty](/Gui.DependencySystem/_DependencyProperty.md) identifier |
|  *CoerceValue(dp)* | Coerces and validates the effective property value |
|  *DependencyPropertyChanged()* | Returns the PropertyChanged event |
|  *Destroyed()* | Destroyed delegate is raised when object is going to be destroyed |
|  *GetBaseValue(dp)* | Returns the base value without animation nor coerce (this never returns [Expression](/Gui.DependencySystem/_Expression.md) like GetLocalValue) |
|  *GetExpression(dp)* | Gets the expression, if any, used to evaluate the specified property value |
|  *GetLocalValue(dp)* | Returns the local value of a dependency property, if it exists |
|  *GetValue(dp)* | Returns the current effective value of a dependency property on this instance of a [DependencyObject](/Gui.DependencySystem/_DependencyObject.md) |
|  *GetValueObject(dp)* | Returns the current effective value of a dependency property on this instance of a [DependencyObject](/Gui.DependencySystem/_DependencyObject.md) as a boxed value |
|  *GetValueProvider(dp)* | Gets the provider that returns the effective value for the specified dependency property |
|  *HasAnimatedProperties()* | Returns true if there is any animated property |
|  *InvalidateProperty(dp, priority)* | Re-evaluates the effective value for the specified dependency property if necessary If null is passed, a full re-evaluation could be needed |
|  *IsCached(dp, provider)* | Returns if the value is stored in the cache. If true, the priority is returned in the provider field |
|  *IsSealed()* | Gets a value that indicates whether this instance is currently sealed (read-only) |
|  *SetAnimation(dp, value)* | Sets the animated value of a property |
|  *SetCurrentValue(dp, value)* | Sets the current value of a dependency property. The current value is set on the coerce field, without modifying source or animated value |
|  *SetCurrentValueObject(dp, value)* | Sets the current value of a dependency property using a boxed value |
|  *SetExpression(dp, expression)* | Sets the expression to be evaluated dynamically to obtain the value of the property |
|  *SetValue(dp, value)* | Sets the local value of a dependency property |
|  *SetValueObject(dp, value)* | Sets the local value (boxed) of a dependency property |

## From [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md)

| Name | Description |
| --- | --- |
|  *CheckAccess()* | Determines whether the calling thread has access to this [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) |
|  *VerifyAccess()* | Enforces that the calling thread has access to this [DispatcherObject](/Gui.DependencySystem/_DispatcherObject.md) |

# Events

Visual has no events