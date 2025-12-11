Source: https://www.noesisengine.com/docs/Gui.Core.CustomControlTutorial.html

# CustomControl Tutorial

![github](https://www.noesisengine.com/docs/github.png) [Tutorial Data](https://github.com/Noesis/Tutorials/tree/master/Samples/CustomControl)

In contrast with [UserControls](UserControlTutorial.md), that are created by *composition* of controls, a *CustomControl* **extends** an existing control. *CustomControls* can be styled and it is usually the best approach to build a control library.

Creating a CustomControl is quite simple but the challenge is to do it the right way. So before you start creating a control try to answer the following questions:

- What problem should my control solve?
- Who will use this control? In which context and environment?
- Can I extend or compose existing controls? Have you look at existing controls?
- Should it be possible to style or template my control?
- Is it used in a single project, or part of a reusable library?

This tutorial gives you a step by step walktrough on how to create a custom control to represent **Date and Time**.

# Choose the right base class

Choosing the right base class is crucial and can save a lot of time. Compare the features of your control with existing controls and start with one that matches close. The following list should give you a good overview from the most lightweight to more heavyweight base types:

- [UIElement](_UIElement.md): The most lightweight base class to start from. It has support for *Layout*, *Input*, *Focus* and *Events*.
- [FrameworkElement](_FrameworkElement.md): Derives from *UIElement* and adds support for styling, tooltips and context menus. It is the first base class that takes part in the logical tree and so it supports [data binding](DataBindingTutorial.md) and resource lookup.
- [Control](_Control.md): is the most common base class for controls (its name speaks for itself). It supports templates and adds some basic properties as *Foreground*, *Background* and *FontSize*.
- [ContentControl](_ContentControl.md): is a control that has an additional *Content* property. This is often used for simple containers.
- [HeaderedContentControl](_HeaderedContentControl.md): is a control that has an *Content* and a *Header* property. This is used for controls with a header like [Expander](_Expander.md), [TabControl](_TabControl.md) or [GroupBox](_GroupBox.md)
- [ItemsControl](_ItemsControl.md): a control that has an additional *Items* collection. This is a good choice for controls that display a dynamic list of items without selection.
- [Selector](_Selector.md): an *ItemsControl* whose items can be indexed and selected. This is used for [ListBox](_ListBox.md), [ComboBox](_ComboBox.md), [ListView](../Gui.Controls/_ListView.md) or [TabControl](_TabControl.md)
- [RangeBase](_RangeBase.md): is the base class for controls that display a value range like [Slider](_Slider.md) or [ProgressBar](_ProgressBar.md). It adds a *Value*, *Minimum* and *Maximum* property.

# Implementation

In our example we will derive from [Control](_Control.md) base class because our control requires templates to present date and time information. Other features added by more complex base classes are not required. We will follow the steps described in the [tutorial](ExtendingTutorial.md) that describes how to extend NoesisGUI.

C++

```
class DateTime: public Control
{
    NS_IMPLEMENT_INLINE_REFLECTION_(DateTime, Control, "CustomControl.DateTime")
};
```

C#

```
public class DateTime : Control
{
}
```

## Override the Default Style

Controls separate **behavior** from **appearance**. The behavior is defined in code. The appearance is defined by the XAML. The default template used by the control is by convention wrapped into a style that has an implicit key.

XAML

```
<Style TargetType="{x:Type local:DateTime}">
  <Setter Property="Template" Value="{StaticResource AnalogDateTimeTemplate}"/>
</Style>
```

## Properties

Our *DateTime* control needs some public properties to allow users to modify or present the control. We will add the properties *Day*, *Month* and *Year* for representing the date and *Hour*, *Minute* and *Second* for representing the time. We decided to use dependency properties because it provides the following advantages for the users:

- Set the property in a style.
- Bind the property to a data source.
- Use a dynamic resource as the property's value.
- Animate the property.

C++

```
class DateTime: public Control
{
public:
    int GetDay() const
    {
        return GetValue<int>(DayProperty);
    }

    void SetDay(int day)
    {
        SetValue<int>(DayProperty, day);
    }

    int GetMonth() const
    {
        return GetValue<int>(MonthProperty);
    }

    void SetMonth(int month)
    {
        SetValue<int>(MonthProperty, month);
    }

    int GetYear() const
    {
        return GetValue<int>(YearProperty);
    }

    void SetYear(int year)
    {
        SetValue<int>(YearProperty, year);
    }

    int GetHour() const
    {
        return GetValue<int>(HourProperty);
    }

    void SetHour(int hour)
    {
        SetValue<int>(HourProperty, hour);
    }

    int GetMinute() const
    {
        return GetValue<int>(MinuteProperty);
    }

    void SetMinute(int minute)
    {
        SetValue<int>(MinuteProperty, minute);
    }

    int GetSecond() const
    {
        return GetValue<int>(SecondProperty);
    }

    void SetSecond(int second)
    {
        SetValue<int>(SecondProperty, second);
    }

    static const DependencyProperty* DayProperty;
    static const DependencyProperty* MonthProperty;
    static const DependencyProperty* YearProperty;
    static const DependencyProperty* HourProperty;
    static const DependencyProperty* MinuteProperty;
    static const DependencyProperty* SecondProperty;

    NS_IMPLEMENT_INLINE_REFLECTION(DateTime, Control, "CustomControl.DateTime")
    {
        UIElementData* data = NsMeta<UIElementData>(TypeOf<DateTime>());
        data->RegisterProperty<int>(DayProperty, "Day", PropertyMetadata::Create(int(1)));
        data->RegisterProperty<int>(MonthProperty, "Month", PropertyMetadata::Create(int(1)));
        data->RegisterProperty<int>(YearProperty, "Year", PropertyMetadata::Create(int(2000)));
        data->RegisterProperty<int>(HourProperty, "Hour", PropertyMetadata::Create(int(0)));
        data->RegisterProperty<int>(MinuteProperty, "Minute", PropertyMetadata::Create(int(0)));
        data->RegisterProperty<int>(SecondProperty, "Second", PropertyMetadata::Create(int(0)));
    }
};

const DependencyProperty* DateTime::DayProperty;
const DependencyProperty* DateTime::MonthProperty;
const DependencyProperty* DateTime::YearProperty;
const DependencyProperty* DateTime::HourProperty;
const DependencyProperty* DateTime::MinuteProperty;
const DependencyProperty* DateTime::SecondProperty;
```

C#

```
public class DateTime : Control
{
    #region Day property
    public static readonly DependencyProperty DayProperty = DependencyProperty.Register(
        "Day", typeof(int), typeof(DateTime), new PropertyMetadata(1));

    public int Day
    {
        get { return (int)GetValue(DayProperty); }
        set { SetValue(DayProperty, value); }
    }
    #endregion

    #region Month property
    public static readonly DependencyProperty MonthProperty = DependencyProperty.Register(
        "Month", typeof(int), typeof(DateTime), new PropertyMetadata(1));

    public int Month
    {
        get { return (int)GetValue(MonthProperty); }
        set { SetValue(MonthProperty, value); }
    }
    #endregion

    #region Year property
    public static readonly DependencyProperty YearProperty = DependencyProperty.Register(
        "Year", typeof(int), typeof(DateTime), new PropertyMetadata(2000));

    public int Year
    {
        get { return (int)GetValue(YearProperty); }
        set { SetValue(YearProperty, value); }
    }
    #endregion

    #region Hour property
    public static readonly DependencyProperty HourProperty = DependencyProperty.Register(
        "Hour", typeof(int), typeof(DateTime), new PropertyMetadata(0));

    public int Hour
    {
        get { return (int)GetValue(HourProperty); }
        set { SetValue(HourProperty, value); }
    }
    #endregion

    #region Minute property
    public static readonly DependencyProperty MinuteProperty = DependencyProperty.Register(
        "Minute", typeof(int), typeof(DateTime), new PropertyMetadata(0));

    public int Minute
    {
        get { return (int)GetValue(MinuteProperty); }
        set { SetValue(MinuteProperty, value); }
    }
    #endregion

    #region Second property
    public int Second
    {
        get { return (int)GetValue(SecondProperty); }
        set { SetValue(SecondProperty, value); }
    }

    public static readonly DependencyProperty SecondProperty = DependencyProperty.Register(
        "Second", typeof(int), typeof(DateTime), new PropertyMetadata(0));
    #endregion
}
```

## Templates

Using this control in any application will require that you specify a template for the *DateTime* type.

To decouple the UI of your control from its logic, consider using [data binding](DataBindingTutorial.md). This is particularly important when you define the appearance of your control in the [ControlTemplate](_ControlTemplate.md). When you use data binding, you might be able to eliminate the need to reference specific parts of the UI from the code. It's a good idea to avoid referencing elements that are in the ControlTemplate because when the code references a specific element and the ControlTemplate is changed, the referenced element needs to be included in the new ControlTemplate.

We are going to provide two different approaches to demonstrate the power of control [styling and templating](StylingTutorial.md).

### Digital Clock

The *first* template shows the date and time as a digital clock:

![CustomControlTutorialImg1.jpg](https://www.noesisengine.com/docs/CustomControlTutorialImg1.jpg)

```
<!-- Digital clock style -->
<ControlTemplate x:Key="DigitalDateTimeTemplate" TargetType="{x:Type local:DateTime}">
  <Viewbox>
    <StackPanel>
      <StackPanel Orientation="Horizontal" HorizontalAlignment="Center" TextElement.FontSize="40">
        <TextBlock Text="{Binding Hour, StringFormat=G, RelativeSource={RelativeSource TemplatedParent}}"/>
        <TextBlock Text=":"/>
        <TextBlock Text="{Binding Minute, StringFormat={}{0:00}, RelativeSource={RelativeSource TemplatedParent}}"/>
      </StackPanel>
      <StackPanel Orientation="Horizontal" HorizontalAlignment="Center" TextElement.FontSize="16">
        <TextBlock Text="{Binding Day, StringFormat=G, RelativeSource={RelativeSource TemplatedParent}}"/>
        <TextBlock Text="/"/>
        <TextBlock Text="{Binding Month, StringFormat=G, RelativeSource={RelativeSource TemplatedParent}}"/>
        <TextBlock Text="/"/>
        <TextBlock Text="{Binding Year, StringFormat=G, RelativeSource={RelativeSource TemplatedParent}}"/>
      </StackPanel>
    </StackPanel>
  </Viewbox>
</ControlTemplate>

<Style x:Key="DigitalStyle">
  <Setter Property="local:DateTime.Template" Value="{StaticResource DigitalDateTimeTemplate}"/>
</Style>
```

### Analog Clock

The *second* template is an attempt to simulate an analog clock:

![CustomControlTutorialImg2.jpg](https://www.noesisengine.com/docs/CustomControlTutorialImg2.jpg)

```
<!-- Converters needed -->
<local:HoursConverter x:Key="DateTimeHoursConverter"/>
<local:MinutesConverter x:Key="DateTimeMinutesConverter"/>
<local:SecondsConverter x:Key="DateTimeSecondsConverter"/>

<!-- Analog clock style -->
<ControlTemplate x:Key="AnalogDateTimeTemplate" TargetType="{x:Type local:DateTime}">
  <Viewbox>
    <Grid Height="200" Width="200">
      <Ellipse StrokeThickness="6" Stretch="Uniform">
        <Ellipse.Stroke>
          <LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
            <GradientStop Color="#FF4D4D4D" Offset="1"/>
            <GradientStop Color="Gray"/>
          </LinearGradientBrush>
        </Ellipse.Stroke>
      </Ellipse>
      <Ellipse StrokeThickness="5" Stretch="Uniform" Margin="5" Fill="White">
        <Ellipse.Stroke>
          <LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
            <GradientStop Color="#FF333333" Offset="0"/>
            <GradientStop Color="#FF999999" Offset="1"/>
          </LinearGradientBrush>
        </Ellipse.Stroke>
      </Ellipse>

      <Grid Margin="18" TextElement.FontSize="24">
        <TextBlock Text="12" HorizontalAlignment="Center" VerticalAlignment="Top"/>
        <TextBlock Text="3" HorizontalAlignment="Right" VerticalAlignment="Center"/>
        <TextBlock Text="6" HorizontalAlignment="Center" VerticalAlignment="Bottom"/>
        <TextBlock Text="9" HorizontalAlignment="Left" VerticalAlignment="Center"/>
      </Grid>

      <Path x:Name="BarS" Data="M100,100L100,20" Stroke="#FF333333" StrokeThickness="2"
                       RenderTransformOrigin="0.5,0.5">
        <Path.RenderTransform>
          <TransformGroup>
            <ScaleTransform/>
            <SkewTransform/>
            <RotateTransform Angle="{Binding Second,
                                   Converter={StaticResource DateTimeSecondsConverter},
                                   RelativeSource={RelativeSource TemplatedParent}}"/>
            <TranslateTransform/>
          </TransformGroup>
        </Path.RenderTransform>
      </Path>
      <Path x:Name="BarM" Data="M100,100L100,20" Stroke="Red" StrokeThickness="4"
                       RenderTransformOrigin="0.5,0.5">
        <Path.RenderTransform>
          <TransformGroup>
            <ScaleTransform/>
            <SkewTransform/>
            <RotateTransform Angle="{Binding Minute,
                                   Converter={StaticResource DateTimeMinutesConverter},
                                   RelativeSource={RelativeSource TemplatedParent}}"/>
            <TranslateTransform/>
          </TransformGroup>
        </Path.RenderTransform>
      </Path>
      <Path x:Name="BarH" Data="M100,100L100,40" Stroke="#FFCA0000" StrokeThickness="8"
                       RenderTransformOrigin="0.5,0.5">
        <Path.RenderTransform>
          <TransformGroup>
            <ScaleTransform/>
            <SkewTransform/>
            <RotateTransform Angle="{Binding Hour,
                                   Converter={StaticResource DateTimeHoursConverter},
                                   RelativeSource={RelativeSource TemplatedParent}}"/>
            <TranslateTransform/>
          </TransformGroup>
        </Path.RenderTransform>
      </Path>

      <Ellipse HorizontalAlignment="Center" VerticalAlignment="Center" Width="20" Height="20">
        <Ellipse.Fill>
          <RadialGradientBrush>
            <GradientStop Color="#FF343434" Offset="0.2"/>
            <GradientStop Color="#FF666666" Offset="1"/>
            <GradientStop Color="Gray" Offset="0.95"/>
            <GradientStop Color="#FF999999"/>
            <GradientStop Color="#FF404040" Offset="0.9"/>
          </RadialGradientBrush>
        </Ellipse.Fill>
      </Ellipse>
    </Grid>
  </Viewbox>
</ControlTemplate>

<Style TargetType="{x:Type local:DateTime}">
  <Setter Property="Template" Value="{StaticResource AnalogDateTimeTemplate}"/>
</Style>
```

## Converters

The analog-clock style needs a few [converters](_BaseValueConverter.md) to transform control properties into the appropriate rotation angles.

C++

```
class HoursConverter: public BaseValueConverter
{
public:
    bool TryConvert(BaseComponent* value, const Type* type, BaseComponent* /*parameter*/,
        Ptr<BaseComponent>& result)
    {
        if (Boxing::CanUnbox<int>(value) && type == TypeOf<float>())
        {
            int hours = Boxing::Unbox<int>(value);
            result = Boxing::Box(hours * 30.0f);
            return true;
        }

        return false;
    }

    NS_IMPLEMENT_INLINE_REFLECTION_(HoursConverter, BaseValueConverter, "CustomControl.HoursConverter")
};

class MinutesConverter: public BaseValueConverter
{
public:
    bool TryConvert(BaseComponent* value, const Type* type, BaseComponent* /*parameter*/,
        Ptr<BaseComponent>& result)
    {
        if (Boxing::CanUnbox<int>(value) && type == TypeOf<float>())
        {
            int minutes = Boxing::Unbox<int>(value);
            result = Boxing::Box(minutes * 6.0f);
            return true;
        }

        return false;
    }

    NS_IMPLEMENT_INLINE_REFLECTION_(MinutesConverter, BaseValueConverter, "CustomControl.MinutesConverter")
};

class SecondsConverter: public BaseValueConverter
{
public:
    bool TryConvert(BaseComponent* value, const Type* type, BaseComponent* /*parameter*/,
        Ptr<BaseComponent>& result)
    {
        if (Boxing::CanUnbox<int>(value) && type == TypeOf<float>())
        {
            int seconds = Boxing::Unbox<int>(value);
            result = Boxing::Box(seconds * 6.0f);
            return true;
        }

        return false;
    }

    NS_IMPLEMENT_INLINE_REFLECTION_(SecondsConverter, BaseValueConverter, "CustomControl.SecondsConverter")
};
```

C#

```
public class HoursConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        int hours = (int)value;
        return hours * 30.0f;
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}

public class MinutesConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        int minutes = (int)value;
        return minutes * 6.0f;
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}

public class SecondsConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        int seconds = (int)value;
        return seconds * 6.0f;
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
```

# Improvements

A cool feature for this control could be automatic updating from system time and date. We can achieve this with a timer in the control instance that updates the time and date values whenever timer is ticked. Then we can add a boolean property to allow this feature to be enabled or disabled from within XAML.