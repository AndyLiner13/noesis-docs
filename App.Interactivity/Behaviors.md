Source: https://www.noesisengine.com/docs/App.Interactivity.Behaviors.html

# Behaviors Architecture

*Behaviors architecture* is a new concept, introduced with Microsoft Blend, to encapsulate pieces of functionality into reusable components. These components can be attached to controls to give them an additional behavior.

The idea behind behaviors is to give the designer more flexibility to design complex user interactions without writing any code. Developers can provide functionality writing triggers, actions and behaviors that are cleanly encapsulated and reusable by both developers and designers. Likewise, designers are empowered to add a new level of interactive functionality to their work without ever having to touch a code file.

Example of a behaviors are **drag&drop**, **input validation**, **pan and zoom** or **re-position** of elements. The list of possible behaviors is very long.

NOTE

The implementation of Behaviors is part of the [Application Framework](/Gui.Core/ApplicationTutorial.md).

# Triggers and Actions

To anyone with some WPF background, triggers and actions should sound familiar. Behaviors architecture introduces a similar model, and allows you to write your own triggers and actions - opening a whole new world of possibilities for what kinds of functionality you can create and reuse in your own applications.

An [Action](/App.Interactivity/_TriggerAction.md) is an object that can be invoked to perform an operation. If you think that sounds pretty vague, you're right. The scope of an action is not constrained: if you can write the code to do something, you could write an action to do the same thing. That said, actions are best written to *perform operations* that are largely *atomic* in nature. That is, actions work best when they don't rely on external state that needs to be persisted between invocations of the action, and that don't have any dependencies on other actions existing or running in a particular order relative to their invocation.

For example: **change** a property, **call** a method, **open** a window, **navigate** to a page or set **focus**.

Actions aren't particularly useful on their own: they provide functionality to do something, but no way to activate that functionality. In order to invoke an action, we need a [Trigger](/App.Interactivity/_TriggerBase.md). Triggers are objects that contain one or more actions and invoke those actions in response to some stimulus. One very common trigger is one that fires in response to an event (an [EventTrigger](/App.Interactivity/_EventTrigger.md)). Other examples might include a trigger that fires on a timer, or a trigger that fires when some data changes.

NOTE

One important thing to note is that triggers and actions are generally meant to be used together arbitrarily. In other words, you should avoid writing an action that makes assumptions about the type of trigger that invokes it, or a trigger that makes assumptions about the actions that belong to it. If you find yourself needing a tight coupling between a trigger and action, you should instead consider a behavior.

## How does it work?

To add triggers and actions to an element you need some kind of extension point: an attached property called *Interaction.Triggers*.

This attached property holds the list of triggers for that element and passes a reference to the element into the trigger. The trigger can then register itself to events or property changes to react and invoke the actions it contains.

The idea is simple, but very clever. We don't need any new infrastructure, we just reuse the existing one.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
    <TextBox Text="{Binding Name}">
      <b:Interaction.Triggers>
        <b:EventTrigger EventName="Loaded">
          <noesis:SetFocusAction/>
        </b:EventTrigger>
      </b:Interaction.Triggers>
    </TextBox>
</Border>
```

C++

```
class SetFocusAction final: public NoesisApp::TargetedTriggerActionT<Noesis::UIElement>
{
    void Invoke(Noesis::BaseComponent* parameter) override
    {
        UIElement* element = GetTarget();
        if (element != nullptr)
        {
            element->Focus();
        }
    }

    //...
};
```

C#

```
public class SetFocusAction: public NoesisApp.TargetedTriggerActionT<Noesis.UIElement>
{
    protected override void Invoke(object parameter)
    {
        UIElement element = Target;
        if (element != null)
        {
            element.Focus();
        }
    }
};
```

NOTE

Microsoft Blend behaviors architecture classes (provided by [Microsoft.Xaml.Behaviors.Wpf](https://github.com/microsoft/XamlBehaviorsWpf) NuGet) are mapped to the following namespace:

- **http://schemas.microsoft.com/xaml/behaviors**

The namespace is usually associated with **behaviors:** or just **b:** prefix.
It is automatically added to your xaml file when you drag an action or behavior to any control in Blend.

For those referencing old Interactivity and Interactions assemblies the namespaces used are:

- **http://schemas.microsoft.com/expression/2010/interactivity**
- **http://schemas.microsoft.com/expression/2010/interactions**

In this case the associated prefixes are **i:** and **ei:** respectively.

Extensions developed by [Noesis](https://www.nuget.org/packages/Noesis.GUI.Extensions) are defined in **NoesisGUIExtensions** namespace, and you will find them with the **noesis:** prefix.

## Supported Triggers

| Prefix | Name |
| --- | --- |
| i: | [EventTrigger](/App.Interactivity/_EventTrigger.md) |
| ei: | [TimerTrigger](/App.Interactivity/_TimerTrigger.md) |
| ei: | [KeyTrigger](/App.Interactivity/_KeyTrigger.md) |
| ei: | [PropertyChangedTrigger](/App.Interactivity/_PropertyChangedTrigger.md) |
| ei: | [DataTrigger](/App.Interactivity/_DataTrigger.md) |
| ei: | [StoryboardCompletedTrigger](/App.Interactivity/_StoryboardCompletedTrigger.md) |
| noesis: | [GamepadTrigger](/App.Interactivity/_GamepadTrigger.md) |
| noesis: | [DataEventTrigger](/App.Interactivity/_DataEventTrigger.md) |

## Supported Actions

| Prefix | Name |
| --- | --- |
| i: | [InvokeCommandAction](/App.Interactivity/_InvokeCommandAction.md) |
| ei: | [ChangePropertyAction](/App.Interactivity/_ChangePropertyAction.md) |
| ei: | [GoToStateAction](/App.Interactivity/_GoToStateAction.md) |
| ei: | [RemoveElementAction](/App.Interactivity/_RemoveElementAction.md) |
| ei: | [ControlStoryboardAction](/App.Interactivity/_ControlStoryboardAction.md) |
| ei: | [LaunchUriOrFileAction](/App.Interactivity/_LaunchUriOrFileAction.md) |
| ei: | [PlaySoundAction](/App.Interactivity/_PlaySoundAction.md) |
| noesis: | [SetFocusAction](/App.Interactivity/_SetFocusAction.md) |
| noesis: | [MoveFocusAction](/App.Interactivity/_MoveFocusAction.md) |
| noesis: | [SelectAction](/App.Interactivity/_SelectAction.md) |
| noesis: | [SelectAllAction](/App.Interactivity/_SelectAllAction.md) |

# Behaviors

Whereas the concepts of triggers and actions have been previously established in WPF, the concept of a [Behavior](/App.Interactivity/_Behavior.md) is a new one. At a glance, a behavior looks similar to an action: a self-contained unit of functionality. The main difference is that actions expect to be invoked, and when invoked, they will perform some operation. A behavior does not have the concept of invocation; instead, it acts more as an **add-on** to an object: optional functionality that can be attached to an object if desired. It may do certain things in response to stimulus from the environment, but there is no guarantee that the user can control what this stimulus is: it is up to the behavior author to determine what can and cannot be customized.

As an example, consider a behavior that allows the user to drag the object the behavior is attached to around with the mouse. The behavior needs to listen to the *mouse down*, *mouse move*, and *mouse up* events on the attached object. In response to the *mouse down*, behavior will record the mouse position, hook up the mouse move and mouse up handlers and capture the mouse input. On *mouse move*, it will update the position of the object as well as the mouse position. On *mouse up*, it will release mouse capture and unhook mouse move and mouse up handlers.

One approach might be to try and use *EventTriggers* for each of these events, and write a *StartDragAction*, *MoveDragAction* and *StopDragAction* to invoke in each case. However, it soon becomes apparent that this scenario is not well-addressed by actions because it needs to store state between invocations (previous mouse position and the state of the drag), and the operation isn't atomic. Instead, we can write a behavior that wraps the exact functionality outlined above into a reusable component.

## How does it work?

To add behaviors to an element we will also use an attached property, called *Interaction.Behaviors*.

This attached property holds the list of behaviors for that element and passes a reference to the element into the behavior. The behavior then can register itself to events and property changes to extend the functionality of the element.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors">
    <Border Background="Silver" Margin="100">
      <Rectangle Width="200" Height="100" Fill="Red">
        <b:Interaction.Behaviors>
          <b:MouseDragElementBehavior ConstrainToParentBounds="True"/>
        </b:Interaction.Behaviors>
      </Rectangle>
    </Border>
</Grid>
```

C++

```
class MouseDragElementBehavior: public NoesisApp::BehaviorT<Noesis::FrameworkElement>
{
public:
    float GetX() const { return GetValue<float>(XProperty); }
    void SetX(float x) { SetValue<float>(XProperty); }

    float GetY() const { return GetValue<float>(YProperty); }
    void SetY(float y) { SetValue<float>(YProperty); }

    bool GetConstrainToParentBounds() const { return GetValue<bool>(ConstrainToParentBoundsProperty); }
    void SetConstrainToParentBounds(bool value) { SetValue<bool>(ConstrainToParentBoundsProperty); }

protected:
    void OnAttached()
    {
        FrameworkElement* obj = GetAssociatedObject();

        _transform = *new Noesis::TranslateTransform();
        obj->SetRenderTransform(_transform);
        obj->MouseLeftButtonDown() += MakeDelegate(this, &MouseDragElementBehavior::OnMouseLeftButtonDown);
    }

    void OnDetaching()
    {
        FrameworkElement* obj = GetAssociatedObject();

        _transform = 0;
        obj->SetRenderTransform(0);
        obj->MouseLeftButtonDown() -= MakeDelegate(this, &MouseDragElementBehavior::OnMouseLeftButtonDown);
    }

    // ...
};
```

C#

```
public class MouseDragElementBehavior: NoesisApp.Behavior<Noesis.FrameworkElement>
{
    public float X
    {
        get { return (float)GetValue(XProperty); }
        set { SetValue(XProperty, value); }
    }

    public float Y
    {
        get { return (float)GetValue(YProperty); }
        set { SetValue(YProperty, value); }
    }

    public bool ConstrainToParentBounds
    {
        get { return (bool)GetValue(ConstrainToParentBoundsProperty); }
        set { SetValue(ConstrainToParentBoundsProperty, value); }
    }

    protected override void OnAttached()
    {
        FrameworkElement associatedObject = AssociatedObject;

        _transform = new TranslateTransform();
        associatedObject.RenderTransform = _transform;
        associatedObject.MouseLeftButtonDown += OnMouseLeftButtonDown;
    }

    protected override void OnDetaching()
    {
        FrameworkElement associatedObject = AssociatedObject;

        _transform = null;
        associatedObject.RenderTransform = null;
        associatedObject.MouseLeftButtonDown -= OnMouseLeftButtonDown;
    }

    // ...
}
```

## Supported Behaviors

| Prefix | Name |
| --- | --- |
| ei: | [ConditionBehavior](/App.Interactivity/_ConditionBehavior.md) |
| ei: | [MouseDragElementBehavior](/App.Interactivity/_MouseDragElementBehavior.md) |
| ei: | [TranslateZoomRotateBehavior](/App.Interactivity/_TranslateZoomRotateBehavior.md) |
| noesis: | [CollectionFilterBehavior](/App.Interactivity/_CollectionFilterBehavior.md) |
| noesis: | [CollectionSortBehavior](/App.Interactivity/_CollectionSortBehavior.md) |
| noesis: | [BackgroundEffectBehavior](/App.Interactivity/_BackgroundEffectBehavior.md) |
| noesis: | [LineDecorationBehavior](/App.Interactivity/_LineDecorationBehavior.md) |

# Styles

Sometimes it is useful to define actions and behaviors for a type of control. Instead of adding the corresponding interactivity attached property for each instance of that control we would prefer to define that once in a [Style](/Gui.Core/_Style.md) so it applies automatically to all of them.

The problem we will find is that *Interaction.Behaviors* and *Interaction.Triggers* are private attached properties that cannot be directly set from XAML.

To workaround this problem we created a new pair of attached properties that will allow you to define a collection of actions and behaviors in a style. They are called *StyleInteraction.Triggers* and *StyleInteraction.Behaviors*, and are defined inside the namespace *NoesisGUIExtensions*. They can be used like this:

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions;assembly=Noesis.GUI.Extensions">
    <Grid.Resources>
      <Style TargetType="{x:Type Button}" BasedOn="{StaticResource {x:Type Button}}">
        <Setter Property="noesis:StyleInteraction.Triggers">
          <Setter.Value>
            <noesis:StyleTriggerCollection>
              <b:EventTrigger EventName="Click">
                <b:PlaySoundAction Source="buttonClick.wav"/>
              </b:EventTrigger>
            </noesis:StyleTriggerCollection>
          </Setter.Value>
        </Setter>
        <Setter Property="noesis:StyleInteraction.Behaviors">
          <Setter.Value>
            <noesis:StyleBehaviorCollection>
              <b:MouseDragElementBehavior/>
            </noesis:StyleBehaviorCollection>
          </Setter.Value>
        </Setter>
      </Style>
    </Grid.Resources>
    <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
      <Button Content="Start"/>
      <Button Content="Options"/>
      <Button Content="Exit"/>
    </StackPanel>
</Grid>
```

Once the style is applied to the control the attached property will get *Interaction.Triggers* or *Interaction.Behaviors* collections from the control and clone the style actions or behaviors there, having the same result as if you have specified them directly in the control.