Source: https://www.noesisengine.com/docs/Gui.Core.CustomRenderTutorial.html

# Custom Rendering Tutorial

![github](/github/png.md) [Tutorial Data](https://github.com/Noesis/Tutorials/tree/master/Samples/CustomRender)

Most of the controls in NoesisGUI are composed of multiple elements internally. It is the preferred method to create controls by combining existing elements, but it might be overkill in some cases. Large number of elements in a visual tree can cause the main element to become very heavy and consume more memory, thereby causing performance issues.

There is a solution to this problem and it involves letting the element take control of the rendering of its content. You simply override the *OnRender* method and draw into its [DrawingContext](/Gui.Core/_DrawingContext.md) parameter. It is a memory efficient way of building a composite element. It also simplifies the visual tree of the element and makes it lighter.

[DrawingContext](/Gui.Core/_DrawingContext.md) is a lightweight class which can be used to render rectangles, lines, text or any arbitrary geometric shapes.

# Arkanoid example

In our collection of examples you can find an implementation of the popular [Arkanoid](https://github.com/Noesis/Tutorials/tree/master/Samples/CustomRender) game using a single element with *custom rendering*.

```
<Window x:Class="CustomRender.MainWindow"
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:local="clr-namespace:CustomRender"
  Title="NoesisGUI - CustomRender"
  SizeToContent="WidthAndHeight"
  ResizeMode="NoResize">

  <local:Game Width="800" Height="600"/>

</Window>
```

![CustomRenderTutorialImg1.png](/CustomRenderTutorialImg1/png.md)

*Game* is a [FrameworkElement](/Gui.Core/_FrameworkElement.md) derived class that overrides its *OnRender* method. *OnRender* receives an object of type [DrawingContext](/Gui.Core/_DrawingContext.md) as an argument which contains useful methods to draw text and shapes. In this example we use *DrawRectangle* to render each block of the game.

C++

```
void Game::OnRender(DrawingContext* context) override
{
    // Draw background
    context->DrawRectangle(Brushes::Black(), nullptr, Rect(0, 0, Width, Height));

    // Draw ball
    context->DrawRectangle(Brushes::LightSkyBlue(), nullptr, Rect(x0, y0, x1, y1));

    // ...
```

NOTE

Although the API exposed by [DrawingContext](/Gui.Core/_DrawingContext.md) seems to be immediate it is still retained as the render commands are stored internally and later used by the render thread. The content is not being drawn immediately to the screen.