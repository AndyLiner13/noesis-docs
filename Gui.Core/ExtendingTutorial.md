Source: https://www.noesisengine.com/docs/Gui.Core.ExtendingTutorial.html

# Extending NoesisGUI

Being based in XAML, NoesisGUI is a framework that can be extended in many ways. For example, you can create your own *Converters*, [Commands](/Gui.Core/CommandsTutorial.md), [CustomControls](/Gui.Core/CustomControlTutorial.md), [UserControls](/Gui.Core/UserControlTutorial.md) or [code-behind](/Gui.Core/CodeBehindTutorial.md) classes. This tutorial is focused on the steps that have to be performed to extend NoesisGUI using your own classes.

# Example

First thing we are going to do is writing a very simple XAML with a [TextBox](/Gui.Core/_TextBox.md) where you can write text and a [TextBlock](/Gui.Core/_TextBlock.md) that outputs the text you write filtered through a [converter](/Gui.Core/_BaseValueConverter.md). The converter we are going to implement transforms the input to upper case.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:local="clr-namespace:Sample">
  <Grid.Resources>
    <local:UppercaseConverter x:Key="Converter"/>
  </Grid.Resources>
  <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center" Background="Blue">
    <TextBox x:Name="Input" Width="100"/>
    <TextBlock Text="{Binding Text, ElementName=Input, Converter={StaticResource Converter}}"
               Margin="5"/>
  </StackPanel>
</Grid>
```

The highlighted line remarks where the extended class, in this case under the namespace *Sample,* is being used. If this XAML is used as it is, we will receive a warning indicating that the type *Sample.UppercaseConverter* is not known. We need to implement a new class registered with this name. Let's see how to do this in both C++ and C# languages.

## Extending in C++

```
#include <NsCore/Noesis.h>
#include <NsCore/TypeOf.h>
#include <NsCore/RegisterComponent.h>
#include <NsCore/ReflectionImplement.h>
#include <NsGui/BaseValueConverter.h>

using namespace Noesis;

namespace Sample
{
    class UppercaseConverter final: public BaseValueConverter
    {
    public:
        bool TryConvert(BaseComponent* value, const Type* targetType, BaseComponent* /*parameter*/,
            Ptr<BaseComponent>& result) override
        {
            if (targetType == TypeOf<NsString>() && Boxing::CanUnbox<NsString>(value))
            {
                NsString text = Boxing::Unbox<NsString>(value);
                text.make_upper();
                result = Boxing::Box<NsString>(text);
                return true;
            }

            return false;
        }

    private:
        NS_IMPLEMENT_INLINE_REFLECTION_(UppercaseConverter, BaseValueConverter, "Sample.UppercaseConverter")
    };
}
```

The code shown above illustrates the key points that are needed to implement a new class:

- New classes must always derive from their corresponding base class. In this case the base class is [BaseValueConverter](/Gui.Core/_BaseValueConverter.md) because we are interested in the *IValueConverter* interface.
- The new class must implement the required methods. *BaseValueConverter* requires us to implement *TryConvert* and *TryConvertBack*, but in this specific sample, conversion in only one direction, we only need implementing *TryConvert*. It is implemented by [unboxing](/Gui.Core/CppArchitectureGuide.md#boxing) the text, converting to uppercase and returning the boxed object.
- And last, [reflection tags](/Gui.Core/CppArchitectureGuide.md#reflection) must be added to our new class:

> ```
> NS_IMPLEMENT_INLINE_REFLECTION_(UppercaseConverter, BaseValueConverter, "Sample.UppercaseConverter")
> ```
>
> Here we are indicating that our class *UppercaseConverter* derives from *BaseValueConverter* and is registered with the name *'UppercaseConverter'* under the namespace *'Sample'*. This is the identifier that XAMLs will be using to reference this native class.

Before using this class inside a XAML it must be registered in the component factory. This must be done after Noesis initialization and before loading the corresponding XAML. Our [application framework](/Gui.Core/ApplicationTutorial.md) provides a virtual function that can be used for this purpose:

```
class AppLauncher final: public ApplicationLauncher
{
private:
    void RegisterComponents() const override
    {
        RegisterComponent<Sample::UppercaseConverter>();
    }
}
```

Once the class is properly registered, the XAML will load without errors and our converter will accordingly be used.

![ExtendingTutorialImg1.jpg](/ExtendingTutorialImg1/jpg.md)

## Extending in C#

Everything is easier in C# because the registration is automatically done internally and we don't need to apply reflection macros because reflection is already supported out of the box. You just need to create the class *UppercaseConverter* under the namespace *Sample* and implement the *IValueConverter* interface.

```
using System;
using System.Globalization;
using Noesis;

namespace Sample
{
    public class UppercaseConverter : IValueConverter
    {
        public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
        {
            return ((string)value).ToUpper();
        }
        public object ConvertBack(object value, Type targetType, object parameter,
            CultureInfo culture)
        {
            return null;
        }
    }
}
```