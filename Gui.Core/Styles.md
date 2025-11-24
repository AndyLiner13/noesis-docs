Source: https://www.noesisengine.com/docs/Gui.Core.Styles.html

# Styles & Templates Overview

Styling and templating represent a set of tools (styles, templates, triggers, and storyboards) that allow developers and designers to create visually compelling effects and to create a consistent appearance for their product. Although developers and or designers can customize the appearance extensively on an application-by-application basis, a strong styling and templating model is necessary to allow maintenance and sharing of the appearance within and among applications.

Another important aspect of styling is the ability to give any user interface element a radically different look without having to give up all of the built-in functionality that it provides.

We will describe here three kinds appearance customization tools present in Noesis GUI Framework: styles, templates and themes.

# Styles

A style is a pretty simple entity. Its main function is to group together property values that could otherwise be set individually. The intent is to then share this group of values among multiple elements. Any individual element can override aspects of its Style by directly setting a property to a local value.

Style uses a collection of Setters to set the target properties. Creating a Setter is just a matter of specifying the name of a dependency property (qualified with its class name) and its desired value.

Defining a Style as a resource also gives you all the flexibility that the resource mechanism provides. For example, you could define one version of a button style at the application level, but override it with a different Style in an individual Window's Resources collection.

Despite its name, there's nothing inherently visual about a Style. But it's typically used for setting properties that affect visuals. Indeed, Style only enables the setting of dependency properties, which tend to be visual in nature.

If you want to enforce that a Style can only be applied to a particular type, you can set its *TargetType* property accordingly. Any attempt to apply this Style to another element type generates an error. In addition, when you apply a TargetType to a Style, you no longer need to prefix the property names inside Setters with the type name. Applying a TargetType to a Style gives you another feature as well. If you omit its Key, the Style gets implicitly applied to all elements of that target type within the same scope. This is typically called a typed style as opposed to a named style.

Styles can also contain a collection of triggers that applies their setters based on one or more conditions. There are two types of triggers supported by a Style: property triggers (invoked when the value of a dependency property changes) and event triggers (invoked when a routed event is raised).

Even more, styles can inherit from another style by using the *BasedOn* property.

Style definition examples:

```
<Grid>
    <Grid.Resources>
        <!-- named style -->
        <Style x:Key="ButtonStyle" TargetType="{x:Type Button}">
            <Setter Property="Background" Value="Navy"/>
            <Setter Property="Foreground" Value="LightBlue"/>
            <Setter Property="FontSize" Value="21"/>
            <Setter Property="Margin" Value="2,1"/>
            <Setter Property="Padding" Value="20,5"/>
        </Style>
        <!-- typed style -->
        <Style TargetType="{x:Type Button}" BasedOn="{StaticResource ButtonStyle}">
            <Setter Property="FontWeight" Value="Bold"/>
            <Style.Triggers>
                <Trigger Property="IsMouseOver" Value="True">
                    <Setter Property="Foreground" Value="White"/>
                </Trigger>
            </Style.Triggers>
        </Style>
    </Grid.Resources>
</Grid>
```

Applying a style example:

```
<StackPanel>
    <Button Style="{StaticResource ButtonStyle}" Content="Using named style"/>
    <Button Content="Using typed style"/>
</StackPanel>
```

![StyledButton.png](/StyledButton/png.md)

# Templates

A template allows the user to completely replace an element's visual tree with anything he can dream up, while keeping all of its functionality intact. And templates aren't just some add-on mechanism for third parties;
the default visuals for every Control are defined in templates (and customized for each theme). The source code for every control is completely separated from its default visual tree representations.

Control templates are represented by the *ControlTemplate* class that derives from the abstract FrameworkTemplate class. The important piece of the ControlTemplate class is its VisualTree content property,
which contains the tree of elements that define the desired look. After you define a ControlTemplate in XAML, you can attach it to any Control by setting its *Template* property.

As with Style, ControlTemplate has a *TargetType* property that can restrict where the template can be applied. It also enables you to remove the class name qualifications on any property references inside a template (such as the values of Trigger.Property and Setter.Property).

Templates can also contain all types of triggers in the Triggers collection to add interactivity to the control.

Naming an element with x:Name inside a template does not make it become a field to access programmatically, unlike its behavior outside of a template. This is because a template can be applied to multiple elements in the same scope. The main purpose of naming elements in a template is for referencing them from triggers (typically defined in XAML).

Unlike a Style, the use of TargetType does not enable you to remove the template's x:Key (when used in a dictionary). There is no such thing as a default control template; you have to set the template inside a typed Style to get such behavior.

In order to respect the templated parent's properties we can use the *TemplateBinding* extension to bind the value of template element properties. No matter what type of control you're creating a control template for, there are undoubtedly other properties on the target control that should be honored if you want the template to be reusable: Height and Width, perhaps Background, Padding, and so on. Some properties (such as Foreground, FontSize, FontWeight, and so on) might automatically inherit their desired values thanks to property value inheritance in the visual tree, but other properties need explicit attention.

Defining a template:

```
<Grid.Resources>
    <!-- template -->
    <ControlTemplate x:Key="ButtonTemplate" TargetType="{x:Type Button}">
        <Border x:Name="Bd"
            Background="{TemplateBinding Background}"
            BorderBrush="LightBlue"
            BorderThickness="4"
            CornerRadius="4">
            <ContentPresenter Margin="{TemplateBinding Padding}"/>
        </Border>
        <ControlTemplate.Triggers>
            <Trigger Property="IsMouseOver" Value="True">
                <Setter TargetName="Bd" Property="BorderBrush" Value="Gold"/>
            </Trigger>
            <Trigger Property="IsPressed" Value="True">
                <Setter TargetName="Bd" Property="Background" Value="Black"/>
                <Setter TargetName="Bd" Property="BorderBrush" Value="Orange"/>
            </Trigger>
        </ControlTemplate.Triggers>
    </ControlTemplate>
    <!-- ... -->
</Grid.Resources>
```

Applying the template:

```
<!-- as a setter value -->
<Style x:Key="ButtonStyle" TargetType="{x:Type Button}">
    <Setter Property="Template" Value="{StaticResource ButtonTemplate}"/>
</Style>

<!-- as a resource applied to a button -->
<Button Template="{StaticResource ButtonTemplate}"/>
```

![TemplatedButton.png](/TemplatedButton/png.md)

# Themes

Themes refers to the act of changing an application's appearance (or skin). The best approach is to make ResourceDictionary the root of a theme representation. ResourceDictionary makes a great extensibility point in general because of the ease in which it can be swapped in and out or merged with others. When defining a theme, it makes sense for the ResourceDictionary to contain Styles and Templates for all the controls.