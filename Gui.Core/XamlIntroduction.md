# A quick guide to XAML

This tutorial describes the features of the XAML language and demonstrates how you can use XAML to write noesisGUI interfaces. Even though there are tools that generate XAML, you'll invariably want to go under the covers to understand or tweak the XAML. Besides, sometimes it's just easier to code UI by hand when you want fine control or just want to know what's going on.

# What is XAML?

XAML is a declarative markup language that you can use to create application UI such as controls, shapes, text, and other content presented on the screen. If you're familiar with web programming, you can think of XAML as similar to HTML. Like HTML, XAML is made up of elements and attributes. But XAML is XML-based and therefore must follow XML rules.

XAML directly represents the instantiation of objects. The following example shows how you might create a [button](https://www.noesisengine.com/docs/Gui.Core._Button.html) as part of a UI:

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">
  <Button Content="Click Me!"/>
</Grid>
```

**NOTE**

The attribute xmlns in the root element is explained later in this document.

For UI, XAML is easier to read and more compact than procedural code. But in rare cases it's necessary to use procedural code to create UI dynamically. The following code is equivalent to the XAML shown above:

C++
```cpp
Ptr<Button> button = *new Button();
button->SetContent("Click Me!");

Ptr<Grid> grid = *new Grid();
grid->GetChildren()->Add(button);
```

C#
```csharp
Button button = new Button();
button.Content = "Click Me!";

Grid grid = new Grid();
grid.Children.Add(button);
```

One aspect of using a declarative language like XAML is having some separation between the markup that makes up the UI and the code that makes the application do something. For example, a designer on your team could design a UI and then hand off the XAML to the developer to add the procedural code. Even if the designer and the developer are the same person (as they often are), you can keep your visuals in XAML files (.xaml) and your procedural UI code in [code-behind](https://www.noesisengine.com/docs/Gui.Core.CodeBehindTutorial.html) files (.cs and .cpp).

# XAML Syntax in Brief

The following sections explain the basic forms of XAML syntax. Much of the material in the next few sections will be elementary to you if you have previous familiarity with the XML language. This is a consequence of one of the basic design principles of XAML. The XAML language defines concepts of its own, but these concepts work within the XML language and markup form.

## XAML Object Elements

An object element typically declares an instance of a type. Object element syntax always starts with an opening angle bracket (<). This is followed by the name of the type where you want to create an instance. The name can possibly include a prefix, a concept that will be explained later. After this, you can optionally declare attributes on the object element. To complete the object element tag, end with a closing angle bracket (>). You can instead use a self-closing form that does not have any content, by completing the tag with a forward slash and closing angle bracket in succession (/>). For example, look at the previously shown markup snippet again:

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">
  <Button Content="Click Me!"/>
</Grid>
```

This specifies two object elements: <Grid> (with content, and a closing tag later), and <Button .../> (the self-closing form, with several attributes). The object elements [Grid](https://www.noesisengine.com/docs/Gui.Core._Grid.html) and [Button](https://www.noesisengine.com/docs/Gui.Core._Button.html) each map to the name of a class that is defined by noesisGUI. When you specify an object element tag, you create an instruction for XAML processing to create a new instance. Each instance is created by calling the default constructor of the underlying type when parsing and loading the XAML.

## Attribute Syntax (Properties)

Properties of an object can often be expressed as attributes of the object element. An attribute syntax names the property that is being set in attribute syntax, followed by the assignment operator (=). The value of an attribute is always specified as a string that is contained within quotation marks.

Attribute syntax is the most streamlined property setting syntax and is the most intuitive syntax to use for developers who have used markup languages in the past. In the next example, we create a red [Rectangle](https://www.noesisengine.com/docs/Gui.Core._Rectangle.html). We set the Fill attribute to a predefined color name, which the XAML parser converts into a [SolidColorBrush](https://www.noesisengine.com/docs/Gui.Core._SolidColorBrush.html) appropriate for the Fill property.

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">
  <Rectangle Fill="Red" />
</Grid>
```

## Property Element Syntax

For some properties of an object element, attribute syntax is not possible, because the object or information necessary to provide the property value cannot be adequately expressed within the quotation mark and string restrictions of attribute syntax. For these cases, a different syntax known as property element syntax can be used.

The syntax for the property element start tag is <typeName.propertyName>. Generally, the content of that tag is an object element of the type that the property takes as its value . After specifying content, you must close the property element with an end tag. The syntax for the end tag is </typeName.propertyName>.

If an attribute syntax is possible, using the attribute syntax is typically more convenient and enables a more compact markup, but that is often just a matter of style, not a technical limitation. The following example shows the same properties being set as in the previous attribute syntax example, but this time by using property element syntax for all properties of the [Button](https://www.noesisengine.com/docs/Gui.Core._Button.html).

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">
  <Rectangle>
    <Rectangle.Fill>
      <SolidColorBrush Color="Red"/>
    </Rectangle.Fill>
  </Rectangle>
</Grid>
```

The next example creates a Rectangle, but instead of a simple red fill, it uses a gradient created by a LinearGradientBrush.

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">
  <!-- This rectangle is painted with a diagonal linear gradient. -->
  <Rectangle Width="200" Height="200">
    <Rectangle.Fill>
      <LinearGradientBrush StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="Yellow" Offset="0.0" />
        <GradientStop Color="Red" Offset="0.25" />
        <GradientStop Color="Blue" Offset="0.75" />
        <GradientStop Color="LimeGreen" Offset="1.0" />
      </LinearGradientBrush>
    </Rectangle.Fill>
  </Rectangle>
</Grid>
```

## Collection Syntax

The XAML language includes some optimizations that produce more human-readable markup. One such optimization is that if a particular property takes a collection type, then items that you declare in markup as child elements within that property's value become part of the collection. In this case a collection of child object elements is the value being set to the collection property.

The following example shows a [Grid](https://www.noesisengine.com/docs/Gui.Core._Grid.html) container that contains one element, a [Rectangle](https://www.noesisengine.com/docs/Gui.Core._Rectangle.html).

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">
  <Rectangle />
</Grid>
```

## XAML Content Properties

XAML specifies a language feature whereby a class can designate exactly one of its properties to be the XAML content property. Child elements of that object element are used to set the value of that content property. In other words, for the content property uniquely, you can omit a property element when setting that property in XAML markup and produce a more visible parent/child metaphor in the markup.

For example, [Border](https://www.noesisengine.com/docs/Gui.Core._Border.html) specifies a content property of Child. The following two Border elements are treated identically. The first one takes advantage of the content property syntax and omits the Border.Child property element. The second one shows Border.Child explicitly.

```xml
<Border>
  <TextBox Width="300"/>
</Border>
<!--explicit equivalent-->
<Border>
  <Border.Child>
    <TextBox Width="300"/>
  </Border.Child>
</Border>
```

If the property that is declared as the XAML content property is the Object type, or is type String, then the XAML content syntax supports what's basically inner text in the XML document model: a string between the opening and closing object tags. For example, the Text property in a [TextBlock](https://www.noesisengine.com/docs/Gui.Core._TextBlock.html) is used to set Text, but the string "Text" never appears in the markup. Here's an example usage:

```xml
<TextBlock>Hello!</TextBlock>
```

## Attribute Syntax (Events)

Attribute syntax can also be used for members that are events rather than properties. In this case, the attribute's name is the name of the event. What you're supplying here is the function name for an event handler function. That function must be defined in the [code-behind](https://www.noesisengine.com/docs/Gui.Core.CodeBehindTutorial.html) for the XAML page. For example, the following markup assigns a handler for the Click event to a [Button](https://www.noesisengine.com/docs/Gui.Core._Button.html) created in markup:

```xml
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      x:Class="ExampleNamespace.ExamplePage">
  <Button Click="Button_Click">Click Me!</Button>
</Page>
```

# Markup Extensions

Markup extensions are a XAML language concept. When used to provide the value of an attribute syntax, curly braces ({ and }) indicate a markup extension usage. This usage directs the XAML processing to escape from the general treatment of attribute values as either a literal string or a string-convertible value.

The most common markup extensions used in noesisGUI are [Binding](https://www.noesisengine.com/docs/Gui.Core._Binding.html), used for data binding expressions, and the resource references StaticResource and DynamicResource. By using markup extensions, you can use attribute syntax to provide values for properties even if that property does not support an attribute syntax in general. Markup extensions often use intermediate expression types to enable features such as deferring values or referencing other objects that are only present at run time.

For example, the following markup sets the value of the Style property using attribute syntax. The Style property takes an instance of the Style class, which by default could not be instantiated by an attribute syntax string. But in this case, the attribute references a particular markup extension, StaticResource. When that markup extension is processed, it returns a reference to a style that was previously instantiated as a keyed resource in a resource dictionary.

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <Grid.Resources>
    <SolidColorBrush x:Key="MyBrush" Color="Gold"/>
    <Style TargetType="Border" x:Key="PageBackground">
      <Setter Property="Background" Value="{StaticResource MyBrush}"/>
    </Style>
  </Grid.Resources>

  <Border Style="{StaticResource PageBackground}" />
</Grid>
```

# Type Converters

In the Attribute Syntax section, it was stated that the attribute value must be able to be set by a string. The basic, native handling of how strings are converted into other object types or primitive values is based on the String type itself. But many noesisGUI types or members of those types extend the basic string attribute processing behavior, in such a way that instances of more complex object types can be specified as strings and attributes.

The Thickness structure is an example of a type that has a type conversion enabled for XAML usages. Thickness indicates measurements within a nested rectangle and is used as the value for properties such as Margin. By placing a type converter on Thickness, all properties that use a Thickness are easier to specify in XAML because they can be specified as attributes. The following example uses a type conversion and attribute syntax to provide a value for a Margin:

```xml
<Button Margin="10,20,10,30" Content="Click me"/>
```

The previous attribute syntax example is equivalent to the following more verbose syntax example, where the Margin is instead set through property element syntax containing a Thickness object element. The four key properties of Thickness are set as attributes on the new instance:

```xml
<Button Content="Click me">
  <Button.Margin>
    <Thickness Left="10" Top="20" Right="10" Bottom="30"/>
  </Button.Margin>
</Button>
```

# XAML Root and Namespaces

A XAML file must have only one root element in order to be both a well-formed XML file and a valid XAML file. For typical scenarios, you use a root element that has a prominent meaning in the application model (for example, Window or Page for a page, ResourceDictionary for an external dictionary, or Application for the application definition). The following example shows the root element of a typical XAML file with the root element of Page.

```xml
<Page
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
</Page>
```

The root element also contains the attributes xmlns and xmlns:x. These attributes indicate to a XAML processor which XAML namespaces contain the type definitions for backing types that the markup will reference as elements. The xmlns attribute specifically indicates the default XAML namespace. Within the default XAML namespace, object elements in the markup can be specified without a prefix. For compatibility purpose the default XAML namespace is mapped to the WPF namespace http://schemas.microsoft.com/winfx/2006/xaml/presentation. The xmlns:x attribute indicates an additional XAML namespace, which maps the XAML language namespace http://schemas.microsoft.com/winfx/2006/xaml.

Note that the xmlns attributes are only strictly necessary on the root element of each XAML file, xmlns definitions will apply to all descendant elements of the root element.

## The x: Prefix

The following is a listing of the most common x: prefix programming constructs you will use:

- x:Key: Sets a unique key for each resource in a [ResourceDictionary](https://www.noesisengine.com/docs/Gui.Core._ResourceDictionary.html), x:Key will probably account for 90% of the x: usages you will see in a typical markup.
- x:Name: Add this attribute on any XAML object element where you want to be able to reference the created runtime instance as part of your code-behind logic.
- x:Class: Specifies the namespace and class name for the class that provides code-behind for a XAML page. You must have such a class to support code-behind, and therefore you almost always see x: mapped, even if there are no resources.
- x:Type: Constructs a Type reference based on a type name. This is used to specify attributes that take Type, such as Style::TargetType, although frequently the property has native string-to-Type conversion in such a way that the x:Type markup extension usage is optional.
- x:Null: If you ever need to specify a null value in XAML.

# Attached Properties and Events

XAML specifies a language feature that enables certain properties or events to be specified on any element, regardless of whether the property or event exists in the type's definitions for the element it is being set on. The properties version of this feature is called an attached property, the events version is called an attached event. Conceptually, you can think of attached properties and attached events as global members that can be set on any XAML element instance.

Attached properties in XAML are typically used through attribute syntax. In attribute syntax, you specify an attached property in the form ownerType.propertyName. The most common scenario for attached properties is to enable child elements to report a property value to their parent element:

```xml
<Canvas>
  <Button Canvas.Left="50">Hello</Button>
</Canvas>
```

## Additional Links

- [HOME](https://www.noesisengine.com/) - NoesisGUI
- [FEATURES](https://www.noesisengine.com/noesisgui) - NoesisGUI Features
- [STUDIO](https://www.noesisengine.com/studio) - NoesisGUI Studio
- [PRICING](https://www.noesisengine.com/licensing.php) - NoesisGUI Pricing
- [DEVELOPER](https://www.noesisengine.com/forums) - NoesisGUI Developer Resources
- [CONTACT](https://www.noesisengine.com/contact.php) - Noesis Contact
- [FORUMS](https://www.noesisengine.com/forums) - NoesisGUI Forums
- [SAMPLES](https://www.noesisengine.com/developers/samples.php) - NoesisGUI Samples
- [XAMLTOY](https://www.noesisengine.com/xamltoy) - NoesisGUI XamlToy
- [DOWNLOADS](https://www.noesisengine.com/developers/downloads.php) - NoesisGUI Downloads
- [DOCUMENTATION](https://www.noesisengine.com/docs/Gui.Core.Index.html) - NoesisGUI Documentation
- [BUGTRACKER](https://www.noesisengine.com/bugs/my_view_page.php) - NoesisGUI Bug Tracker
- [ROADMAP](https://www.noesisengine.com/bugs/roadmap_page.php) - roadmap

[NoesisGUI GitHub](https://github.com/Noesis)  
[NoesisGUI Linkedin](https://www.linkedin.com/company/noesis-technologies-sl)  
[NoesisGUI Twitter](https://twitter.com/noesisengine)  
[NoesisGUI Youtube](https://www.youtube.com/user/NoesisTechnologies)

© 2013 Noesis Technologies  
[Privacy](https://www.noesisengine.com/legal/privacy.php)  
[Terms & Conditions](https://www.noesisengine.com/legal/terms-of-use.php)