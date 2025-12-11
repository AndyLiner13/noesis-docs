Source: https://www.noesisengine.com/docs/Gui.Core.DataBindingTutorial.html

# Data Binding

![github](https://www.noesisengine.com/docs/github.png) [Tutorial Data](https://github.com/Noesis/Tutorials/tree/master/Samples/DataBinding)

NoesisGUI provides a simple and powerful way to auto-update data between the business model and the user interface. This mechanism is called *Data Binding*.
The key to data binding is a [Binding](_Binding.md) object that "glues" two properties together and keeps a channel of communication open between them. You can set a *Binding* once, and then have it do all the synchronization work for the remainder of the application's lifetime.

In this tutorial we will explain the different ways you might want to use data binding.

# Using *Binding* in XAML

![DataBindingTutorialImg1.jpg](https://www.noesisengine.com/docs/DataBindingTutorialImg1.jpg)

To use *Binding* in XAML, you directly set the target property to a *Binding* instance and then use the standard markup extension syntax to set its properties. The following example shows a simple binding between the text of a [TextBox](_TextBox.md) and a [Label](_Label.md) that reflects the typed value:

```
<StackPanel
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    VerticalAlignment="Center">

  <TextBox x:Name="textbox" />
  <Label Content="{Binding Text, ElementName=textbox}" />

</StackPanel>
```

NOTE

The source of a data binding can be a normal property or a *DependencyProperty*. The target property of the binding must be a *DependencyProperty*.

# Data Context

It is quite common for many elements in the same UI to bind to the same source object. For this reason, NoesisGUI supports specifying an implicit data source rather than explicitly marking every *Binding* with *Source*, *RelativeSource* or *ElementName*. This implicit data source is also known as a *data context*.

To designate a source object as a data context, simply find a common parent element and set its *DataContext* property to the source object. When encountering *Binding* without an explicit source object, NoesisGUI traverses up the logical tree until it finds a non null *DataContext*. Here is an example of setting a data context that will be used for all of the examples to come:

```
<UserControl
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <UserControl.Resources>
    <DataModel x:Name="dataModel" />
  </UserControl.Resources>

  <StackPanel DataContext="{StaticResource dataModel}" />

</UserControl>
```

NOTE

In real projects is more common setting the data context by code.

# Binding to Plain Properties

NoesisGUI supports any normal property on any object as a data-binding source. For example, the following XAML binds several properties that belong to instances found in the current data context:

```
<UserControl
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <UserControl.Resources>
    <DataModel1 x:Name="dataModel">
      <DataModel1.Person>
        <Person Weight="90">
          <Person.Name>
            <Name First="John" Last="Doe" />
          </Person.Name>
        </Person>
      </DataModel1.Person>
    </DataModel1>
  </UserControl.Resources>

  <StackPanel DataContext="{StaticResource dataModel}" HorizontalAlignment="Center"
              VerticalAlignment="Center">
    <TextBlock Text="{Binding Person.Name.First}" />
    <TextBlock Text="{Binding Person.Name.Last}" />
    <TextBlock Text="{Binding Person.Weight}" />
  </StackPanel>

</UserControl>
```

There is a big caveat to using a plain property as a data-binding source, however. Because such properties have no automatic plumbing for change notification, the target is not kept up to date as the source property value changes without doing a little extra work. To keep the target and source properties synchronized, the source object must implement the *INotifyPropertyChanged* interface.

## C++ implementation

There are a few important details you must pay attention to whenever you implement a data model in C++:

- The base class *NotifyPropertyChangedBase* already implements the interface *INotifyPropertyChanged* for us
- Expose properties using [reflection macros](CppArchitectureGuide.md#reflection) macros with getter and setter functions
- In each setter, check if the property changed event must be fired

C++

```
class Name: public NotifyPropertyChangedBase
{
public:
    const char* GetFirst() const
    {
        return _first.Str();
    }

    void SetFirst(const char* first)
    {
        if (_first != first)
        {
            _first = first;
            OnPropertyChanged("First");
        }
    }

    const char* GetLast() const
    {
        return _last.Str();
    }

    void SetLast(const char* last)
    {
        if (_last != last)
        {
            _last = last;
            OnPropertyChanged("Last");
        }
    }

private:
    String _first;
    String _last;

    NS_IMPLEMENT_INLINE_REFLECTION(Name, NotifyPropertyChangedBase)
    {
        NsProp("First", &Name::GetFirst, &Name::SetFirst);
        NsProp("Last", &Name::GetLast, &Name::SetLast);
    }
};

class Person: public NotifyPropertyChangedBase
{
public:
    Name* GetName() const
    {
        return _name;
    }

    void SetName(Name* name)
    {
        if (_name != name)
        {
            _name.Reset(name);
            OnPropertyChanged("Name");
        }
    }

    float GetWeight() const
    {
        return _weight;
    }

    void SetWeight(const float weight)
    {
        if (_weight != weight)
        {
            _weight = weight;
            OnPropertyChanged("Weight");
        }
    }

private:
    Ptr<Name> _name;
    float _weight;

    NS_IMPLEMENT_INLINE_REFLECTION(Person, BaseComponent)
    {
        NsProp("Name", &Person::GetName, &Person::SetName);
        NsProp("Weight", &Person::GetWeight, &Person::SetWeight);
    }
};

class DataModel1: public NotifyPropertyChangedBase
{
public:
    Person* GetPerson() const
    {
        return _person;
    }

    void SetPerson(Person* person)
    {
        if (_person != person)
        {
            _person.Reset(person);
            OnPropertyChanged("Person");
        }
    }

private:
    Ptr<Person> _person;

    NS_IMPLEMENT_INLINE_REFLECTION(DataModel1, BaseComponent)
    {
        NsProp("Person", &DataModel1::GetPerson, &DataModel1::SetPerson);
    }
};
```

## C# implementation

Things are a lot easier in C#. You basically only need to implement the *INotifyPropertyChanged* interface.

C#

```
public class Name: INotifyPropertyChanged
{
    private string _first;
    public string First
    {
        get { return _first; }
        set
        {
            if (_first != value)
            {
                _first = value;
                PropertyChanged?.Invoke(this, new PropertyChangedEventArgs("First"));
            }
        }
    }

    private string _last;
    public string Last
    {
        get { return _last; }
        set
        {
            if (_last != value)
            {
                _last = value;
                PropertyChanged?.Invoke(this, new PropertyChangedEventArgs("Last"));
            }
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;
}

public class Person: INotifyPropertyChanged
{
    private Name _name;
    public Name Name
    {
        get { return _name; }
        set
        {
            if (_name != value)
            {
                _name = value;
                PropertyChanged?.Invoke(this, new PropertyChangedEventArgs("Name"));
            }
        }
    }

    private float _weight;
    public float Weight
    {
        get { return _weight; }
        set
        {
            if (_weight != value)
            {
                _weight = value;
                PropertyChanged?.Invoke(this, new PropertyChangedEventArgs("Weight"));
            }
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;
}

public class DataModel1
{
    private Person _person;
    public Person Person
    {
        get { return _person; }
        set
        {
            if (_person != value)
            {
                _person = value;
                PropertyChanged?.Invoke(this, new PropertyChangedEventArgs("Person"));
            }
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;
}
```

## Indexed Properties

In C#, *Indexed Properties* can be used as source of a data-binding. That way, you can write something like this:

C#

```
class Person
{
    public string Name {get; set;}
    public string PhoneNumber {get; set;}
}

class Contacts
{
    public IEnumerable<Person> Persons {get; set;}

    public Person this[string Name]
    {
        get
        {
            return Persons.Where(p => p.Name == Name).FirstOrDefault();
        }
    }
}
```

```
<TextBox Text="{Binding Contacts[John].PhoneNumber}" />
```

NOTE

Only indexers with the key type being int or string are supported in NoesisGUI.

## StringFormat

If you need to format the text display of a given value, you can do so using the *StringFormat* attribute in the binding declaration. With *StringFormat* you can format the output of information without using code behind or value converters.

```
<UserControl
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <UserControl.Resources>
    <DataModel1 x:Name="dataModel">
      <DataModel1.Person>
        <Person Weight="90">
          <Person.Name>
            <Name First="John" Last="Doe" />
          </Person.Name>
        </Person>
      </DataModel1.Person>
    </DataModel1>
  </UserControl.Resources>

  <StackPanel DataContext="{StaticResource dataModel}" HorizontalAlignment="Center"
              VerticalAlignment="Center">
    <TextBlock Text="{Binding Person.Name.First}" />
    <TextBlock Text="{Binding Person.Name.Last}" />
    <TextBlock Text="{Binding Person.Weight, StringFormat=Weight is {0:F2}}" />
  </StackPanel>

</UserControl>
```

More examples of StringFormat:

```
<TextBlock Text="{Binding Amount, StringFormat={}{0:D}}" />
<TextBlock Text="{Binding Amount, StringFormat=Total: {0:D}}" />
<TextBlock Text="{Binding Amount, StringFormat=Total: {0:D} units}" />
```

NOTE

Notice the '{}' just after the StringFormat attribute? What that is doing is escaping the text after the '=' sign. This is needed because there is no text after the '=' sign

[Standard](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings), [Custom](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings) and [Composite](https://docs.microsoft.com/en-us/dotnet/standard/base-types/composite-formatting) .NET Numeric Format String are supported.

### Standard Numeric Format strings

| Format specifier | Name | Description | Example |
| --- | --- | --- | --- |
| "C" or "c" | Currency | A currency value | 123.456 ("C") ➡ $123,46 |
| "D" or "d" | Decimal | Integer digits with optional negative sign | 1234 ("D") ➡ 1234 |
| "E" or "e" | Exponential | Exponential notification | 1052.0329112756 ("E") ➡ 1.052033E+003 |
| "F" or "f" | Fixed-point | Integral and decimal digits with optional negative sign | 234.567 ("F") ➡ 1234.57 |
| "G" or "g" | General | The more compact of either fixed-point or scientific notation | -123.456 ("G") ➡ -123.456 |
| "N" or "n" | Number | Integral and decimal digits, group separators, and a decimal separator with optional negative sign | 1234.567 ("N") ➡ 1,234.57 |
| "P" or "p" | Percent | Number multiplied by 100 and displayed with a percent symbol | 1 ("P") ➡ 100.00 % |
| "R" or "r" | Round-trip | A string that can round-trip to an identical number | 123456789.12345678 ("R") ➡ 123456789.12345678 |
| "X" or "x" | Hexadecimal | A hexadecimal string | 255 ("X") ➡ FF |

### Custom numeric format strings

| Format specifier | Name | Description | Example |
| --- | --- | --- | --- |
| "0" | Zero placeholder | Replaces the zero with the corresponding digit if one is present; otherwise, zero appears in the result string | 1234.5678 ("00000") ➡ 01235 |
| "#" | Digit placeholder | Replaces the "#" symbol with the corresponding digit if one is present; otherwise, no digit appears in the result string | 1234.5678 ("#####") ➡ 1235 |
| "." | Decimal point | Determines the location of the decimal separator in the result string | 0.45678 ("0.00") ➡ 0.46 |
| "," | Group separator and number scaling | Serves as both a group separator and a number scaling specifier. As a group separator, it inserts a localized group separator character between each group. As a number scaling specifier, it divides a number by 1000 for each comma specified | 2147483647 ("##,#") ➡ 2,147,483,647  2147483647 ("#,#,,") ➡ 2,147 |
| "%" | Percentage placeholder | Multiplies a number by 100 and inserts a localized percentage symbol in the result string | 0.3697 ("%#0.00") ➡ %36.97 |
| "E0" | Exponential notation | If followed by at least one 0 (zero), formats the result using exponential notation. The case of "E" or "e" indicates the case of the exponent symbol in the result string. The number of zeros following the "E" or "e" character determines the minimum number of digits in the exponent. A plus sign (+) indicates that a sign character always precedes the exponent. A minus sign (-) indicates that a sign character precedes only negative exponents | 987654 ("#0.0e0") ➡ 98.8e4  1.8901385E-16 ("0.0e+00") ➡ 1.9e-16  1503.92311 ("0.0##e+00") ➡ 1.504e+03 |
| "\" | Escape character | Causes the next character to be interpreted as a literal rather than as a custom format specifier | 87654 ("\###00\#") ➡ #987654# |
| 'string' | Literal string delimiter | Indicates that the enclosed characters should be copied to the result string unchanged | 68 ("# 'degrees'") ➡ 68 degrees |
| ; | Section separator | Defines sections with separate format strings for positive, negative, and zero numbers | 12.345 ("#0.0#;(#0.0#);-0-") ➡ 12.35 |
| Other | All other characters | The character is copied to the result string unchanged | 68 ("# °") ➡ 68 ° |

# Binding Dependency Properties

Dependency properties have plumbing for change notifications built in. This facility is the key to noesisGUI's ability to keep the target property and source property in sync. You don't need to use *INotifyPropertyChange* when you implement Dependency Properties. In fact, this should be the preferred method for creating bindable properties if you are deriving from [DependencyObject](../Gui.DependencySystem/_DependencyObject.md).

Dependency Properties are created imperatively in the code behind of the visual element, for example:

```
<UserControl
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="View2"
    x:Name="root">

  <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
    <TextBox Text="{Binding ElementName=root, Path=Text, Mode=TwoWay, UpdateSourceTrigger=PropertyChanged}" />
    <TextBlock Text="{Binding ElementName=root, Path=Text}" Width="100" />
  </StackPanel>

</UserControl>
```

As you can see we are setting the *Mode* property of the *Binding*. It can be set to one of the following values of the *BindingMode* enumeration:

![DataBindingTutorialImg2.jpg](https://www.noesisengine.com/docs/DataBindingTutorialImg2.jpg)

- **OneWay**: The target is updated whenever the source changes.
- **TwoWay**: A change to either the target or source updates the other.
- **OneWayToSource**: The opposite of *OneWay*. The source is updated whenever the target changes.
- **OneTime**: This works just like *OneWay*, except changes to the source are not reflected at the target. The target retains a snapshot of the source at the time the *Binding* is initiated.

*TwoWay* binding is appropriate for data-bounds forms, where you might have *TextBoxes* that get filled with data that the user is allowed to change. In fact, whereas most dependency properties default to *OneWay* binding, dependency properties such as *TextBox.Text* default to *TwoWay* binding.

We are also using the *UpdateSourceTrigger* property. When using *TwoWay* or *OneWayToSource* binding, you might want different behaviors for when and how the source gets updated. For example, if a user types in a *TwoWay* data-bound *TextBox*, do you want the source to be updated with each keystroke, or only when the user is done typing? Binding enables you to control such behavior with its *UpdateSourceTrigger* property.

*UpdateSourceTrigger* can be set to a member of the *UpdateSourceTrigger* enumeration, which has the following values:

- **PropertyChanged**: The source is updated whenever the target property value changes.
- **LostFocus**: When the target property value changes, the source is only updated after the target element loses focus.
- **Explicit**: The source is only updated when you make an explicit call to *BindingExpression.UpdateSource*.

Just as different properties have different default *Mode* settings, they also have different default *UpdateSourceTrigger* settings. *TextBox.Text* defaults to *LostFocus*.

C++

```
class View2: public UserControl
{
public:
    const char* GetText() const
    {
        return GetValue<String>(TextProperty).Str();
    }

    void SetText(const char* text)
    {
        SetValue<String>(TextProperty, text);
    }

    static const DependencyProperty* TextProperty;

private:
    NS_IMPLEMENT_INLINE_REFLECTION(View2, UserControl)
    {
        UIElementData* data = NsMeta<UIElementData>(TypeOf<SelfClass>());
        data->RegisterProperty<String>(TextProperty, "Text",
            FrameworkPropertyMetadata::Create(String(""), FrameworkOptions_None));
    }
};
```

C#

```
class View2: UserControl
{
    public static DependencyProperty TextProperty = DependencyProperty.Register("Text", typeof(string),
        typeof(View2), new PropertyMetadata(""));

    public string Text
    {
        get { return (string)GetValue(TextProperty); }
        set { SetValue(TextProperty, value); }
    }
}
```

# Binding to a Collection

So far we've only discussed binding to single objects, however, binding to a data collection is a common scenario. For example, a common scenario is to use an [ItemsControl](_ItemsControl.md) such as a [ListBox](_ListBox.md), [ListView](../Gui.Controls/_ListView.md), or [TreeView](_TreeView.md) to display a data collection.

It would make sense to create a *Binding* with *ListBox.Items* as the target property, but, unfortunately, *Items* is not a dependency property. But *ListBox* (and all other *ItemsControl*) have an *ItemsSource* dependency property that exist specifically for this data-binding scenario.

![DataBindingTutorialImg3.jpg](https://www.noesisengine.com/docs/DataBindingTutorialImg3.jpg)

```
<ListBox ItemsSource="{Binding Source={StaticResource items}}" />
```

For the target property to stay updated with changes to the source collection, the source collection must implement an interface called *INotifyCollectionChanged*. Fortunately, NoesisGUI already has a built-in class that does this work for you. It is called [ObservableCollection](_ObservableCollection.md).

```
<Grid
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    Width="600">

  <Grid.Resources>
    <DataModel3 x:Name="dataModel" />

    <DataTemplate x:Key="TaskTemplate">
      <Grid>
        <Grid.ColumnDefinitions>
          <ColumnDefinition Width="Auto"/>
          <ColumnDefinition Width="100"/>
          <ColumnDefinition Width="200"/>
          <ColumnDefinition Width="200"/>
        </Grid.ColumnDefinitions>

        <Rectangle Width="15" Height="10" Fill="{Binding Color}" Stroke="Transparent"
                   StrokeThickness="0" Margin="5, 0, 5, 0" Grid.Column="0"/>
        <TextBlock Text="{Binding Name}" Margin="5, 0, 5, 0" Grid.Column="1"/>
        <TextBlock Text="{Binding Scale, StringFormat=P0}" Margin="5, 0, 5, 0" Grid.Column="2"/>
        <TextBlock Text="{Binding Pos}" Margin="5, 0, 5, 0" Grid.Column="3"/>
      </Grid>
    </DataTemplate>
  </Grid.Resources>

  <ListBox Height="100" DataContext="{StaticResource dataModel}"
      ItemsSource="{Binding Players}"
      ItemTemplate="{StaticResource TaskTemplate}" />

</Grid>
```

Note that we are using the *ItemTemplate* property to control how each item is rendered. This property is set to an instance of a [DataTemplate](_DataTemplate.md). *DataTemplate* derives from [FrameworkTemplate](_FrameworkTemplate.md). Therefore, it has a *VisualTree* content property that can be set to an arbitrary tree of *FrameworkElements*.

NOTE

For very simple cases you can use the **DisplayMemberPath** property present on all *ItemsControls*. This property works hand in hand with *ItemsSource*. If you set it to an appropriate property path, the corresponding property value gets rendered for each item.

When you apply a data template, it is implicitly given an appropriate data context. When applied as an *ItemTemplate*, the data context is implicitly the current item in *ItemsSource*.

![DataBindingTutorialImg6.jpg](https://www.noesisengine.com/docs/DataBindingTutorialImg6.jpg)

C++

```
class Player: public BaseComponent
{
public:
    Player() {}
    Player(const char* name, Color color, float scale, const char* pos): _name(name), _scale(scale),
        _pos(pos), _color(MakePtr<SolidColorBrush>(color)) {}

private:
    String _name;
    float _scale;
    String _pos;
    Ptr<Brush> _color;

    NS_IMPLEMENT_INLINE_REFLECTION(Player, BaseComponent)
    {
        NsProp("Name", &Player::_name);
        NsProp("Scale", &Player::_scale);
        NsProp("Pos", &Player::_pos);
        NsProp("Color", &Player::_color);
    }
};

class DataModel3: public BaseComponent
{
public:
    DataModel3(): _players(MakePtr<ObservableCollection<Player>>())
    {
        _players->Add(MakePtr<Player>("Player0", Color::Red, 1.0f, "(0,0,0)"));
        _players->Add(MakePtr<Player>("Player1", Color::Gray, 0.75f, "(0,30,0)"));
        _players->Add(MakePtr<Player>("Player2", Color::Orange, 0.50f, "(0,-10,0)"));
        _players->Add(MakePtr<Player>("Player3", Color::Green, 0.85f, "(0,-10,0)"));
    }

    ObservableCollection<Player>* GetPlayers() const { return _players; }

private:
    Ptr<ObservableCollection<Player>> _players;

    NS_IMPLEMENT_INLINE_REFLECTION(DataModel3, BaseComponent)
    {
        NsProp("Players", &DataModel3::GetPlayers);
    }
};
```

C#

```
public class Player
{
    public Player(string name, Color color, float scale, string pos)
    {
        Name = name;
        Color = new SolidColorBrush(color);
        Scale = scale;
        Pos = pos;
    }

    public string Name { get; private set; }
    public Brush Color { get; private set; }
    public float Scale { get; private set; }
    public string Pos { get; private set; }

}

public class DataModel3
{
    public DataModel3()
    {
        Players = new ObservableCollection<Player>();
        Players.Add(new Player("Player0", Colors.Red, 1.0f, "(0,0,0)"));
        Players.Add(new Player("Player1", Colors.Gray, 0.75f, "(0,30,0)"));
        Players.Add(new Player("Player2", Colors.Orange, 0.50f, "(0,-10,0)"));
        Players.Add(new Player("Player3", Colors.Green, 0.85f, "(0,-10,0)"));
    }

    public ObservableCollection<Player> Players { get; private set; }
}
```

A special subclasss of *DataTemplate* exists for working with **hierarchical** data. This class is called [HierarchicalDataTemplate](_HierarchicalDataTemplate.md). It not only enables you to change the presentation of such data, but enables you to directly bind a hierarchy of objects to an element that intrinsically understands hierarchies, such as a *TreeView* or *Menu* control.

The idea is to use *HierarchicalDataTemplate* for every data type in the hierarchy but then use a simple *DataTemplate* for any leaf nodes. Each data template gives you the option to customize the rendering of the data type, but *HierarchicalDataTemplate* also enables you to specify its children in the hierarchy by setting its *ItemsSource* property.

![DataBindingTutorialImg7.jpg](https://www.noesisengine.com/docs/DataBindingTutorialImg7.jpg)

```
<Grid
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <Grid.Resources>
    <LeagueList x:Key="items" />
    <HierarchicalDataTemplate DataType="League" ItemsSource="{Binding Path=Divisions}">
      <TextBlock Foreground="LightCyan" Text="{Binding Path=Name}"/>
    </HierarchicalDataTemplate>
    <HierarchicalDataTemplate DataType="Division" ItemsSource="{Binding Path=Teams}">
      <TextBlock Foreground="Snow" Text="{Binding Path=Name}"/>
    </HierarchicalDataTemplate>
    <DataTemplate DataType="Team">
      <TextBlock Foreground="Moccasin" Text="{Binding Path=Name}"/>
    </DataTemplate>
  </Grid.Resources>

  <TreeView DataContext="{StaticResource items}">
    <TreeViewItem ItemsSource="{Binding Leagues}" Header="My Soccer Leagues" />
  </TreeView>
</Grid>
```

# Value Converters

Whereas data templates can customize they way certain target values are rendered, value converters can morph the source value into a completely different target value. They enable you to plug in custom logic without giving up the benefits of data binding.

Value converters are often used to reconcile a source and target that are different data types. For example, you could change the background or foreground color of an element on the value of some non-*Brush* data source. Or, you could use it to simply enhance the information being displayed without the need for separate elements, such as adding an "item(s)" suffix to a raw count.

![DataBindingTutorialImg4.jpg](https://www.noesisengine.com/docs/DataBindingTutorialImg4.jpg)

For example, the following XAML toggles the visibility of an element based on the *IsChecked* property of a [CheckBox](_CheckBox.md) using a converter named [BooleanToVisibilityConverter](_BooleanToVisibilityConverter.md).

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Background="Gray">

  <Grid.Resources>
    <BooleanToVisibilityConverter x:Key="converter"/>
  </Grid.Resources>

  <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
    <CheckBox x:Name="checkBox" Content="Show Button" Width="100"/>
    <Button Content="Click" Margin="5" Visibility="{Binding ElementName=checkBox, Path=IsChecked,
            Converter={StaticResource converter}}"/>
  </StackPanel>

</Grid>
```

You can create your own converters by inheriting from *BaseValueConverter*. An example is shown in the [Extending Tutorial](ExtendingTutorial.md).

# Solar System Example

![DataBindingTutorialImg5.jpg](https://www.noesisengine.com/docs/DataBindingTutorialImg5.jpg)

This [example](https://github.com/Noesis/Tutorials/tree/master/Samples/DataBinding) summarizes all the concepts presented at this tutorial. It basically consists of a [ListBox](_ListBox.md) bound to an [ObservableCollection](_ObservableCollection.md) of *SolarSystemObject* items.

```
<ListBox ItemsSource="{Binding Source={StaticResource solarSystem}, Path=SolarSystemObjects}" />
```

The look of each planet is defined by a [DataTemplate](_DataTemplate.md) that uses data binding and a converter to generate the final look.

NOTE

This sample was adapted from the sample [The power of Styles and Templates in WPF](https://sudonull.com/post/203827-WPF-Binding-The-power-of-styles-and-templates-in-WPF).