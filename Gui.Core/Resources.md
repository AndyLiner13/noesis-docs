Source: https://www.noesisengine.com/docs/Gui.Core.Resources.html

# Resources Overview

# Introduction

This overview explains how to use resources as a simple way to reuse commonly defined objects and values. It focuses on how to use resources in XAML. You can also create and access resources by using code, or interchangeably between code and XAML.

Every [FrameworkElement](/Gui.Core/_FrameworkElement.md) has a Resources property, which is the property that contains the resources (as a [ResourceDictionary](/Gui.Core/_ResourceDictionary.md)) that an element defines. You can define resources on any element. However, resources are most often defined on the root element of the XAML tree.

Each resource in a resource dictionary must have a unique key. When you define resources in markup, you assign the unique key through the *x:Key* directive. Typically, the key is a string; however, you can also set it to object types by using the appropriate markup extensions. Nonstring keys for resources are usally employed for styles.

After you define a resource, you can reference the resource to be used for a property value by using a resource markup extension syntax that specifies the key name, for example:

```
<Grid
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

    <Grid.Resources>
        <SolidColorBrush x:Key="RedBrush" Color="#80800000"/>
    </Grid.Resources>

    <Button Background="{StaticResource RedBrush}"/>
    <Ellipse Fill="{DynamicResource RedBrush}"/>
</Grid>
```

When you define a resource on the root element, all the elements in the logical tree can access it, and you can reuse the same resource for setting the value of any property that accepts the type that the resource represents. In the previous example, the same *RedBrush* resource sets two different properties: the *Background* of a [Button](/Gui.Core/_Button.md), and the *Fill* of a [Rectangle](/Gui.Core/_Rectangle.md).

# Static and Dynamic Resources

A resource can be referenced as either a static resource or a dynamic resource. This is done by using either the [StaticResource](/Gui.Core/_StaticResourceExtension.md) Markup Extension or the [DynamicResource](/Gui.Core/_DynamicResourceExtension.md) Markup Extension. A markup extension is a feature of XAML whereby you can specify an object reference by having the markup extension process the attribute string and return the object to a XAML loader. For more information about markup extension behavior, see [Markup Extensions](/Gui.Core/MarkupExtensions.md).

When you use a markup extension, you typically provide one or more parameters in string form that are processed by that particular markup extension, rather than being evaluated in the context of the property being set. The StaticResource Markup Extension processes a key by looking up the value for that key in all available resource dictionaries. This happens during loading, which is the point in time when the loading process needs to assign the property value that takes the static resource reference. The DynamicResource Markup Extension instead processes a key by creating an expression, and that expression remains unevaluated until the application is actually run, at which time the expression is evaluated and provides a value.

## Static Resources

Static resource references work best for the following circumstances:

- Your application design concentrates most of all of its resources into window or application level resource dictionaries. Static resource references are not reevaluated based on runtime behaviors and therefore there can be some performance benefit to avoiding large numbers of dynamic resource references when they are not necessary per your resource and application design.
- You are setting the value of a property that is not on a DependencyObject or a Freezable.
- You are creating a theme for a custom control, and are defining resources that are used within the themes. For this case, you typically do not want the dynamic resource reference lookup behavior, you instead want the static resource reference behavior so that the lookup is predictable and self-contained to the theme.

When a StaticResource extension searches for the named resource it follows this lookup behavior:

- The lookup process checks for the requested key within the resource dictionary defined by the element that sets the property.
- The lookup process then traverses the logical tree upward, to the parent element and its resource dictionary. This continues until the root element is reached.
- Next, application resources are checked. Application resources are those resources within the resource dictionary that is defined by the Application object for your application.

NOTE

When using C++ SDK, objects that are not part of the logical tree (FrameworkElement or Animatable inherited classes), need to implement the **IUITreeNode** interface so StaticResource extension can walk up the tree to search for the specified resource. We also provide a base collection, **UICollection<T>**, that implements such interface to allow StaticResources defined in the contained items to correctly perform the resource look up.

Static resource references from within a resource dictionary must reference a resource that has already been defined lexically before the resource reference. Forward references cannot be resolved by a static resource reference. For this reason, if you use static resource references, you must design your resource dictionary structure such that resources intended for by-resource use are defined at or near the beginning of each respective resource dictionary.

Static resource lookup can extend into themes; however, static resource references to keys that are known to only exist in themes or as system resources are not recommended. This is because such references are not reevaluated if the theme is changed by the user in realtime. A dynamic resource reference is more reliable when you request theme resources.

If a resource was requested by a static resource reference in XAML, and was not found, then an error message will be shown at runtime.

## Dynamic Resources

Dynamic resources work best for the following circumstances:

- The value of the resource depends on conditions that are not known until runtime. This includes resources that can be user settable. These values are truly dynamic because they ultimately come from the runtime environment of the user. You might also have application-level themes that can change, where window-level resource access must also capture the change.
- You are creating or referencing theme styles for a custom control.
- You intend to adjust the contents of a ResourceDictionary during an application lifetime.
- You have a complicated resource structure that has interdependencies, where a forward reference may be required. Static resource references do not support forward references, but dynamic resource references do support them because the resource does not need to be evaluated until runtime, and forward references are therefore not a relevant concept.
- You are creating a style where setter values might come from other values that are influenced by themes or other user settings.
- You are applying resources to elements that might be reparented in the logical tree during application lifetime. Changing the parent also potentially changes the resource lookup scope, so if you want the resource for a reparented element to be reevaluated based on the new scope, always use a dynamic resource reference.

Resource lookup behavior for a dynamic resource reference parallels the lookup behavior in your code if you call FindResource.

- The lookup process checks for the requested key within the resource dictionary defined by the element that sets the property.

> - If the element defines a Style property, the Resources dictionary within the Style is checked.
> - If the element defines a Template property, the Resources dictionary within the FrameworkTemplate is checked.

- The lookup process then traverses the logical tree upward, to the parent element and its resource dictionary. This continues until the root element is reached.
- Next, application resources are checked. Application resources are those resources within the resource dictionary that is defined by the Application object for your WPF application.
- Theme resource dictionary is checked, for the currently active theme. If the theme changes at runtime, the value is reevaluated.

NOTE

As mentioned before, when using C++ SDK, objects that are not part of the logical tree (FrameworkElement or Animatable inherited classes), need to implement the **IUITreeNode** interface so DynamicResource extension can walk up the tree to search for the specified resource.

When a resource was requested by a FindResource call, and was not found, no error message is generated, but the returned value is null. If the property being set does not accept null, then it is still possible that an error will be raised (this depends on the individual property being set).

If a resource was requested by a dynamic resource reference in XAML, and was not found, then the behavior depends on the general property system, but the general behavior is as if no property setting operation occurred at the level where the resource exists. For instance, if you attempt to set the *Background* on an individual button element using a resource that could not be evaluated, then no value set results, but the effective value can still come from other participants in the property system and value precedence. For instance, the background value might still come from a locally defined button style, or from the theme style. For properties that are not defined by theme styles, the effective value after a failed resource evaluation might come from the default value in the property metadata.

Dynamic resource references have some notable restrictions. At least one of the following must be true:

- The property being set must be a property on a FrameworkElement. That property must be backed by a DependencyProperty.
- The reference is for a value within a Style Setter.
- The property being set must be a property on a Freezable that is provided as a value of a FrameworkElement property, or a Setter value.

Because the property being set must be a DependencyProperty or Freezable property, most property changes can propagate to UI because a property change (the changed dynamic resource value) is acknowledged by the property system. Most controls include logic that will force another layout of a control if a DependencyProperty changes and that property might affect layout. However, not all properties that have a DynamicResource Markup Extension as their value are guaranteed to provide the value in such a way that they update in realtime in the UI. That functionality still might vary depending on the property, as well as depending on the type that owns the property, or even the logical structure of your application.

# Styles and Implicit Keys

Earlier, it was stated that all items in a ResourceDictionary must have a key. However, that does not mean that all resources must have an explicit x:Key. Several object types support an implicit key when defined as a resource, where the key value is tied to the value of another property. This is known as an implicit key, whereas an x:Key attribute is an explicit key. You can overwrite any implicit key by specifying an explicit key.

One very important scenario for resources is when you define a Style. In fact, a Style is almost always defined as an entry in a resource dictionary, because styles are inherently intended for reuse. For more information about styles, see [Styling and Templating](/Gui.Core/Styles.md).

Styles for controls can be both created with and referenced with an implicit key. The theme styles that define the default appearance of a control rely on this implicit key. The implicit key from the standpoint of requesting it is the Type of the control itself. The implicit key from the standpoint of defining the resource is the *TargetType* of the style. Therefore, if you are creating themes for custom controls, creating styles that interact with existing theme styles, you do not need to specify an x:Key Directive for that Style. And if you want to use the themed styles, you do not need to specify any style at all. For instance, the following style definition works, even though the Style resource does not appear to have a key:

```
<Grid.Resources>
    <Style TargetType="Button" BasedOn="{StaticResource {x:Type Button}}">
        <Setter Property="Background">
            <Setter.Value>
                <LinearGradientBrush>
                    <GradientStop Offset="0.0" Color="Red"/>
                    <GradientStop Offset="1.0" Color="Orange"/>
                </LinearGradientBrush>
            </Setter.Value>
        </Setter>
        <Setter Property="FontSize" Value="18"/>
    </Style>
</Grid.Resources>
```

That style really does have a key: the implicit key TypeOf<Button>(). In markup, you can specify a TargetType directly as the type name or you can optionally use {x:Type...} markup extension to return a type.

Through the default theme style mechanisms, that style is applied as the runtime style of a Button on the Grid subtree, even though the Button itself does not attempt to specify its Style property or a specific resource reference to the style. Your style defined in the tree is found earlier in the lookup sequence earlier than the theme dictionary style, using the same key that the theme dictionary style has. You could just specify <Button>Hello</Button> anywhere in the tree, and the style you defined with TargetType of Button would apply to that button. If you want, you can still explicitly key the style with the same type value as TargetType, for clarity in your markup, but that is optional.

```
<Grid.Resources>
    <Style x:Key="{x:Type Button}" TargetType="{x:Type Button}" />
</Grid.Resources>
```

Implicit keys for styles do not apply on a control if OverridesDefaultStyle is true (also note that OverridesDefaultStyle might be set as part of native behavior for the control class, rather than explicitly on an instance of the control). If you set OverridesDefaultStyle to true on a control, you will be suppressing the default control template supplied by the theme styles. Also, in order to support implicit keys for derived class scenarios, the control must override DefaultStyleKey property (all existing controls provided as part of Noesis GUI do this).

# Organizing XAML Resources

Resources provide a nice way to factor your XAML within a tree. And if you store them as application-level resources, they can live in a separate XAML file. But if you want to partition a set of resources into arbitrary XAML files no matter where they are stored in the logical tree (perhaps for maintainability or flexibility), you can leverage the MergedDictionaries property of the ResourceDictionary class to achieve this.

For example, a Window could set its Resources collection as follows to merge together multiple resource dictionaries from separate files:

```
<Window.Resources>
    <ResourceDictionary>
        <ResourceDictionary.MergedDictionaries>
            <ResourceDictionary Source="CommonResources.xaml"/>
            <ResourceDictionary Source="MainWindowResources.xaml"/>
        </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
</Window.Resources>
```

The separate files must use ResourceDictionary as the root element. For example, CommonResources.xaml could contain:

```
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
        <SolidColorBrush x:Key="RedBrush" Color="#80800000"/>
</ResourceDictionary>
```

If the dictionaries being merged have a duplicate key, the last one wins (unlike the case of having duplicate keys in a single dictionary).