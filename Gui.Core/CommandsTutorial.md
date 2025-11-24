Source: https://www.noesisengine.com/docs/Gui.Core.CommandsTutorial.html

# Commands

![github](/github/png.md) [Tutorial Data](https://github.com/Noesis/Tutorials/tree/master/Samples/Commands)

*Commands* allow you to define actions in one place and then refer to them from all your user interface controls like [MenuItems](/Gui.Core/_MenuItem.md), [ToolBars](/Gui.Core/_ToolBar.md) or [Buttons](/Gui.Core/_Button.md). Examples of commands are the *Copy*, *Cut*, and *Paste* operations found on many applications. Applications often expose these actions through many mechanisms simultaneously: MenuItems in a *Menu*, MenuItems on a *ContextMenu*, Buttons on a *ToolBar*, *Keyboard Shortcuts* and so on.

*Commands* have several purposes. The first purpose is to *separate* the semantics and the object that invokes a command from the logic that executes the command. This allows for multiple and disparate sources to *invoke* the same command logic, and it allows the command logic to be customized for different targets. For example, the editing operations *Copy*, *Cut*, and *Paste*, which are found in many applications, can be invoked by using different user actions if they are implemented by using commands. An application might allow a user to cut selected objects or text by either clicking a button, choosing an item in a menu, or using a key combination, such as *CTRL+X*. By using commands, you can *bind* each type of user action to the same logic.

Command is also one of the important components of any *MVVM* (Model-View-ViewModel) application. MVVM architectures help with decoupling the components of an application to make the application easier to unit test, maintain and extend.

# Command bindings

Commands don't actually do anything by themselves. At the root, they consist of the *ICommand* interface, which only defines an event and two methods: *Execute()* and *CanExecute()*. The first one is for performing the actual action, while the second one is for determining whether the action is currently available. To perform the actual action of the command, you need a link between the command and your code and this is where the [CommandBinding](/Gui.Core/_CommandBinding.md) comes into play.

A *CommandBinding* is usually defined on a [Window](/App.ApplicationLauncher/_Window.md) or [UserControl](/Gui.Core/_UserControl.md), and holds a reference to the *Command* that it handles, as well as the actual event handlers for dealing with the *Execute()* and *CanExecute()* events of the *Command*.

The semantics of a command can be consistent across applications and classes, but the logic of the action is specific to the particular object acted upon. For example, the key combination *CTRL+X* invokes the *Cut* command in text classes, image classes, and Web browsers, but the actual logic for performing the *Cut* operation is defined by the application that performs the cut. A *RoutedCommand* enables clients to implement the logic. A text object may cut the selected text into the clipboard, while an image object may cut the selected image. When an application handles the *Executed* event, it has access to the target of the command and can take *appropriate* action depending on the target's type.

# Built-In Commands

Controls such as [Button](/Gui.Core/_Button.md), [CheckBox](/Gui.Core/_CheckBox.md), and [MenuItem](/Gui.Core/_MenuItem.md) have logic to interact with any command on your behalf. They expose a simple *Command* property. When set, these controls automatically call the command's *Execute* method (when *CanExecute* returns true) whenever their *Click* event is raised. In addition, they automatically keep their value for *IsEnabled* synchronized with the value of *CanExecute* by leveraging the *CanExecuteChanged* event. By supporting all this via a simple property assignment, all of this logic is available from XAML.

[ApplicationCommands](/Gui.Core/_ApplicationCommands.md) provides a set of built-in commands ready to be used.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <DockPanel Width="300" Height="300" Background="#505860">
    <Menu DockPanel.Dock="Top">
      <MenuItem Header="File"/>
      <MenuItem Header="Edit">
        <MenuItem Header="Copy" Command="ApplicationCommands.Copy"/>
        <MenuItem Header="Cut" Command="ApplicationCommands.Cut"/>
        <MenuItem Header="Paste" Command="ApplicationCommands.Paste"/>
      </MenuItem>
      <MenuItem Header="Help"/>
    </Menu>
    <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
      <TextBox Width="200"/>
      <TextBox Width="200" Margin="0,10,0,0"/>
    </StackPanel>
  </DockPanel>
</Grid>
```

# Custom Commands

The easiest way to create custom commands is implementing the *ICommand* interface. For example, the implementation of a *Command* that invokes a [Delegate](/Gui.Core/CppArchitectureGuide.md#delegates) is as follows:

NOTE

Please, refer to our [Extending NoesisGUI Tutorial](/Gui.Core/ExtendingTutorial.md) for more information about extending noesisGUI.

C++

```
class DelegateCommand final: public Noesis::BaseCommand
{
public:
    typedef Noesis::Delegate<void (BaseComponent*)> ExecuteFunc;
    typedef Noesis::Delegate<bool (BaseComponent*)> CanExecuteFunc;

    DelegateCommand(const ExecuteFunc& execute): _execute(execute) {}
    DelegateCommand(const ExecuteFunc& execute, const CanExecuteFunc& canExecute):
        _execute(execute), _canExecute(canExecute) {}

    bool CanExecute(BaseComponent* param) const override
    {
        return _canExecute.Empty() || _canExecute(param);
    }

    void Execute(BaseComponent* param) const override
    {
        _execute(param);
    }

private:
    ExecuteFunc _execute;
    CanExecuteFunc _canExecute;
};
```

C#

```
public class DelegateCommand: ICommand
{
    public DelegateCommand(Action<object> execute)
    {
        if (execute == null)
        {
            throw new ArgumentNullException("execute");
        }

        _execute = execute;
    }

    public DelegateCommand(Func<object, bool> canExecute, Action<object> execute)
    {
        if (canExecute == null)
        {
            throw new ArgumentNullException("canExecute");
        }
        if (execute == null)
        {
            throw new ArgumentNullException("execute");
        }

        _canExecute = canExecute;
        _execute = execute;
    }

    public bool CanExecute(object parameter)
    {
        return _canExecute == null || _canExecute(parameter);
    }

    public void Execute(object parameter)
    {
        _execute(parameter);
    }

    public event EventHandler CanExecuteChanged;

    public void RaiseCanExecuteChanged()
    {
        var handler = CanExecuteChanged;
        if (handler != null)
        {
            handler(this, System.EventArgs.Empty);
        }
    }

    private Func<object, bool> _canExecute;
    private Action<object> _execute;
}
```

# MVVM example

[MVVM](https://en.wikipedia.org/wiki/Model_View_ViewModel) pattern can be implemented in NoesisGUI by using commands and a *ViewModel* class. The *ViewModel* is the class in charge of binding data to the XAML and implementing the delegate that will be invoked by the command. For example:

NOTE

In this sample DelegateCommand is not allocated in the heap to reduce allocations as explained in the [C++ Architecture Guide](/Gui.Core/CppArchitectureGuide.md#reference-counting). This is one of those scenarios where it is safe to do so and reference counting is not needed.

C++

```
class ViewModel: public NotifyPropertyChangedBase
{
public:
    ViewModel()
    {
        _command.SetExecuteFunc(MakeDelegate(this, &ViewModel::SayHello));
    }

    const char* GetInput() const
    {
        return _input;
    }

    void SetInput(const char* input)
    {
        String::Copy(_input, sizeof(_input), value);
    }

    const char* GetOutput() const
    {
        return _output;
    }

    void SetOutput(const char* output)
    {
        if (!String::Equals(_output, value))
        {
            String::Copy(_output, sizeof(_output), value);
            OnPropertyChanged("Output");
        }
    }

    DelegateCommand* GetSayHelloCommand() const
    {
        return &_command;
    }

private:
    void SayHello(BaseComponent* param_)
    {
        if (Boxing::CanUnbox<NsString>(param_))
        {
            const char* param = Boxing::Unbox<NsString>(param_).c_str();

            char text[512];
            snprintf(text, sizeof(text), "Hello, %s (%s)", _input, param);
            SetOutput(text);
        }
    }

private:
    DelegateCommand _command;
    char _input[256] = "";
    char _output[256] = "";

    NS_IMPLEMENT_INLINE_REFLECTION(ViewModel, NotifyPropertyChangedBase)
    {
        NsMeta<TypeId>("Commands.ViewModel");
        NsProp("Input", &ViewModel::GetInput, &ViewModel::SetInput);
        NsProp("Output", &ViewModel::GetOutput, &ViewModel::SetOutput);
        NsProp("SayHelloCommand", &ViewModel::GetSayHelloCommand);
    }
};
```

C#

```
public class ViewModel : NotifyPropertyChangedBase
{
    public string Input { get; set; }

    private string _output = string.Empty;
    public string Output
    {
        get { return _output; }
        set
        {
            if (_output != value)
            {
                _output = value;
                OnPropertyChanged("Output");
            }
        }
    }

    public Noesis.Samples.DelegateCommand SayHelloCommand { get; private set; }

    public ViewModel()
    {
        SayHelloCommand = new Noesis.Samples.DelegateCommand(SayHello);
    }

    private void SayHello(object parameter)
    {
        string param = (string)parameter;
        Output = System.String.Format("Hello, {0} ({1})", Input, param);
    }
}
```

The following XAML shows how you might use the previous *ViewModel*. It is set as the *DataContext* of the root element. The button inside the panel gets the command assigned from the *ViewModel*. Whenever the button is pressed the command is fired.

![CommandsTutorialImg1.jpg](/CommandsTutorialImg1/jpg.md)

```
<Grid
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <Viewbox>
    <Border x:Name="myBorder" DataContext="{StaticResource ViewModel}" Width="400" Margin="50"
        Background="#801C1F21" BorderThickness="1" CornerRadius="5" BorderBrush="#D0101611"
        Padding="5" HorizontalAlignment="Center" VerticalAlignment="Center">
      <StackPanel Orientation="Vertical">
        <TextBox MinWidth="300" Margin="3" Text="{Binding Input, Mode=TwoWay}" FontSize="28"/>
        <TextBox x:Name="Param" MinWidth="300" Margin="3" Text="" FontSize="24"/>
        <Button Content="Say Hello" Margin="3" Command="{Binding SayHelloCommand}"
            CommandParameter="{Binding Text, ElementName=Param}" FontSize="28" />
        <Viewbox Margin="5" Height="50">
          <TextBlock Margin="5" Padding="0" TextAlignment="Center" Text="{Binding Output}"
              FontSize="28" Foreground="White"/>
        </Viewbox>
      </StackPanel>
    </Border>
  </Viewbox>

</Grid>
```