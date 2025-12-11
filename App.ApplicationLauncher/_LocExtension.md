Source: https://www.noesisengine.com/docs/App.ApplicationLauncher._LocExtension.html

# LocExtension Class

## namespace [NoesisApp](../Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

Implements a markup extension that supports references to a localization [ResourceDictionary](../Gui.Core/_ResourceDictionary.md).

Provides a value for any XAML property attribute by looking up a reference in the [ResourceDictionary](../Gui.Core/_ResourceDictionary.md) defined by the Source attached property. Values will be re-evaluated when the Source attached property changes.

If used with a string or object property, and the provided resource key is not found, the [LocExtension](_LocExtension.md) will return a string in the format "<Loc !%s>" where %s is replaced with the key.

A Converter can also be specified, with an optional ConverterParameter.

This example shows the full setup for a [LocExtension](_LocExtension.md). It utilizes the [RichText](_RichText.md) attached property to support BBCode markup in the localized strings. The Loc.Source property references the "Language\_en-gb.xaml" [ResourceDictionary](../Gui.Core/_ResourceDictionary.md) below.

```
<StackPanel
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions"
  noesis:Loc.Source="Language_en-gb.xaml">
  <Image Source="{noesis:Loc Flag}"/>
  <TextBlock noesis:RichText.Text="{noesis:Loc SoundLabel}"/>
  <TextBlock noesis:RichText.Text="{noesis:Loc TitleLabel, Converter={StaticResource CaseConverter}, ConverterParameter=UpperCase}"/>
</StackPanel>
```

This is the contents of a "Language\_en-gb.xaml" localized [ResourceDictionary](../Gui.Core/_ResourceDictionary.md):

Language\_en-gb.xaml

```
<ResourceDictionary
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <ImageBrush x:Key="Flag" ImageSource="Flag_en-gb.png" Stretch="Fill"/>
  <sys:String x:Key="TitleLabel">[b]Localization Sample[/b]</sys:String>
  <sys:String x:Key="SoundLabel">A [i]sound[/i] label</sys:String>
</ResourceDictionary>
```

# Inheritance Hierarchy

• [MarkupExtension](../Gui.Core/_MarkupExtension.md)

• *LocExtension*

# Properties

| Name | Description |
| --- | --- |
| ○ *Converter* | Gets or sets a converter to use on any found resource |
| ○ *ConverterParameter* | Gets or sets the value of the parameter to use with the converter |
| ○ *ResourceKey* | Gets or sets the value of the key to use when finding a resource |

● Dependency Property   ○ Reflection Property

# Attached Properties

| Name | Description |
| --- | --- |
| ● *Resources* | Gets the dictionary where localization resources are found |
| ● *Source* | Gets or sets the value of the Source property of the localization dictionary |

# Methods

## From [MarkupExtension](../Gui.Core/_MarkupExtension.md)

| Name | Description |
| --- | --- |
|  *ProvideValue(provider)* | Returns an object that is provided as the value of the target property for this extension |

# Events

LocExtension has no events