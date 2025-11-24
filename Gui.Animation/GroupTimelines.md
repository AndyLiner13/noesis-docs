Source: https://www.noesisengine.com/docs/Gui.Animation.GroupTimelines.html

# Group Timelines

Here are the timelines deriving from TimelineGroup. This timelines can contain other timelines to create complex animations

# TimelineGroup

<http://msdn.microsoft.com/en-us/library/system.windows.media.animation.timelinegroup.aspx>

Defines a children collection of timeline objects. This class overrides the AllocateClock method, creating a GroupClock which contains the same number of clocks as children the collection has.

| Methods | | --- | --- | --- |
| Name | Sup | Comments |
| CreateClock | Yes | Renamed to AllocateClock |

| Dependency Properties | | | --- | --- | --- | --- |
| Name | Att | Sup | Comments |
| ChildrenProperty | No | Yes | Not declared as dependency property (TODO) |

# ParallelTimeline

<http://msdn.microsoft.com/en-us/library/system.windows.media.animation.paralleltimeline.aspx>

| Methods | | --- | --- | --- |
| Name | Sup | Comments |
| Clone | No | CloneCurrentValue | No | Dependency Properties | | | --- | --- | --- | --- |
| Name | Att | Sup | Comments |
| SlipBehaviorProperty | No | No ## Members

- **SlipBehavior**: this property is not currently supported

# Storyboard

<http://msdn.microsoft.com/en-us/library/system.windows.media.animation.storyboard.aspx>

| Methods | | --- | --- | --- |
| Name | Sup | Comments |
| Begin | Yes | Clone | No | GetCurrentGlobalSpeed | No | GetCurrentIteration | No | GetCurrentProgress | No | GetCurrentState | No | GetCurrentTime | No | GetIsPaused | No | Pause | No | Remove | Yes | Resume | No | Seek | No | SeekAlignedToLastTick | No | SetSpeedRatio | No | SkipToFill | No | Stop | No | Dependency Properties | | | --- | --- | --- | --- |
| Name | Att | Sup | Comments |
| TargetNameProperty | Yes | Yes | TargetProperty | Yes | Yes | TargetPropertyProperty | Yes | Yes This is most important class of the group timelines. It allows the execution of the timelines that contains, assigning the resulting values of each child to a different target if desired.

Also, a storyboard is mandatory to execute any animation from XAML. Even if it's a single animation, it must belong to a storyboard.

## Members

- **TargetName (attached)**: if assigned to the storyboard, fixes the target object to apply the resulting animations of the children timelines, but every child can be assigned to it's own TargetName to animate a different object
- **Target (attached)**: similar to the above property, buy allows setting the target using a binding expression instead of by name
- **TargetProperty (attached)**: target property, that can also be specified at storyboard level, or at timeline child level.

## Methods

- **Begin**: Starts a storyboard animation by code. If the controllable parameter is set to null, the whole animation can be cancelled at any time using the Remove method
- **Remove**: Stops the animation, removing from the targets the animated values set by the storyboard.

```
Ptr<DoubleAnimation> animation = NsCreateComponent<DoubleAnimation>();
animation->SetTo(40.0f);

Ptr<Storyboard> storyboard = NsCreateComponent<Storyboard>();
storyboard->GetChildren()->Add(animation);

storyboard->Begin(targetObject, true, HandoffBehavior_SnapshotAndReplace);
...
storyboard->Remove(targetObject);
```

Here is a complete XAML sample, starting an storyboard from a trigger event

```
<Button Content="Animate me!">
<Button.Triggers>
    <EventTrigger RoutedEvent="Button.Click">
    <EventTrigger.Actions>
        <BeginStoryboard>
            <Storyboard>
                <ThicknessAnimation Storyboard.TargetName="Border" Storyboard.TargetProperty="BorderThickness" To="20,20" AutoReverse="True"/>
                <ColorAnimation Storyboard.TargetName="Border" Storyboard.TargetProperty="Background.Color" From="Red" To="Green" AutoReverse="True" BeginTime="0:0:2"/>
                <PointAnimation Storyboard.TargetName="Rectangle" Storyboard.TargetProperty="Fill.Center" To="0.3,0.3" AutoReverse="True" BeginTime="0:0:4"/>
                <RectAnimation Storyboard.TargetName="Path" Storyboard.TargetProperty="Data.Rect" To="10,10,300,50" AutoReverse="True" BeginTime="0:0:6"/>
            </Storyboard>
        </BeginStoryboard>
    </EventTrigger.Actions>
    </EventTrigger>
</Button.Triggers>
</Button>
```