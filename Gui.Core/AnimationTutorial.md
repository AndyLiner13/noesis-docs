# Animation Tutorial

![github](https://www.noesisengine.com/docs/github.png)

[Tutorial Data](https://github.com/Noesis/Tutorials/tree/master/Snippets/Animation)

Animation functionality makes it very straightforward to add dynamic effects to your applications or components. Animation might not be appropriate for every piece of software, but there are many situations that can benefit from its reasonable use to enhance the viewing experience of the user. When exposed via design tools like Microsoft Expression Blend, noesisGUI's animation support provides capabilities much like Adobe Flash. But because it's a core part with APIs that are fairly simple, you can easily create a wide range of animations without the help of such a tool.

On this tutorial we demonstrate how to create some simple animations to bring life into your interface.

# Animations in XAML

We can start with a simple rectangle in the middle of the screen.

![AnimationTutorialImg1.jpg](https://www.noesisengine.com/docs/AnimationTutorialImg1.jpg)

```xml
<Canvas
 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
 Height="100" Width="500">
   <Rectangle Width="100" Height="60" Margin="60" Fill="YellowGreen"/>
</Canvas>
```

Animations are specified in XAML using [Storyboard](https://www.noesisengine.com/docs/Gui.Animation._Storyboard.html) objects. A Storyboard defines a timeline of property modifications that will be applied to interface elements over time. But, where should they be placed in order to be fired? An animation can begin in response to an event, for example, a button click. So, the next step should be to add a button to our example:

![AnimationTutorialImg2.jpg](https://www.noesisengine.com/docs/AnimationTutorialImg2.jpg)

```xml
<Canvas
 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
 Height="100" Width="500">
    <Rectangle Width="100" Height="60" Margin="60" Fill="YellowGreen"/>
    <Button Content="Start Animation" Margin="10" HorizontalAlignment="Left" VerticalAlignment="Top"/>
</Canvas>
```

Every control can define a set of actions that are executed in response to a routed event. They are called event triggers, and can be specified in the Triggers property of any control. So if we want to launch an animation when the button in the sample is clicked we should add the following code to the XAML:

```xml
<Canvas
 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
 Height="100" Width="500">
    <Rectangle Width="100" Height="60" Margin="60" Fill="YellowGreen"/>
    <Button Content="Start Animation" Margin="10" HorizontalAlignment="Left" VerticalAlignment="Top">
        <Button.Triggers>
            <EventTrigger RoutedEvent="Button.Click"/>
        </Button.Triggers>
    </Button>
</Canvas>
```

The action that launches an animation is represented by the [BeginStoryboard](https://www.noesisengine.com/docs/Gui.Animation._BeginStoryboard.html) class, and it defines a simple Storyboard property where the animation is specified.

```xml
<Canvas
 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
 Height="100" Width="500">
    <Rectangle Width="100" Height="60" Margin="60" Fill="YellowGreen"/>
    <Button Content="Start Animation" Margin="10" HorizontalAlignment="Left" VerticalAlignment="Top">
        <Button.Triggers>
            <EventTrigger RoutedEvent="Button.Click">
                <BeginStoryboard>
                    <!-- Storyboard property is the content property of BeginStoryboard -->
                    <!-- class, so we don't need to make it explicit in the code -->
                    <Storyboard />
                </BeginStoryboard>
            </EventTrigger>
        </Button.Triggers>
    </Button>
</Canvas>
```

The first animation we could add can be moving the rectangle within the screen. We can do that by applying a [TranslateTransform](https://www.noesisengine.com/docs/Gui.Core._TranslateTransform.html) to the RenderTransform property of the rectangle. But we need a way to refer to the rectangle from the animation timeline, and this is obviously done by setting the Name of the rectangle element. The example will look now like this:

```xml
<Canvas
 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
 Height="100" Width="500">
  <Rectangle x:Name="Rect" Width="100" Height="60" Margin="60" Fill="YellowGreen" RenderTransformOrigin="0.5,0.5">
    <Rectangle.RenderTransform>
      <TranslateTransform X="0" Y="0"/>
    </Rectangle.RenderTransform>
  </Rectangle>
  <Button Content="Start Animation" Margin="10" HorizontalAlignment="Left" VerticalAlignment="Top">
    <Button.Triggers>
      <EventTrigger RoutedEvent="Button.Click">
        <BeginStoryboard>
          <Storyboard TargetName="Rect"
            TargetProperty="(UIElement.RenderTransform).(TranslateTransform.X)">
            <DoubleAnimation Duration="0:0:1" From="0" To="50"/>
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger>
    </Button.Triggers>
  </Button>
</Canvas>
```

Now, when the user clicks the button, the green rectangle is displaced horizontally to the right by 50 pixels during one second. You can read [Animation](https://www.noesisengine.com/docs/Gui.Animation.Introduction.html) reference to obtain full information about the properties that are available to customize animations (begin time, auto reverse, repeat behavior, etc.).

In case we want to animate more than one property of the same object or from different objects, we can benefit of the attached behavior of TargetProperty and TargetName properties. For example, to fade out the rectangle while it is being moved we could add the following:

```xml
<Canvas
 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
 Height="100" Width="500">
  <Rectangle x:Name="Rect" Width="100" Height="60" Margin="60" Fill="YellowGreen" RenderTransformOrigin="0.5,0.5">
    <Rectangle.RenderTransform>
      <TranslateTransform X="0" Y="0"/>
    </Rectangle.RenderTransform>
  </Rectangle>
  <Button Content="Start Animation" Margin="10" HorizontalAlignment="Left" VerticalAlignment="Top">
    <Button.Triggers>
      <EventTrigger RoutedEvent="Button.Click">
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Duration="0:0:1" From="0" To="50"
              Storyboard.TargetName="Rect"
              Storyboard.TargetProperty="(UIElement.RenderTransform).(TranslateTransform.X)"/>
            <DoubleAnimation Duration="0:0:1" From="1" To="0"
              Storyboard.TargetName="Rect"
              Storyboard.TargetProperty="(Shape.Fill).(Brush.Opacity)"/>
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger>
    </Button.Triggers>
  </Button>
</Canvas>
```

![AnimationTutorialImg3.jpg](https://www.noesisengine.com/docs/AnimationTutorialImg3.jpg)

**NOTE**

Animations can also be launched automatically when a XAML is loaded. This can be achieved by using the FrameworkElement.Loaded routed event instead of responding to a Button.Click event.

# Keyframe animations

The normal animation classes only support linear interpolation from one value to another (or limited forms of nonlinear interpolation thanks to AccelerationRatio and DecelerationRatio properties). If you want to represent a more complicated animation, you can specify keyframes, which provide specific values at specific times. The use of keyframes requires a keyframe-enabled animation class. For example, [Double Animation](https://www.noesisengine.com/docs/Gui.Animation._DoubleAnimation.html) has a companion class called [DoubleAnimationUsingKeyFrames](https://www.noesisengine.com/docs/Gui.Animation._DoubleAnimationUsingKeyFrames.html), as do all the other animation classes.

The keyframe animation classes have the same properties and events as their counterparts, except for the From, To, and By properties. Instead, they have a KeyFrames collection that can hold keyframe instances specific to the type being animated. There are three kinds of keyframes: Linear, Spline and Discrete.

## Linear Keyframes

Linear interpolation is performed between [KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._LinearDoubleKeyFrame.html) values.

```xml
<Canvas
 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
 Height="100" Width="500">
  <Rectangle x:Name="Rect" Width="100" Height="60" Margin="60" Fill="YellowGreen" RenderTransformOrigin="0.5,0.5">
    <Rectangle.RenderTransform>
      <TranslateTransform X="0" Y="0"/>
    </Rectangle.RenderTransform>
  </Rectangle>
  <Button Content="Start Animation" Margin="10" HorizontalAlignment="Left" VerticalAlignment="Top">
    <Button.Triggers>
      <EventTrigger RoutedEvent="Button.Click">
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimationUsingKeyFrames
              Storyboard.TargetName="Rect"
              Storyboard.TargetProperty="(UIElement.RenderTransform).(TranslateTransform.X)">
              <LinearDoubleKeyFrame Value="0" KeyTime="0:0:0"/>
              <LinearDoubleKeyFrame Value="50" KeyTime="0:0:1"/>
              <LinearDoubleKeyFrame Value="-20" KeyTime="0:0:2"/>
              <LinearDoubleKeyFrame Value="80" KeyTime="0:0:3"/>
            </DoubleAnimationUsingKeyFrames>
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger>
    </Button.Triggers>
  </Button>
</Canvas>
```

## Spline Keyframes

The spline keyframe classes have an additional KeySpline property that differentiates themselves from the linear classes. KeySpline can be set to an instance of a KeySpline object, which describes the desired motion as a cubic Bezier curve. [KeySpline](https://www.noesisengine.com/docs/Gui.Animation._KeySpline.html) has two properties of type Point that represent the curve's control points.

```xml
<Canvas
 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
 Height="100" Width="500">
  <Rectangle x:Name="Rect" Width="100" Height="60" Margin="60" Fill="YellowGreen" RenderTransformOrigin="0.5,0.5">
    <Rectangle.RenderTransform>
      <TranslateTransform X="0" Y="0"/>
    </Rectangle.RenderTransform>
  </Rectangle>
  <Button Content="Start Animation" Margin="10" HorizontalAlignment="Left" VerticalAlignment="Top">
    <Button.Triggers>
      <EventTrigger RoutedEvent="Button.Click">
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimationUsingKeyFrames
              Storyboard.TargetName="Rect"
              Storyboard.TargetProperty="(UIElement.RenderTransform).(TranslateTransform.X)">
              <SplineDoubleKeyFrame KeySpline="0,1 1,0" Value="0" KeyTime="0:0:0"/>
              <SplineDoubleKeyFrame KeySpline="0,1 1,0" Value="50" KeyTime="0:0:1"/>
              <SplineDoubleKeyFrame KeySpline="0,1 1,0" Value="-20" KeyTime="0:0:2"/>
              <SplineDoubleKeyFrame KeySpline="0,1 1,0" Value="80" KeyTime="0:0:3"/>
            </DoubleAnimationUsingKeyFrames>
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger>
    </Button.Triggers>
  </Button>
</Canvas>
```

## Discrete Keyframes

A [discrete KeyFrame](https://www.noesisengine.com/docs/Gui.Animation._DiscreteDoubleKeyFrame.html) simply indicates that no interpolation should be done from the previous keyframe.

```xml
<Canvas
 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
 Height="100" Width="500">
  <Rectangle x:Name="Rect" Width="100" Height="60" Margin="60" Fill="YellowGreen" RenderTransformOrigin="0.5,0.5">
    <Rectangle.RenderTransform>
      <TranslateTransform X="0" Y="0"/>
    </Rectangle.RenderTransform>
  </Rectangle>
  <Button Content="Start Animation" Margin="10" HorizontalAlignment="Left" VerticalAlignment="Top">
    <Button.Triggers>
      <EventTrigger RoutedEvent="Button.Click">
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimationUsingKeyFrames
              Storyboard.TargetName="Rect"
              Storyboard.TargetProperty="(UIElement.RenderTransform).(TranslateTransform.X)">
              <DiscreteDoubleKeyFrame Value="0" KeyTime="0:0:0"/>
              <DiscreteDoubleKeyFrame Value="50" KeyTime="0:0:1"/>
              <DiscreteDoubleKeyFrame Value="-20" KeyTime="0:0:2"/>
              <DiscreteDoubleKeyFrame Value="80" KeyTime="0:0:3"/>
            </DoubleAnimationUsingKeyFrames>
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger>
    </Button.Triggers>
  </Button>
</Canvas>
```

**NOTE**

Each keyframe instance can give a specific value and a time for that value to be applied. Setting KeyTime is optional, however. If you omit one, the animation system assumes the keyframe occurs halfway between the surrounding keyframes. If you omit the KeyTime on all keyframes, they are spaced evenly across the duration of the animation.

# Easing functions

Easing functions allow you to apply custom mathematical formulas to your animations. For example, you may want an object to realistically bounce or behave as though it were on a spring. You could use KeyFrame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.

Besides creating your own custom easing function by inheriting from [EasingFunctionBase](https://www.noesisengine.com/docs/Gui.Animation._EasingFunctionBase.html), you can use one of several [easing functions](https://www.noesisengine.com/docs/Gui.Animation.EasingFunctions.html) provided by the animation system to create common effects.

```xml
<Canvas
 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
 Height="100" Width="500">
  <Rectangle x:Name="Rect" Width="100" Height="60" Margin="60" Fill="YellowGreen" RenderTransformOrigin="0.5,0.5">
    <Rectangle.RenderTransform>
      <TranslateTransform X="0" Y="0"/>
    </Rectangle.RenderTransform>
  </Rectangle>
  <Button Content="Start Animation" Margin="10" HorizontalAlignment="Left" VerticalAlignment="Top">
    <Button.Triggers>
      <EventTrigger RoutedEvent="Button.Click">
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Duration="0:0:1" From="1" To="0"
              Storyboard.TargetName="Rect"
              Storyboard.TargetProperty="(Shape.Fill).(Brush.Opacity)">
              <DoubleAnimation.EasingFunction>
                <SineEase EasingMode="EaseInOut"/>
              </DoubleAnimation.EasingFunction>
            </DoubleAnimation>
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger>
    </Button.Triggers>
  </Button>
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