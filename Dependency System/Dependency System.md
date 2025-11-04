# Dependency System

## Table of Contents

- [Introduction](#introduction)
- [DependencyObject](#dependencyobject)
  - [Introduction](#introduction-1)
  - [Implementation](#implementation)
- [DependencyProperty](#dependencyproperty)
  - [Introduction](#introduction-2)
  - [Implementation](#implementation-1)
- [PropertyMetadata](#propertymetadata)
  - [Default Value](#default-value)
  - [Property Changed Callback](#property-changed-callback)
  - [Coerce Value Callback](#coerce-value-callback)

## Introduction

One of the primary architectural philosophies used in building declarative interfaces was a preference for properties over methods or events. Properties are declarative and allow you to more easily specify intent instead of action. This also supported a model driven, or data driven, system for displaying user interface content. This philosophy had the intended effect of creating more properties that you could bind to, in order to better control the behavior of an application.

In order to have more of the system driven by properties, a richer property system than what reflection provides was needed. A simple example of this richness is change notifications. In order to enable two way binding, you need both sides of the bind to support change notification. In order to have behavior tied to property values, you need to be notified when the property value changes.

UI provides a richer property system, derived from the [DependencyObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html) type. The property system is truly a "dependency" property system in that it tracks dependencies between property expressions and automatically revalidates property values when dependencies change. For example, if you have a [DependencyProperty](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyProperty.html) that inherits (like FontSize), the system is automatically updated if the property changes on a parent of an element that inherits the value.

One of the most important concepts in the property system are property [Expressions](https://www.noesisengine.com/docs/Gui.DependencySystem._Expression.html). Through expressions a property value can be calculated and updated in many different forms: a expression can assign a value from a ResourceDictionary, can be bound to another object property or data bound.

The property system also provides for sparse storage of property values. Because objects can have dozens (if not hundreds) of properties, and most of the values are in their default state (inherited, set by styles, etc.), not every instance of an object needs to have the full weight of every property defined on it.

The final new feature of the property system is the notion of attached properties. UI elements are built on the principle of composition and component reuse. It is often the case that some containing element (like a Grid layout element) needs additional data on child elements to control its behavior (like the Row/Column information). Instead of associating all of these properties with every element, any object is allowed to provide property definitions for any other object.

## DependencyObject

### Introduction

The DependencyObject base class enables derived objects to use the dependency property system.

It also provides the following services and characteristics:

- Dependency property hosting support. You register a dependency property by calling the **RegisterProperty** or **RegisterPropertyRO** (read-only property) method, and storing the created property as a public static field in your class.
- Attached property hosting support. You register an attached property by calling the RegisterProperty method, and storing the created property as a public static field in your class. Your attached property can then be set on any class that derives from DependencyObject.
- Get, set, and clear utility methods for values of any dependency properties that exist on the DependencyObject.
- Metadata, coerce value support, property changed notification, and override callbacks for dependency properties or attached properties. Also, the DependencyObject class facilitates the per-owner property metadata for a dependency property.

It is the common base class for classes derived from Visual, UIElement, or Freezable.

### Implementation

Supposing we have a class deriving from DependencyObject:

```cpp
/// A button that raises Click event after a delay time
class DelayedButton: public Button
{
    NS_DECLARE_REFLECTION(DelayedButton, Button)
};
```

Inheritors must take care of some important points about NoesisGUI implementation of the DependencyObject:

1. DependencyObject is an **IComponentInitializer** class. Before object is initialized, all value modifications are not notified, and expressions are not evaluated (that means that resources and bindings are not resolved). Derived classes must initialize instance members that are not dependency properties overriding the **OnInit** function. Inheritors must call parent implementation to not break dependency object initialization:

   ```cpp
   void DelayedButton::OnInit()
   {
       ParentClass::OnInit();

       InitComponent(mOtherInfo);
   }
   ```

2. DependencyObject provides an **OnPropertyChanged** function to notify inheritors of property changes. Inheritors must call parent implementation to not break the notification system:

   ```cpp
   NsBool DelayedButton::OnPropertyChanged(const DependencyPropertyChangedEventArgs& e)
   {
       NsBool handled = ParentClass::OnPropertyChanged(e);

       if (!handled)
       {
           if (e.prop == DelayProperty)
           {
               // property change management here
               return true;
           }
       }

       return handled;
   }
   ```

## DependencyProperty

### Introduction

The purpose of dependency properties is to provide a way to compute the value of a property based on the value of other inputs. These other inputs might include system properties such as themes and user preference, just-in-time property determination mechanisms such as data binding and animations/storyboards, multiple-use templates such as resources and styles, or values known through parent-child relationships with other elements in the element tree.

In addition, a dependency property can be implemented to provide self-contained validation, default values, callbacks that monitor changes to other properties, and a system that can coerce property values based on potentially runtime information.

Derived classes can also change some specific characteristics of an existing property by overriding dependency property metadata, rather than overriding the actual implementation of existing properties or creating new properties.

### Implementation

NoesisGUI implements dependency property system over reflection metadata support. Every dependency object stores its dependency properties inside a reflection TypeMetaData derived class, the **DependencyData**. This class provides functionality to register dependency properties associated with a reflection type.

To create a new derived DependencyObject class we begin defining the public dependency properties it will have:

```cpp
// DelayedButton.h

namespace Tutorials
{
class DelayedButton: public Button
{
public:
    /// Dependency properties
    //@{
    static const DependencyProperty* DelayProperty;
    //@}
};
}
```

Then we must register the property in the dependency system:

```cpp
// DelayedButton.cpp

NS_IMPLEMENT_REFLECTION(Tutorials::DelayedButton, "Tutorials.DelayedButton")
{
    DependencyData* data = NsMeta<DependencyData>(TypeOf<SelfClass>());
    data->RegisterProperty<float>(DelayProperty, "Delay", PropertyMetadata::Create(1.0f));
}
```

The previous code does three things:

- Defines the type name used to register the class in the ComponentFactory, so XAML parser is able to create instances of DelayedButton when parsing a XAML file.
- **NsMeta** creates a metadata associated with the reflection of DelayedButton class, that would be used by dependency system to look for dependency properties registered by this class.
- **RegisterProperty** creates a property in the dependency system named "Delay", with a default value of 1.0f, and it is associated to DelayedButton class.
- RegisterProperty also assigns the created property to the DelayProperty public member.

After this we can use that class from a xaml like this:

```xml
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:local="clr-namespace:Tutorials">
  <local:DelayedButton Delay="1.5"/>
</Grid>
```

Or in code:

```cpp
Ptr<Tutorials::DelayedButton> btn = Noesis::MakePtr<Tutorials::DelayedButton>();
btn->SetValue<float>(Tutorials::DelayedButton::DelayProperty, 1.5f);
```

The function **SetValue** is a templated method of DependencyObject that sets the local value of the specified dependency property in the object. To make it easier to modify and access dependency property values, we usually wrap them with getter/setter methods in the owner class (we omit the above code to make it more clear):

```cpp
// DelayedButton.h

namespace Tutorials
{
class DelayedButton: public Button
{
public:
    /// Gets or sets button click delay in seconds
    //@{
    float GetDelay() const;
    void SetDelay(float delay);
    //@}
};
}

// DelayedButton.cpp

namespace Tutorials
{
float DelayedButton::GetDelay() const
{
    return GetValue<float>(DelayProperty);
}

void DelayedButton::SetDelay(float delay)
{
    SetValue<float>(DelayProperty, delay);
}
}

// in use...
Ptr<Tutorials::DelayedButton> btn = Noesis::MakePtr<Tutorials::DelayedButton>();
btn->SetDelay(1.5f);
```

As we see in the example, dependency properties can have extra information associated with a reflection type. This metadata is stored in a [PropertyMetadata](https://www.noesisengine.com/docs/Gui.DependencySystem._PropertyMetadata.html) object.

## PropertyMetadata

When registering a dependency property, we use a PropertyMetadata object to set some values associated with the property.

### Default Value

First we can defined its **default value**. This value could probably be stored inside the property, but the default value (and other info that will be explained later) is stored in a metadata because a dependency property can have different metadatas associated with different types. This gives us the potential to override the default value of a property in derived classes. For example:

```cpp
// DerivedDelayedButton.cpp

NS_IMPLEMENT_REFLECTION(Tutorials::DerivedDelayedButton, "Tutorials::DerivedDelayedButton")
{
    DependencyData* data = NsMeta<DependencyData>(TypeOf<SelfClass>());
    data->OverrideMetadata<float>(DelayedButton::DelayProperty, "Delay",
        PropertyMetadata::Create(5.0f));
}
```

Instances of the derived class will have a different default value:

```cpp
Ptr<Tutorials::DelayedButton> btn1 = Noesis::MakePtr<Tutorials::DelayedButton>();
float delayBtn1 = btn1->GetDelay(); // -> returns 1.0f

Ptr<Tutorials::DerivedDelayedButton> btn2 = Noesis::MakePtr<Tutorials::DerivedDelayedButton>();
float delayBtn2 = btn2->GetDelay(); // -> returns 5.0f
```

In addition, other metadata values that have not been modified (overridden) are merged with the metadata associated with the ancestor classes. This other metadata values are: the property changed callback and the coerce value callback. But PropertyMetadata derived classes can expand property info with more values.

### Property Changed Callback

The **property changed callback** is a static function that is called every time the real value of the property changes in a DependencyObject. The signature of the function must be the following:

```cpp
void PropertyChangedCallback(DependencyObject* d, const DependencyPropertyChangedEventArgs& e);
```

The function receives the object where the property is changed, and a struct with change info:

- *e.prop:* The property that has changed
- *e.oldValue:* The value in the dependency object before the change. You can use templated method `e.OldValue<T>()` to simplify access to the old value.
- *e.newValue:* The new value set in the dependency object. You can use templated method `e.NewValue<T>()` to simplify access to the new value.

Using this info a class can manage changes of its dependency properties and update other values or launch events.

```cpp
// DelayedButton.cpp

static void OnDelayChanged(DependencyObject* d, const DependencyPropertyChangedEventArgs& e)
{
    DelayedButton* btn = (DelayedButton*)d;
    float delay = e.NewValue<float>();
    btn->ResetDelayTimer(delay);
}

NS_IMPLEMENT_REFLECTION(Tutorials::DelayedButton, "Tutorials.DelayedButton")
{
    DependencyData* data = NsMeta<DependencyData>(TypeOf<SelfClass>());
    data->RegisterProperty<float>(DelayProperty, "Delay",
        PropertyMetadata::Create(1.0f, OnDelayChanged));
}
```

### Coerce Value Callback

The **coerce value callback** is a static function that is called whenever a dependency property value is being re-evaluated, or coercion is specifically requested through *CoerceValue* method. The signature of the function must be the following:

```cpp
bool CoerceValueCallback(const DependencyObject* d, const void* baseValue, void* coercedValue);
```

Coercion interacts with the base value of a dependency property to ensure that some constraints are applied as those constraints exist at the time, but the base value is still retained. The most common use of the coerce callback is to ensure that a value is between minimum and maximum values. Continuing with the previous example, we can define two more properties, *MinimumDelay* and *MaximumDelay*, in our DelayedButton class, and associate a CoerceValueCallback to the Delay property:

```cpp
// DelayedButton.cpp

static bool CoerceDelay(const DependencyObject* d, const void* baseValue, void* coercedValue)
{
    const DelayedButton* btn = (const DelayedButton*)d;
    float newValue = *(const float*)baseValue;
    float& coerced = *(float*)coercedValue;

    coerced = std::max(btn->GetMinimumDelay(), std::min(newValue, btn->GetMaximumDelay()));

    return true;
}

NS_IMPLEMENT_REFLECTION(Tutorials::DelayedButton, "Tutorials.DelayedButton")
{
    DependencyData* data = NsMeta<DependencyData>(TypeOf<SelfClass>());
    data->RegisterProperty<float>(DelayProperty, "Delay",
        PropertyMetadata::Create(1.0f, CoerceDelay));
    data->RegisterProperty<float>(MinimumDelayProperty, "MinimumDelay",
        PropertyMetadata::Create(0.0f));
    data->RegisterProperty<float>(MaximumDelayProperty, "MaximumDelay",
        PropertyMetadata::Create(10.0f));
}
```

But we also need to ensure that maximum value is greater than minimum value, so we apply coerce functions to that property too:

```cpp
// DelayedButton.cpp

static bool CoerceMax(const DependencyObject* d, const void* baseValue, void* coercedValue)
{
    const DelayedButton* btn = (const DelayedButton*)d;
    float newValue = *(const float*)baseValue;
    float& coerced = *(float*)coercedValue;

    coerced = std::max(btn->GetMinimumDelay(), newValue);

    return true;
}

NS_IMPLEMENT_REFLECTION(Tutorials::DelayedButton, "Tutorials.DelayedButton")
{
    DependencyData* data = NsMeta<DependencyData>(TypeOf<SelfClass>());
    data->RegisterProperty<float>(DelayProperty, "Delay",
        PropertyMetadata::Create(1.0f, CoerceDelay));
    data->RegisterProperty<float>(MinimumDelayProperty, "MinimumDelay",
        PropertyMetadata::Create(0.0f));
    data->RegisterProperty<float>(MaximumDelayProperty, "MaximumDelay",
        PropertyMetadata::Create(10.0f, CoerceMax));
}
```

And finally we must check if minimum and maximum values change to update current delay value:

```cpp
// DelayedButton.cpp

static void OnMinChanged(DependencyObject* d, const DependencyPropertyChangedEventArgs& e)
{
    DelayedButton* btn = (DelayedButton*)d;
    btn->CoerceValue<float>(DelayedButton::MaximumDelayProperty);
    btn->CoerceValue<float>(DelayedButton::DelayProperty);
}

void DelayedButton::OnMaxChanged(DependencyObject* d, const DependencyPropertyChangedEventArgs& e)
{
    DelayedButton* btn = (DelayedButton*)d;
    btn->CoerceValue<float>(DelayedButton::DelayProperty);
}

NS_IMPLEMENT_REFLECTION(Tutorials::DelayedButton, "Tutorials.DelayedButton")
{
    DependencyData* data = NsMeta<DependencyData>(TypeOf<SelfClass>());
    data->RegisterProperty<float>(DelayProperty, "Delay",
        PropertyMetadata::Create(1.0f, CoerceDelay));
    data->RegisterProperty<float>(MinimumDelayProperty, "MinimumDelay",
        PropertyMetadata::Create(0.0f, OnMinChanged));
    data->RegisterProperty<float>(MaximumDelayProperty, "MaximumDelay",
        PropertyMetadata::Create(10.0f, OnMaxChanged, CoerceMax));
}
```