Source: https://www.noesisengine.com/docs/Gui.Controls._GridView.html

# GridView Class

## namespace [Noesis](../Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.controls.gridview.aspx)

Represents a view mode that displays data items in columns for a [ListView](_ListView.md) control.

XAML

```
<Grid>
  <ListView Margin="10">
    <ListView.View>
      <GridView>
        <GridViewColumn Header="Name" Width="120" DisplayMemberBinding="{Binding Name}"/>
        <GridViewColumn Header="Age" Width="50" DisplayMemberBinding="{Binding Age}"/>
        <GridViewColumn Header="Mail" Width="150" DisplayMemberBinding="{Binding Mail}"/>
      </GridView>
    </ListView.View>
  </ListView>
</Grid>
```

The [GridView](_GridView.md) class and its supporting classes provide the infrastructure to display data items that are specified for a [ListView](_ListView.md) control in a series of columns. The columns have column headers, which are buttons that are derived from ButtonBase, and you can reorder the columns by using drag-and-drop operations. Note that the columns of a [GridView](_GridView.md) display data and do not provide direct access to the source of the data.

The columns in a [GridView](_GridView.md) are defined as [GridViewColumn](_GridViewColumn.md) objects. In XAML, you can define [GridViewColumn](_GridViewColumn.md) objects as child elements of the [GridView](_GridView.md).

# Inheritance Hierarchy

• [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md)

• [DependencyObject](../Gui.DependencySystem/_DependencyObject.md)

• [Freezable](../Gui.DependencySystem/_Freezable.md)

• [Animatable](../Gui.Core/_Animatable.md)

• [BaseView](_BaseView.md)

• *GridView*

# Properties

| Name | Description |
| --- | --- |
| ● *AllowsColumnReorder* | Gets or sets whether columns in a [GridView](_GridView.md) can be reordered by a drag-and-drop operation |
| ● *ColumnHeaderContainerStyle* | Gets or sets the style to apply to column headers |
| ● *ColumnHeaderContextMenu* | Gets or sets a [ContextMenu](../Gui.Core/_ContextMenu.md) for the [GridView](_GridView.md) |
| ● *ColumnHeaderStringFormat* | Gets or sets a composite string that specifies how to format the column headers of the [GridView](_GridView.md) if they are displayed as strings |
| ● *ColumnHeaderTemplate* | Gets or sets a template to use to display the column headers |
| ● *ColumnHeaderTemplateSelector* | Gets or sets the selector object that provides logic for selecting a template to use for each column header |
| ● *ColumnHeaderToolTip* | Gets or sets the content of a tooltip that appears when the mouse pointer pauses over one of the column headers |
| ○ *Columns* | Gets the collection of [GridViewColumn](_GridViewColumn.md) objects that is defined for this [GridView](_GridView.md) |

● Dependency Property   ○ Reflection Property

## From [Freezable](../Gui.DependencySystem/_Freezable.md)

| Name | Description |
| --- | --- |
| ○ *CanFreeze* | Gets a value that indicates whether the object can be made unmodifiable. |
| ○ *IsFrozen* | Gets a value that indicates whether the object is currently modifiable. |

● Dependency Property   ○ Reflection Property

## From [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md)

| Name | Description |
| --- | --- |
| ○ *ThreadId* | Gets the thread this [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md) is associated with. Returns NoThreadId when this object is not attached to any thread. |

● Dependency Property   ○ Reflection Property

# Attached Properties

| Name | Description |
| --- | --- |
| ● *ColumnCollection* | Gets or sets the attached property that contains the GridViewColumnCollection |

# Methods

## From [BaseView](_BaseView.md)

| Name | Description |
| --- | --- |
|  *ClearItem(item)* | Removes all bindings and styling that are set for an item |
|  *PrepareItem(item)* | Prepares an item in the view for display, by setting bindings and styles |

## From [Freezable](../Gui.DependencySystem/_Freezable.md)

| Name | Description |
| --- | --- |
|  *Clone()* | Creates a modifiable clone of the [Freezable](../Gui.DependencySystem/_Freezable.md), making deep copies of the object's values. When copying the object's dependency properties, this method copies expressions (which might no longer resolve) but not animations or their current values. The cloned Freezable::IsFrozen property is false even if the source's IsFrozen property is true. |
|  *CloneCurrentValue()* | Creates a modifiable clone (deep copy) of the [Freezable](../Gui.DependencySystem/_Freezable.md) using its current values. The cloned object's IsFrozen property is false even if the source's IsFrozen property is true. |
|  *Freeze()* | Makes the current object unmodifiable and sets its IsFrozen property to true. |
|  *GetAsFrozen()* | Creates a frozen copy of the [Freezable](../Gui.DependencySystem/_Freezable.md), using base (non-animated) property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. Throws if the [Freezable](../Gui.DependencySystem/_Freezable.md) cannot be frozen because it contains expressions or animated properties. |
|  *GetCurrentValueAsFrozen()* | Creates a frozen copy of the [Freezable](../Gui.DependencySystem/_Freezable.md) using current property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. |

## From [DependencyObject](../Gui.DependencySystem/_DependencyObject.md)

| Name | Description |
| --- | --- |
|  *ClearAnimation(dp)* | Clears the animation value of a property |
|  *ClearLocalValue(dp)* | Clears the local value of a property The property to be cleared is specified by a [DependencyProperty](../Gui.DependencySystem/_DependencyProperty.md) identifier |
|  *CoerceValue(dp)* | Coerces and validates the effective property value |
|  *DependencyPropertyChanged()* | Returns the PropertyChanged event |
|  *Destroyed()* | Destroyed delegate is raised when object is going to be destroyed |
|  *GetBaseValue(dp)* | Returns the base value without animation nor coerce (this never returns [Expression](../Gui.DependencySystem/_Expression.md) like GetLocalValue) |
|  *GetExpression(dp)* | Gets the expression, if any, used to evaluate the specified property value |
|  *GetLocalValue(dp)* | Returns the local value of a dependency property, if it exists |
|  *GetValue(dp)* | Returns the current effective value of a dependency property on this instance of a [DependencyObject](../Gui.DependencySystem/_DependencyObject.md) |
|  *GetValueObject(dp)* | Returns the current effective value of a dependency property on this instance of a [DependencyObject](../Gui.DependencySystem/_DependencyObject.md) as a boxed value |
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

## From [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md)

| Name | Description |
| --- | --- |
|  *CheckAccess()* | Determines whether the calling thread has access to this [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md) |
|  *VerifyAccess()* | Enforces that the calling thread has access to this [DispatcherObject](../Gui.DependencySystem/_DispatcherObject.md) |

# Events

GridView has no events