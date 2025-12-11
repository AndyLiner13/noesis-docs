Source: https://www.noesisengine.com/docs/Gui.Core.CodeBehindTutorial.html

# Code-Behind and XAML in Noesis

![github](https://www.noesisengine.com/docs/github.png) [Tutorial Data](https://github.com/Noesis/Tutorials/tree/master/Samples/ApplicationTutorial)

Code-behind is a term used to describe the code that is joined with markup-defined objects. The code-behind class is where you can put code for the implementation of event handlers and other application logic. It is common to find [Window](../App.ApplicationLauncher/_Window.md) and [UserControl](UserControlTutorial.md) implementations using code-behind.

The XAML language includes language-level features that make it possible to associate code files with markup files, from the markup file side. Specifically, the XAML language defines the *x:Class* directive.

# x:Class Directive

*x:Class* is optional in the sense that it is entirely valid to have a XAML page that has no code-behind. However, if your XAML declares event-handling attribute values or instantiates custom elements where the defining classes are in the code-behind class, you have to provide the *x:Class* directive.

*x:Class* can only be specified on the root element of a XAML. The value of the *x:Class* directive must be a string that specifies the fully qualified name of a class. There is more information about registering classes in our [Extending Tutorial](ExtendingTutorial.md).

```
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Title="NoesisGUI - Main Window"
  x:Class="Sample.MainWindow">

</Window>
```

The code-behind is a class implemented in C++ or C# that derives from the root of the XAML page element. Code behind files have the extension '*.xaml.cpp*' or '*.xaml.cs*' and they may be displayed collapsed under the XAML file in your editor.

C++

```
namespace Sample
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

        NS_IMPLEMENT_INLINE_REFLECTION_(MainWindow, Window, "Sample.MainWindow")
    };
}
```

C#

```
namespace Sample
{
    public class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private void InitializeComponent()
        {
            GUI.LoadComponent(this, "MainWindow.xaml");
        }
    }
}
```

Note

In comparison with WPF, InitializeComponent() is not implemented automatically in a partial class when compiling the XAML

# x:Name Directive

*x:Name* uniquely identifies XAML-defined elements. This property can be used in your code-behind, as a reference to the object being created.

```
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Title="NoesisGUI - Main Window"
  x:Class="Sample.MainWindow">

  <Button x:Name="Button"/>

</Window>
```

As an alternative to manual invocations using *FindName()* from the code-behind, [FrameworkElement](_FrameworkElement.md) exposes the virtual function *ConnectField* that is invoked for each named element in the tree. In C++ the macro **NS\_CONNECT\_FIELD** is provided as a helper to easily implement *ConnectField*.

C++

```
namespace Sample
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

        bool ConnectField(BaseComponent* object, const char* name) override
        {
            NS_CONNECT_FIELD(_button, "Button");

            return false;
        }

        Button* _button;

        NS_IMPLEMENT_INLINE_REFLECTION_(MainWindow, Window, "Sample.MainWindow")
    };
}
```

# Event Subscription

As explained in the [Events Tutorial](EventsTutorial.md#code-behind-subscription), you can assign an event handler to an element in XAML using markup.

```
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Title="NoesisGUI - Main Window"
  x:Class="Sample.MainWindow">

  <Button Click="OnClick"/>

</Window>
```

C++

```
namespace Sample
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
            NS_CONNECT_EVENT(Button, Click, OnClick);

            return false;
        }

        void OnClick(BaseComponent* source, const RoutedEventArgs& args)
        {
            printf("Button was clicked");
        }

        NS_IMPLEMENT_INLINE_REFLECTION_(MainWindow, Window, "Sample.MainWindow")
    };
}
```

C#

```
namespace Sample
{
    public class MainWindow: Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private void InitializeComponent()
        {
            GUI.LoadComponent(this, "MainWindow.xaml");
        }

        protected override bool ConnectEvent(object source, string eventName, string handlerName)
        {
            if (eventName == "Click" && handlerName == "OnClick")
            {
                ((Button)source).Click += this.OnClick;
                return true;
            }

            return false;
        }

        private void OnClick(object sender, RoutedEventArgs args)
        {
            Console.WriteLine("Button was clicked");
        }
    }
}
```