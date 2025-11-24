Source: https://www.noesisengine.com/docs/Gui.Core.BlendTutorial.html

# Blend Integration Tutorial

![github](/github/png.md) [Tutorial Data](https://github.com/Noesis/Tutorials/tree/master/Samples/BlendTutorial)

# Introduction

## What is Blend?

Microsoft Blend is a *visual tool* for creating eye candy, vector based, graphical *user interfaces*. You build an interface by drawing shapes and paths, drawing controls such as buttons and list boxes, making the pieces of your application respond to mouse clicks and other user input, and styling everything to look uniquely your own.

What you see on the design surface in Blend while you create your interface is what users will see when they run your application.

In Blend, you work on real pieces of a working application, but you can still draw and style everything as easily as you can in other illustration software, or event import your designs from other popular vector graphics tools like *Adobe Illustrator*. When you want to draw something that represents an interactive control, you can actually select an available control (such as a button or a list box) and then style it, or create your control from scratch; in any case, the powerful skinning mechanism will allow to fully customize the visual appearance.

## What does Blend produce?

Blend produces a visual design that is represented by a text file in [XAML](/Gui.Core/XamlIntroduction.md) format. Just as HTML is the markup language for web applications, XAML is the markup language for Blend applications. These XAML files, together with other resources such as images or fonts, will be the input of NoesisGUI applications.

This tutorial is based on *Microsoft Blend for Visual Studio*, and will show you how to use it to design application user interfaces to be imported and executed by NoesisGUI framework.

# Blend Editor

## Supported Assets

The following sections describe the functionality provided by Blend that is implemented by NoesisGUI. As NoesisGUI becomes more mature this subset will be increased with new releases.

### Controls

Blend has a huge control palette available to the user. At this time not all controls are supported in NoesisGUI framework, but a big set of the most important are ready to be used. The following chart shows a quick view of the main controls supported in the current version. For further info follow [Controls tutorial](/Gui.Core/ControlsTutorial.md).

> ![BlendTutorialImg1.png](/BlendTutorialImg1/png.md)

### Panels

Panels determine the layout (size and position) of their content, formed by other interface elements. Arranging user interface elements simply with static pixel-based coordinates and static pixel-based sizes can work in limited environments, but these types of interfaces can't correctly deal with different screen resolutions and dimensions, user settings such as font sizes, or content that changes in unpredictable ways (such as text being translated into different languages).

Blend defines a variety of panels enough to avoid the problems mentioned above and to create any type of application. NoesisGUI framework implements the following [Panel](/Gui.Core/_Panel.md) classes from among those provided by Blend. More information can be found in the [Layout and Panels tutorial](/Gui.Core/LayoutPanelTutorial.md).

> ![BlendTutorialImg2.png](/BlendTutorialImg2/png.md)

### Shapes

A [Shape](/Gui.Core/_Shape.md) is a basic 2D drawing that combines a [Geometry](/Gui.Core/_Geometry.md) with a [Pen](/Gui.Core/_Pen.md) (for drawing outlines) and a [Brush](/Gui.Core/_Brush.md) (for filling the geometry). Shapes can be directly placed in a user interface without custom code or a complex hierarchy of objects. Shape objects share the following common properties.

- **Fill**: describes how the interior of the shape is painted.
- **Stroke**: describes how the shape's outline is painted.
- **StrokeThickness**: describes the thickness of the shape's outline.
- **Strecth**: describes how the shape stretches to fill the available space in its container.

NoesisGUI implements the following shapes. For further info follow [Shapes tutorial](/Gui.Core/ShapesTutorial.md).

> ![BlendTutorialImg3.png](/BlendTutorialImg3/png.md)

Note

Virtually all shapes are supported because all of them can be converted to Path by clicking on the shape and doing 'Path -> Convert to Path'. Follow this approach if you need a Shape that is not supported by Noesis.

### Behaviors

[Behaviors](/App.Interactivity/Behaviors.md) are reusable pieces of packaged code that can be dragged onto any object and then fine-tuned by changing their properties to add interactivity to your application. Behaviors have a *trigger*, an *action* and usually a target:

- The *trigger* is the event that invokes the behavior. The most useful triggers are user interface control events (like clicking) and those invoked by changes to system states (like storyboards ending or properties changing).
- The *action* specifies what the behavior should do. For example, an action might be to run a storyboard, or change a property of an element.
- The *target* is the element which the behavior will act upon.

The following *Behaviors* classes are implemented in NoesisGUI. More information can be found in the [Interactivity tutorial](/App.Interactivity/Behaviors.md).

> ![BlendTutorialImg30.png](/BlendTutorialImg30/png.md)

### Effects

Effects are simple pixel processing operations. An effect takes a bitmap source as an input and produces a new bitmap after applying the effect, such as a blur or drop shadow. Each effect exposes properties to control it.

Effects can be applied to [UIElement](/Gui.Core/_UIElement.md) objects, such as a [Button](/Gui.Core/_Button.md) or [TextBox](/Gui.Core/_TextBox.md). When you set an effect to a layout container, such as [DockPanel](/Gui.Core/_DockPanel.md) or [Canvas](/Gui.Core/_Canvas.md), the effect is applied to the visual tree of the element or visual, including all of its child elements.

The architecture to support effects is not yet implemented by NoesisGUI.

## Supported Project Types

When creating a new project, Blend shows the following dialog:

![BlendTutorialImg4.png](/BlendTutorialImg4/png.md)

There are several types of technologies supported by Blend: *WPF*, *Silverlight* and *UWP*. Microsoft designed *WPF* to provide a consistent programming model for the development of desktop applications. *Silverlight* was created later to bring the power of *WPF* to the web. *Silverlight* defines a simpler runtime but in comparison to *WPF* it has a few differences: it implements less controls, it has more limited styling capabilities (triggers), however includes a new property that simulates 3D transformations applied to graphic elements, the *Projection* property.

Currently NoesisGUI supports the creation of *WPF* and *Silverlight* projects from Blend.

For this tutorial we will create a fully functional application using the [application framework](/Gui.Core/ApplicationTutorial.md).

## Creating Main Window UI

Use Blend to add and organize controls and graphical elements within the application main window (if you are not familiar with this tool, you should read this [Blend user guide](https://docs.microsoft.com/en-us/visualstudio/designers/creating-a-ui-by-using-blend-for-visual-studio) to learn the basics on how to use it). Controls and other elements can be selected in Blend from the *Assets* tab or directly from the appropriate buttons on the left tool bar.

After some work we ended with something similar to this:

![BlendTutorialImg5.png](/BlendTutorialImg5/png.md)

## Control Styling

It's important to understand the different techniques to change the visual appearance of an element. *Style*, *Template* and *Theme* are the base concepts to unveil and master the customization capabilities that XAML has to offer. We recommend reading this brief [introduction to Styles and Templates](/Gui.Core/StylingTutorial.md), along as the Blend documentation about the matter.

For our application we can add a personal look by adding our custom control styles. To organize resources we will create a new [ResourceDictionary](/Gui.Core/_ResourceDictionary.md) and place all style definitions there:

![BlendTutorialImg6.png](/BlendTutorialImg6/png.md)
![BlendTutorialImg7.png](/BlendTutorialImg7/png.md)

We will begin style edition by selecting one of the window controls, the "AddButton" for example, and then go to the *Format* menu -> *Edit Style* -> *Create Empty...*

![BlendTutorialImg8.png](/BlendTutorialImg8/png.md)

Then we customize button style by setting some properties. And finally we create the button template that will give our personal appearance to the button.

![BlendTutorialImg9.png](/BlendTutorialImg9/png.md)
![BlendTutorialImg10.png](/BlendTutorialImg10/png.md)

After creating and editing the styles and templates of all the controls we are using, our main window looks like this:

![BlendTutorialImg11.png](/BlendTutorialImg11/png.md)

## User Controls

Sometimes we need to create controls that can be reused in other applications. In this case it is best to create a user control consisting of standard controls, so that control can assimilate the appearance of the application where it is used, while maintaining the logic needed to operate unchanged. Now we will add a [UserControl](/Gui.Core/_UserControl.md) for our application to define a color selector:

![BlendTutorialImg6.png](/BlendTutorialImg6/png.md)
![BlendTutorialImg12.png](/BlendTutorialImg12/png.md)

The user control appearance is defined by the composition of standard controls. Then we add the logic to manage the color selector, and the control is ready to use in our application:

![BlendTutorialImg13.png](/BlendTutorialImg13/png.md)

More detailed information is available in the [user controls](/Gui.Core/UserControlTutorial.md) tutorial.

## Fonts

NoesisGUI framework allows the use of local resource [fonts](/Gui.Core/TextTutorial.md) in your application. First you need to include the font in your project:

![BlendTutorialImg14.png](/BlendTutorialImg14/png.md)

Then the font can be referenced in the XAML as a local resource:

```
<Window FontFamily="Fonts/#WeblySleek UI Normal">
```

## Animation

Animation can make an attractive user interface even more spectacular and usable. By just animating a background color or applying an animated transform, you can create dramatic screen transitions or provide helpful visual cues.

Using a tool like Blend eases this process even more. What follows next is a brief introduction to the animation system using Blend.

More information about animations in NoesisGUI can be found in the [animation tutorial](/Gui.Core/AnimationTutorial.md)

### The Storyboard

All the animations created from Blend are based on a timeline called [Storyboard](/Gui.Animation/_Storyboard.md). Inside a *Storyboard*, animation changes are inserted like in a music score, using groups of keyframes that affect a number of properties. The animation tells which property is going to be animated, and the keyframes inside the animation specify which value is going to take the property over the time.

### Where to apply a storyboard

Storyboards can be applied in 3 situations:

- As a response to a *routed event* (using an [EventTrigger](/Gui.Core/_EventTrigger.md), both used directly over a [FrameworkElement](/Gui.Core/_FrameworkElement.md) or inside a [Style](/Gui.Core/_Style.md) or [Template](/Gui.Core/_FrameworkTemplate.md)).

> ```
> <Button Content="Button">
>   <Button.Triggers>
>     <EventTrigger RoutedEvent="Button.Click">
>       <BeginStoryboard>
>         <Storyboard .../>
>       </BeginStoryboard>
>     </EventTrigger>
>   </Button.Triggers>
> </Button>
> ```
>
> ```
> <Style TargetType="Rectangle">
>   <Style.Triggers>
>     <EventTrigger RoutedEvent="UIElement.MouseEnter">
>       <BeginStoryboard>
>         <Storyboard .../>
>      </BeginStoryboard>
>     </EventTrigger>
>   </Style.Triggers>
> </Button>
> ```

- As a response to the activation or deactivation of a *property* (inside a *Style* or a *Template*).

> ```
> <Style TargetType="Rectangle">
>   <Style.Triggers>
>     <Trigger Property="IsMouseOver">
>       <Trigger.EnterActions>
>         <BeginStoryboard>
>           <Storyboard .../>
>         </BeginStoryboard>
>       </Trigger.EnterActions>
>     </Trigger>
>   </Style.Triggers>
> </Button>
> ```
>
> ```
> <ControlTemplate TargetType="Button">
>   <Border x:Name="border" .../>
>   <ControlTemplate.Triggers>
>     <Trigger Property="IsMouseOver">
>       <Trigger.EnterActions>
>         <BeginStoryboard>
>           <Storyboard .../>
>         </BeginStoryboard>
>       </Trigger.EnterActions>
>     </Trigger>
>   </ControlTemplate.Triggers>
> </ControlTemplate>
> ```

- In a *visual state* (inside a *Template*).

> ```
> <ControlTemplate TargetType="Button">
>   <Border x:Name="border">
>     <VisualStateManager.VisualStateGroups>
>       <VisualStateGroup x:Name="CommonStates">
>         <VisualState x:Name="Normal"/>
>         <VisualState x:Name="MouseOver">
>           <Storyboard .../>
>         </VisualState>
>         <VisualState x:Name="Pressed"/>
>       </VisualStateGroup>
>     </VisualStateManager.VisualStateGroups>
>     ...
>   </Border>
> </ControlTemplate>
> ```

### A simple animation

Let's take a simple [Rectangle](/Gui.Core/_Rectangle.md) to make some animations to it.

![BlendTutorialAnimationImg1.png](/BlendTutorialAnimationImg1/png.md)

After drawing the rectangle, go to the *Objects and Timeline* window, and click on the *New* button on the right to create a new *Storyboard*.

![BlendTutorialAnimationImg2.png](/BlendTutorialAnimationImg2/png.md)

Give a name to the *Storyboard* and create it.

![BlendTutorialAnimationImg3.png](/BlendTutorialAnimationImg3/png.md)

Now in the *Objects and Timeline* window the newly created storyboard appears. Moving the time bar in the timeline sets the exact time when property changes will be executed during the animation

![BlendTutorialAnimationImg4.png](/BlendTutorialAnimationImg4/png.md)

When a new animation is created, Blend enters in the recording state automatically. This means that any change made in the design window or in the element properties are being recorded into the animation timeline, just in the time where the time bar is pointing.

![BlendTutorialAnimationImg5.png](/BlendTutorialAnimationImg5/png.md)

Now we can start animating our rectangle. We are going to start changing the color of the background to red at time 0, and then we want to start a progressive change to green for 1 second. So we move the time bar to time 0 seconds, and change the background property to red value while the recording button is still active (in red). The change in the background property is registered in the timeline as a new [KeyFrame](/Gui.Animation/_BaseKeyFrame.md) in the position where the time bar is located at that exact moment.

![BlendTutorialAnimationImg6.png](/BlendTutorialAnimationImg6/png.md)

To insert the green color value we move the time bar to 1 second and change the color of the rectangle. Blend will represent this in the timeline as a continous line.

![BlendTutorialAnimationImg7.png](/BlendTutorialAnimationImg7/png.md)

Once a *KeyFrame* is inserted, the transition from the previous one can be modified selecting the keyframe in the timeline window and changing the [KeySpline](/Gui.Animation/_KeySpline.md) or [EasingFunction](/Gui.Animation/_EasingFunctionBase.md).

With the *KeySpline* window the transition curve can be fine tuned to the user desires. In this example we create a transition that starts to change slowly, then in the middle of the transition it speeds up, and finally it ends reaching the next *KeyFrame* value slowly again.

![BlendTutorialAnimationImg8.png](/BlendTutorialAnimationImg8/png.md)

With the *EasingFunction* window the user can choose between a number of predefined effects that affects the exit from the previous *KeyFrame* to the selected one (*In*), the entrance to the new *KeyFrame* value (*Out*) or both (*InOut*).

![BlendTutorialAnimationImg9.png](/BlendTutorialAnimationImg9/png.md)

Some of the predefined effects have additional values that can be tweaked by the user.

![BlendTutorialAnimationImg10.png](/BlendTutorialAnimationImg10/png.md)

We can also control the number of repetions that the animation is going to be executed. For this, we can right click over the animated property in the timeline.

![BlendTutorialAnimationImg11.png](/BlendTutorialAnimationImg11/png.md)

And set the number of repetitions, or select *Forever* so the animation is playing countinously

![BlendTutorialAnimationImg12.png](/BlendTutorialAnimationImg12/png.md)

Finally, we can assign the animation to an [EventTrigger](/Gui.Core/_EventTrigger.md) so it starts, for example, when the mouse enters the rectangle. We can use the *Triggers* panel for this.

![BlendTutorialAnimationImg13.png](/BlendTutorialAnimationImg13/png.md)

### Animations using VisualStates

The [VisualState](/Gui.Animation/_VisualState.md) system is a powerful mechanism to change and animate properties based on the internal state of objects. The states are hard-coded inside every control, and the template elements can react to the states using animations that play when a change between states occurs.

For our example, we put a button into the design view, and then we edit its template. The *States* panel will show something like this.

![BlendTutorialAnimationImg14.png](/BlendTutorialAnimationImg14/png.md)

Selecting the *Normal* state we could create the default template we are going to use for our *Button*. In this case, a gray rounded rectangle is drawn.

![BlendTutorialAnimationImg15.png](/BlendTutorialAnimationImg15/png.md)

Now we want that when the button is in the *MouseOver* state, the color of our background changes to dark gray. So we select the *MouseOver* state, and as the recoding button is active (exactly the same as when we were creating an animation) we can change the value of the ellipse to blue, so Blend detects the change and creates a new storyboard for the *MouseOver* state. In this case, Blend assigns the *MouseOver* name to the storyboard, because it's going to be executed only when the button enters in that state.

![BlendTutorialAnimationImg16.png](/BlendTutorialAnimationImg16/png.md)

VisualStates provides a very easy and powerful way to create animations. Beside the Storyboard that is played for every state, a dynamic animation is created to make a smooth transition between the property values set in every state. The duration of this dynamic animation and the curve that is applied to make the transitions between states can be controlled using the *Default transition* icon present in every group of VisualStates. For example, if we want a transition time of 0.5s using a Bounce animation curve, we could enter the following values.

![BlendTutorialAnimationImg17.png](/BlendTutorialAnimationImg17/png.md)

And even the transition values between specific states could be introduced. This allows even more control on the animations. For example, we could specify a different duration and effect for the transition from *Normal* to *MouseOver*

![BlendTutorialAnimationImg18.png](/BlendTutorialAnimationImg18/png.md)

We used some animations in our control templates to add more appeal to our application appearance.

# C++ Implementation

Now that all design and artwork is completed we have to implement the logic. Blend creates two types of files for every item that is added to the project: a XAML file and a C# file that is usually called [code-behind](/Gui.Core/CodeBehindTutorial.md). A matching class to the element defined in the XAML is created along with the methods that will respond to the desired events. The user is free to modify this code and add the logic to be executed as response to the events, or even add any other method or property that is required by the application. This powerful feature of separating visual definition from logic code allows a efficient workflow because programmers and designers can work separately on each part.

For NoesisGUI to work, we need to translate that C# [code-behind](/Gui.Core/CodeBehindTutorial.md) to C++, and the first step will be to create a [Noesis component](/Gui.Core/ExtendingTutorial.md) that matches each class created by Blend.

## Application

In our tutorial we have an *Application* derived class that contains the *App.xaml* code behind. That file was created automatically by Blend and can be modified using Blend code editor:

App.xaml.cs

```
using System.Windows;

namespace BlendTutorial
{
    /// <summary>
    /// Interaction logic for App.xaml
    /// </summary>
    public partial class App : Application
    {
    }
}
```

The *App.xaml* refers to this class using the *x:Class* extension. And, as we can see, it follows the form *Namespace.ClassName*:

App.xaml

```
<Application
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      x:Class="BlendTutorial.App"
      StartupUri="MainWindow.xaml">
  <Application.Resources>
    <ResourceDictionary>
      <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="Resources.xaml"/>
      </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
  </Application.Resources>
</Application>
```

To match that class we have to create a C++ component that derives from *Application* and that has *BlendTutorial.App* as TypeId.

```
namespace BlendTutorial
{

class App final: public Application
{
    NS_IMPLEMENT_INLINE_REFLECTION(App, Application)
    {
        NsMeta<TypeId>("BlendTutorial.App");
    }
};

}
```

## MainWindow

For the *MainWindow.xaml* file, Blend created a Window derived class and added an event handler for each event managed by the class:

MainWindow.xaml

```
<Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:BlendTutorial" mc:Ignorable="d"
        x:Class="BlendTutorial.MainWindow"
        x:Name="Window"
        Title="Noesis - Getting started with Blend"
        Width="800" Height="480" Background="Gray" UseLayoutRounding="True"
        FontFamily="Fonts/#WeblySleek UI Normal">

  <Grid x:Name="LayoutRoot">
    <Grid.ColumnDefinitions>
      <ColumnDefinition Width="8*"/>
      <ColumnDefinition Width="2*"/>
    </Grid.ColumnDefinitions>
    <Border x:Name="ContainerBorder" BorderBrush="DimGray" BorderThickness="1" Margin="10"
            CornerRadius="2" Background="White" Padding="1" ClipToBounds="True"
            PreviewMouseLeftButtonDown="ContainerBorder_MouseDown">
      <Canvas x:Name="ContainerCanvas"/>
    </Border>
    <Viewbox Grid.Column="1" VerticalAlignment="Top">
      <StackPanel Margin="0,10,10,10" Width="150">
        <Button x:Name="AddButton" Content="Add" Margin="0,0,0,3" Click="AddButton_Click"/>
        <Button x:Name="RemoveButton" Content="Remove" Margin="0,0,0,10"
                Click="RemoveButton_Click"/>
        <Expander Header="Position" Margin="0,0,0,10" IsExpanded="True">
          <Grid Margin="5">
            <Grid.ColumnDefinitions>
              <ColumnDefinition/>
              <ColumnDefinition Width="2*"/>
            </Grid.ColumnDefinitions>
            <Grid.RowDefinitions>
              <RowDefinition/>
              <RowDefinition/>
            </Grid.RowDefinitions>
            <TextBlock Text="Left " VerticalAlignment="Center" HorizontalAlignment="Right"
                       Margin="0"/>
            <Slider x:Name="PositionLeft" Margin="0,0,0,3" Grid.Column="1"
                    Maximum="{Binding ActualWidth, ElementName=ContainerCanvas}"
                    LargeChange="10" SmallChange="1"/>
            <TextBlock Text="Top " VerticalAlignment="Center" HorizontalAlignment="Right"
                       Grid.Row="1"/>
            <Slider x:Name="PositionTop" Margin="0,0,0,3" Grid.Column="1" Grid.Row="1"
                    Maximum="{Binding ActualHeight, ElementName=ContainerCanvas}"
                    LargeChange="10" SmallChange="1"/>
          </Grid>
        </Expander>
        <Expander Header="Size" Margin="0,0,0,10" IsExpanded="True">
          <Grid Margin="5">
            <Grid.ColumnDefinitions>
              <ColumnDefinition/>
              <ColumnDefinition Width="2*"/>
            </Grid.ColumnDefinitions>
            <Grid.RowDefinitions>
              <RowDefinition/>
              <RowDefinition/>
            </Grid.RowDefinitions>
            <TextBlock Text="Width " VerticalAlignment="Center" HorizontalAlignment="Right"
                       Margin="0"/>
            <Slider x:Name="SizeWidth" Grid.Column="2" Margin="0,0,0,3" LargeChange="10"
                    SmallChange="1" Maximum="200" Minimum="10"/>
            <TextBlock Text="Height " VerticalAlignment="Center" HorizontalAlignment="Right"
                       Grid.Row="1"/>
            <Slider x:Name="SizeHeight" Grid.Column="2" Grid.Row="1" LargeChange="10"
                    SmallChange="1" Maximum="200" Minimum="10"/>
          </Grid>
        </Expander>
        <Expander Header="Color" Margin="0,0,0,10" IsExpanded="True">
          <StackPanel Margin="5" Orientation="Vertical" ToggleButton.Checked="RadioButton_Checked">
            <RadioButton x:Name="FillSelected" Content="Fill" IsChecked="True"/>
            <RadioButton x:Name="StrokeSelected" Content="Stroke" Margin="0,0,0,3"/>
            <local:ColorSelector x:Name="ColorSelect"/>
          </StackPanel>
        </Expander>
      </StackPanel>
    </Viewbox>
  </Grid>
</Window>
```

MainWindow.xaml.cs

```
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Media;
using System.Windows.Shapes;
using System.Windows.Input;

namespace BlendTutorial
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            this.InitializeComponent();
        }

        private void AddButton_Click(object sender, RoutedEventArgs e)
        {
        }

        private void RemoveButton_Click(object sender, RoutedEventArgs e)
        {
        }

        private void ContainerBorder_MouseDown(object sender, MouseButtonEventArgs e)
        {
        }

        private void RadioButton_Checked(object sender, RoutedEventArgs e)
        {
        }
    }
}
```

To match that class we have to create a C++ component that derives from *Window* and that has *BlendTutorial.MainWindow* as TypeId. In addition, we must [connect](/Gui.Core/EventsTutorial.md) the functions that match the event handlers defined in MainWindow.xaml file:

```
namespace BlendTutorial
{

class MainWindow final: public Window
{
public:
    MainWindow()
    {
        InitializeComponent();
    }

private:
    void InitializeComponent()
    {
        Noesis::GUI::LoadComponent(this, "MainWindow.xaml");
    }

    bool ConnectEvent(BaseComponent* source, const char* event, const char* handler) override
    {
        NS_CONNECT_EVENT(Button, Click, AddButton_Click);
        NS_CONNECT_EVENT(Button, Click, RemoveButton_Click);
        NS_CONNECT_EVENT(Border, PreviewMouseLeftButtonDown, ContainerBorder_MouseDown);
        NS_CONNECT_ATTACHED_EVENT(ToggleButton, Checked, RadioButton_Checked);
        return false;
    }

    void AddButton_Click(BaseComponent*, const RoutedEventArgs&)
    {
    }

    void RemoveButton_Click(BaseComponent*, const RoutedEventArgs&)
    {
    }

    void ContainerBorder_MouseDown(BaseComponent*, const MouseButtonEventArgs&)
    {
    }

    void RadioButton_Checked(BaseComponent*, const RoutedEventArgs&)
    {
    }

    NS_IMPLEMENT_INLINE_REFLECTION(MainWindow, Window)
    {
        NsMeta<TypeId>("BlendTutorial.MainWindow");
    }
};
```

Named elements of the XAML file can be stored during element initialization to facilitate logic implementation:

```
namespace BlendTutorial
{

class MainWindow final: public Window
{
public:
    MainWindow()
    {
        InitializeComponent();
    }

private:
    void InitializeComponent()
    {
        Noesis::GUI::LoadComponent(this, "MainWindow.xaml");

        _containerCanvas = FindName<Canvas>("ContainerCanvas"); NS_ASSERT(_containerCanvas != 0);
        _positionLeft = FindName<Slider>("PositionLeft"); NS_ASSERT(_positionLeft != 0);
        _positionTop = FindName<Slider>("PositionTop"); NS_ASSERT(_positionTop != 0);
        _sizeWidth = FindName<Slider>("SizeWidth"); NS_ASSERT(_sizeWidth != 0);
        _sizeHeight = FindName<Slider>("SizeHeight"); NS_ASSERT(_sizeHeight != 0);
        _fillSelected = FindName<RadioButton>("FillSelected"); NS_ASSERT(_fillSelected != 0);
    }

    Canvas* _containerCanvas;
    Slider* _positionLeft;
    Slider* _positionTop;
    Slider* _sizeWidth;
    Slider* _sizeHeight;
    RadioButton* _fillSelected;
};
```

## ColorSelector

The last class created by Blend is the one associated with our *ColorSelector* user control.

ColorSelector.xaml

```
 <UserControl
     xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
     xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
     xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d"
     x:Class="BlendTutorial.ColorSelector"
     x:Name="ColorSelectorRoot"
     Foreground="{StaticResource BlendTutorialForeground}"
     Slider.ValueChanged="Slider_ValueChanged"
     d:DesignWidth="200" d:DesignHeight="100">

     <Grid x:Name="LayoutRoot">
         <Grid.RowDefinitions>
             <RowDefinition Height="*"/>
             <RowDefinition Height="*"/>
             <RowDefinition Height="*"/>
             <RowDefinition Height="*"/>
         </Grid.RowDefinitions>
         <Grid.ColumnDefinitions>
             <ColumnDefinition Width="1*"/>
             <ColumnDefinition Width="2*"/>
         </Grid.ColumnDefinitions>
         <Rectangle RadiusX="2" RadiusY="2" Grid.RowSpan="4" Margin="0,0,5,0">
             <Rectangle.Fill>
                 <LinearGradientBrush StartPoint="0,0" EndPoint="0,15" MappingMode="Absolute"
                                      SpreadMethod="Repeat">
                     <GradientStop Color="Gray" Offset="0"/>
                     <GradientStop Color="Silver" Offset="0.5"/>
                     <GradientStop Color="White" Offset="0.5001"/>
                     <GradientStop Color="Gainsboro" Offset="1"/>
                 </LinearGradientBrush>
             </Rectangle.Fill>
         </Rectangle>
         <Rectangle x:Name="ColorRect" Fill="{Binding Color, ElementName=ColorSelectorRoot}"
                    Stroke="{StaticResource BlendTutorialBorderBrush}" RadiusX="2" RadiusY="2"
                    Grid.RowSpan="4" Margin="0,0,5,0"/>
         <Slider x:Name="R" Grid.Column="1" Grid.Row="0" VerticalAlignment="Center"
                 Margin="10,1,0,1" Maximum="255" LargeChange="10" SmallChange="1"/>
         <Slider x:Name="G" Grid.Column="1" Grid.Row="1" VerticalAlignment="Center"
                 Margin="10,1,0,1" Maximum="255" LargeChange="10" SmallChange="1"/>
         <Slider x:Name="B" Grid.Column="1" Grid.Row="2" VerticalAlignment="Center"
                 Margin="10,1,0,1" Maximum="255" LargeChange="10" SmallChange="1"/>
         <Slider x:Name="A" Grid.Column="1" Grid.Row="3" VerticalAlignment="Center"
                 Margin="10,1,0,1" Maximum="255" SmallChange="1" LargeChange="10" Value="255"/>
         <TextBlock Text="R" Grid.Column="1" HorizontalAlignment="Left"
                    VerticalAlignment="Center"/>
         <TextBlock Text="G" Grid.Column="1" HorizontalAlignment="Left"
                    VerticalAlignment="Center" Grid.Row="1"/>
         <TextBlock Text="B" Grid.Column="1" HorizontalAlignment="Left"
                    VerticalAlignment="Center" Grid.Row="2"/>
         <TextBlock Text="A" Grid.Column="1" HorizontalAlignment="Left"
                    VerticalAlignment="Center" Grid.Row="3"/>
     </Grid>
 </UserControl>
```

ColorSelector.xaml.cs

```
using System;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Media;

namespace BlendTutorial
{
    /// <summary>
    /// Interaction logic for ColorSelector.xaml
    /// </summary>
    public partial class ColorSelector : UserControl
    {
        public ColorSelector()
        {
            this.InitializeComponent();
        }

        public static DependencyProperty ColorProperty = DependencyProperty.Register("Color",
            typeof(SolidColorBrush), typeof(ColorSelector),
            new PropertyMetadata(null, new PropertyChangedCallback(OnColorChanged)));

        public SolidColorBrush Color
        {
            get { return (SolidColorBrush)GetValue(ColorProperty); }
            set { SetValue(ColorProperty, value); }
        }

        private static void OnColorChanged(object sender,
            System.Windows.DependencyPropertyChangedEventArgs e)
        {
        }

        private void Slider_ValueChanged(object sender,
            System.Windows.RoutedPropertyChangedEventArgs<double> e)
        {
        }
    }
}
```

To match that user control we have to create a C++ component that derives from *UserControl* and that has *BlendTutorial.ColorSelector* as TypeId. We must connect the function that manages changes in the sliders, and register the dependency property defined by the ColorSelector.

```
namespace BlendTutorial
{

class ColorSelector final: public UserControl
{
public:
    ColorSelector()
    {
        InitializeComponent();
    }

    SolidColorBrush* GetColor() const
    {
        return GetValue<Ptr<SolidColorBrush>>(ColorProperty);
    }

    void SetColor(SolidColorBrush* color)
    {
        SetValue<Ptr<SolidColorBrush>>(ColorProperty, color);
    }

public:
    static const DependencyProperty* ColorProperty;

private:
    void InitializeComponent()
    {
        Noesis::GUI::LoadComponent(this, "ColorSelector.xaml");
    }

    bool ConnectEvent(BaseComponent* source, const char* event, const char* handler) override
    {
        NS_CONNECT_EVENT(Slider, ValueChanged, Slider_ValueChanged);
        return false;
    }

    static void OnColorChanged(DependencyObject* d, const DependencyPropertyChangedEventArgs& /*e*/)
    {
    }

    void Slider_ValueChanged(BaseComponent*, const RoutedPropertyChangedEventArgs<float>&)
    {
    }

    NS_IMPLEMENT_INLINE_REFLECTION(ColorSelector, UserControl)
    {
        NsMeta<TypeId>("BlendTutorial.ColorSelector");

        UIElementData* data = NsMeta<UIElementData>(TypeOf<SelfClass>());
        data->RegisterProperty<Ptr<SolidColorBrush>>(ColorProperty, "Color",
            PropertyMetadata::Create(Brushes::Transparent()->Clone(),
                &ColorSelector::OnColorChanged));
    }
};
```