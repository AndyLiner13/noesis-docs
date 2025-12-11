Source: https://www.noesisengine.com/docs/Gui.Core._HierarchicalDataTemplate.html

# HierarchicalDataTemplate Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.hierarchicaldatatemplate.aspx)

Represents a [DataTemplate](_DataTemplate.md) that supports [HeaderedItemsControl](_HeaderedItemsControl.md), such as [TreeViewItem](_TreeViewItem.md) or [MenuItem](_MenuItem.md).

```
<Grid
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

    <Grid.Resources>
        <LeagueList x:Key="items" />

        <HierarchicalDataTemplate DataType="League" ItemsSource="{Binding Path=Divisions}">
            <TextBlock Text="{Binding Path=Name}"/>
        </HierarchicalDataTemplate>

        <HierarchicalDataTemplate DataType="Division" ItemsSource="{Binding Path=Teams}">
            <TextBlock Text="{Binding Path=Name}"/>
        </HierarchicalDataTemplate>

        <DataTemplate DataType="Team">
            <TextBlock Text="{Binding Path=Name}"/>
        </DataTemplate>
    </Grid.Resources>

    <TreeView DataContext="{StaticResource items}">
        <TreeViewItem ItemsSource="{Binding Leagues}" Header="My Soccer Leagues" />
    </TreeView>

</Grid>
```

# Inheritance Hierarchy

• [FrameworkTemplate](_FrameworkTemplate.md)

• [DataTemplate](_DataTemplate.md)

• *HierarchicalDataTemplate*

# Properties

| Name | Description |
| --- | --- |
| ○ *ItemContainerStyle* | Gets or sets the [Style](_Style.md) that is applied to the item container for each child item |
| ○ *ItemTemplate* | Gets or sets the [DataTemplate](_DataTemplate.md) to apply to the ItemTemplate property on a generated [HeaderedItemsControl](_HeaderedItemsControl.md) (such as a [MenuItem](_MenuItem.md) or a [TreeViewItem](_TreeViewItem.md)), to indicate how to display items from the next level in the data hierarchy |
| ○ *ItemTemplateSelector* | Gets or sets the [DataTemplateSelector](_DataTemplateSelector.md) to apply to the ItemTemplateSelector property on a generated [HeaderedItemsControl](_HeaderedItemsControl.md) (such as a [MenuItem](_MenuItem.md) or a [TreeViewItem](_TreeViewItem.md)), to indicate how to select a template to display items from the next level in the data hierarchy |
| ○ *ItemsSource* | Gets or sets the binding for this data template, which indicates where to find the collection that represents the next level in the data hierarchy |

● Dependency Property   ○ Reflection Property

## From [DataTemplate](_DataTemplate.md)

| Name | Description |
| --- | --- |
| ○ *DataType* | Gets or sets the type for which this [DataTemplate](_DataTemplate.md) is intended |
| ○ *Triggers* | Gets a collection of triggers that apply property values or perform actions based on one or more conditions. |

● Dependency Property   ○ Reflection Property

## From [FrameworkTemplate](_FrameworkTemplate.md)

| Name | Description |
| --- | --- |
| ○ *Resources* | Gets or sets the collection of resources that can be used within the scope of this template |
| ○ *VisualTree* | Gets or sets the root node of the template |

● Dependency Property   ○ Reflection Property

# Attached Properties

HierarchicalDataTemplate has no attached properties

# Methods

## From [FrameworkTemplate](_FrameworkTemplate.md)

| Name | Description |
| --- | --- |
|  *Apply(templatedParent)* | Applies current template to the specified element |
|  *FindName(name, templatedParent)* | Finds the element associated with the specified name defined within this template |
|  *FindName(name)* | Returns an object that has the provided identifying name |
|  *FindObject(object)* | Finds if element is a named object registered in the template. Returns null if not found |
|  *GetAvailableTriggers()* | Gets template triggers if available |
|  *RegisterName(name, object)* | Registers the provided name into the current XAML namescope |
|  *UnregisterName(name)* | Unregisters the provided name from the current XAML namescope |
|  *UpdateName(name, object)* | Updates previously registered item with new one. This is required to refresh Binginds when freezables are cloned during animations |

# Events

HierarchicalDataTemplate has no events