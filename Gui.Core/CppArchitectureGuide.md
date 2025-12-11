Source: https://www.noesisengine.com/docs/Gui.Core.CppArchitectureGuide.html

# C++ Architecture Guide

Although NoesisGUI is based on *WPF*, a C# framework, many of the core concepts exposed in that API do not directly translate to C++. For example, reflection, a key concept for data binding, is not available in C++. There is also no notion of garbage collection in C++. With the purpose of creating a C++ API easier to use, NoesisGUI exposes a few helpers that contribute to make the transition from C# painless and more efficient. Please read carefully the following sections if you are going to use Noesis in C++ language.

# Headers and Namespaces

NoesisGUI headers are grouped by modules (prefixed by *Ns*). The whole API is exposed in the *namespace Noesis*.

```
#include <NsCore/Stream.h>
#include <NsCore/File.h>
#include <NsCore/Log.h>
#include <NsCore/Hash.h>
#include <NsCore/SpinMutex.h>
#include <NsRender/Texture.h>
#include <NsRender/RenderTarget.h>
#include <NsGui/TextureProvider.h>

using namespace Noesis;
```

In case you don't want to manually pick each header we also provide a single header, *'NoesisPCH.h'*, exposing all NoesisGUI API. This is specially useful when using precompiled headers.

```
#include <NoesisPCH.h>

using namespace Noesis;
```

NOTE

Noesis [Application Framework](ApplicationTutorial.md), a helper library not part of core is exposed in a different namespace, *NoesisApp*, and its headers are not included in *NoesisPCH.h*.

# Reference Counting

In Noesis each object contains a reference counter that control its lifetime. The reference counter is initialized to 1 when the instance is created using the *new operator*. This counter is increased or decreased each time *AddReference()* or *Release()* is invoked. If an object's reference count reaches zero it is automatically destroyed using the *operator delete*.

```
// Create a new instance. Reference counter is '1' at this point
Brush* color = new SolidColorBrush(Color::Red);

//...

// Release instance and delete it if reference counter reaches zero
color->Release();
```

You should never destroy Noesis instances using the *operator delete* because there could be more objects holding references and you would be ignoring them. You should use *Release()* instead. There are a few asserts in the implementation of *BaseRefCounted* detecting this kind of scenarios.

References to components can be manually handled using *AddReference()* and *Release()*. For example:

```
Brush* color0 = new SolidColorBrush(Color::Red);     // Ref '1' - Created

Brush* color1 = color0;
color0->AddReference();                              // Ref '1' -> '2'

//...

color0->Release();                                   // Ref '2' -> '1'
color1->Release();                                   // Ref '1' -> '0' - Destroyed
```

To avoid manually handling the reference counter, Noesis provides *Ptr<>*, a smart pointer that automatically handles lifetime of objects by doing *AddReference()* and *Release()*. *Ptr<>* overloads certain operators in order to behave similar to a pointer but ensuring that
objects are deleted when they are no longer needed, to avoid memory leaks.

```
Ptr<Brush> color0 = *new SolidColorBrush(Color::Red);
Ptr<Brush> color1(color0);

//...

// color0 and color1 are automatically destroyed when they go out of scope
```

*BaseRefCounted* objects start with reference counter set to 1. When they are stored inside a *Ptr<>* the counter is increased by 1 again. As you can see in the example above, to avoid having to do a manual Release() to cancel that extra reference, *Ptr<>* supports being constructed from a reference. In this case the reference counter is not incremented again. We also provide a better and more convenient alternative using *MakePtr*:

```
Ptr<Brush> color0 = MakePtr<SolidColorBrush>(Color::Red);
Ptr<Brush> color1(color0);

//...

// color0 and color1 are automatically destroyed when they go out of scope
```

*Ptr<>* implicitly converts to raw pointers, so most of the times its usage is totally transparent and you don't need to care about the details.

```
// Read XAMLs from current working directory
GUI::SetXamlProvider(MakePtr<LocalXamlProvider>("."));

// Renderer initialization with an OpenGL device
Ptr<RenderDevice> device = GLFactory::CreateDevice();
_view->GetRenderer()->Init(device);
```

NOTE

For performance purposes, refcounted instances created in the stack are also supported. In this case is very important to make sure that no extra references are pending at destruction time. *BaseRefCounted* will assert if that scenario is detected.

# Boxing

Sometimes basic types or structs need to be converted to *BaseComponent*. This adds the overhead of the polymorphism to the type, the reference counter and the allocation in the heap, but in some scenarios this is needed, for example when implementing value converters.

The mechanism of converting a stack-type instance to a component is called *boxing* and is performed using *Boxing::Box()*:

```
Ptr<BaseComponent> boxed = Boxing::Box(50.0f);
```

The reverse operation is called *unboxing*. A boxed value is unboxed using *Boxing::Unbox()*:

```
float val = Boxing::CanUnbox<float>(boxed) ? Boxing::Unbox<float>(boxed) : 0.0f;
```

Although boxing is optimized internally (for example using pools to avoid memory allocations) it should be avoided whenever possible because it cannot be considered a 'fast' operation. The following snippet implement a thousand converter. Note how the input value is given as a *BaseComponent* instance that needs to be unboxed and how the result is boxed to a *BaseComponent* instance.

```
bool ThousandConverter::TryConvert(BaseComponent* value, const Type*, BaseComponent*, Ptr<BaseComponent>& result)
{
    if (Boxing::CanUnbox<int>(value))
    {
        char str[16];
        int v = Boxing::Unbox<int>(value);
        snprintf(str, sizeof(str), "%.2f K", (float)v / 1000.0f);
        result = Boxing::Box(str);
        return true;
    }

    return false;
}
```

# Nullables

*Nullable* types are instances of the *Noesis::Nullable<T>* struct. A nullable type can represent the correct range of values for its underlying types, plus an additional *null* value. For example, a *Nullable<bool>* can be assigned the values '*true*', '*false*' or '*null*'. Use the *HasValue* and *GetValue* functions to test for null and retrieve the value, as shown in the following example:

```
Nullable<bool> a(nullptr);
assert(!a.HasValue());
assert(a == nullptr);

Nullable<bool> b(false);
assert(b.HasValue());
assert(b == false);
assert(b.GetValue() == false);
```

NOTE

You can assign a value and compare against a value with nullables just as you would for and ordinary value type.

Objects based on nullable types are only boxed if the object is non-null. If *HasValue* is *false*, the object reference is assigned to *null* instead of boxing:

```
Ptr<BaseComponent> obj = Boxing::Box(Nullable<float>(nullptr));
assert(obj == nullptr);
```

# Delegates

*Delegate* is a generic implementation for *callbacks*. Delegates in Noesis are implemented very similarly to *.NET* delegates. Delegates ensure that the callback method is type-safe. They also support invoking multiple methods sequentially and allow binding both static and instance methods.

## Declaring Delegates

A delegate is declared using a function signature. For example:

```
/// A delegate with void return and two parameters: int and float
Delegate<void (int, float)> d;
```

## Non-member Methods

The following code adds a static method to the delegate and invokes it:

```
void Print(int size, float value)
{
    printf("%d %4.3f", size, value);
}

void main()
{
    // Create and Bind the delegate
    Delegate<void (int, float)> d = &Print;

    // Invoke
    d(500, 10.0f);
}
```

## Member Methods

Instance methods can also be bound to delegates:

```
struct Printer
{
    void Print(const char* string) const
    {
        printf("%s", string);
    }
};

void main()
{
    // Create the instance
    Printer printer;

    // Create and Bind the delegate
    Delegate<void (const char*)> d = MakeDelegate(&printer, &Printer::Print);

    // Invoke
    d("hi :)");
}
```

## Lambdas

C++11 lambda expressions can also be used with delegates:

```
void main()
{
    Delegate<uint32_t(uint32_t, uint32_t)> d = [](uint32_t x, uint32_t y) { return x + y; };
    assert(d(123, 456) == 579);
}
```

NOTE

Delegates created from lambdas by value (the most common case) **cannot be compared**. This is
because each lambda has a unique, anonymous type. As a result, such delegates cannot be removed
from multicast delegates using '*-=*'. If you need to add and later remove a lambda from a multicast delegate, see the section below on
'Lambda References'.

## Lambda References

By default, lambdas cannot be compared because each lambda expression has a unique, anonymous type. As a result, delegates created from standard lambdas cannot be removed from a multicast delegate.

To address this limitation, Noesis supports *lambda references*, where the delegate stores a pointer to the lambda:

```
auto lambda = [](const char* msg) { printf("Message: %s\n", msg); };

// This version supports += and -= because the lambda is passed by pointer
Delegate<void (const char*)> d = &lambda;

// Can now be added to and removed from a multicast delegate
d += &lambda;
d -= &lambda;
```

This allows lambda-based callbacks to participate in add/remove operations, such as with multicast delegates.

WARNING

When using lambda references, the client code is responsible for keeping the lambda object alive
for the duration of its use in the delegate. The delegate only stores a raw pointer and does not
manage the lifetime of the lambda.

## MultiDelegates

A delegate can be bound to several callbacks using the overloaded operators '*+=*' and '*-=*':

```
struct Printer
{
    void Print(const char* string) const
    {
        printf("Printer: %s", string);
    }
};

struct Screen
{
    void Print(const char* string) const
    {
        printf("Screen: %s", string);
    }
};

void main()
{
    // Create the instances
    Printer printer;
    Screen screen;

    // Create and Bind the delegate
    Delegate<void (const char*)> delegate;

    delegate += MakeDelegate(&printer, &Printer::Print);
    delegate += MakeDelegate(&screen, &Screen::Print);

    // Invoke. This line will call all the callbacks
    delegate("hi :)");
}
```

When using *MultiDelegates*, the return value from the delegate invocation is the one returned by the last callback executed.

NOTE

In contrast with C#, delegates do not increment the reference count of the target instance. This is done to avoid circular references that can occur when a delegate points back to the object that owns it. As a result, before destroying an instance that is the target of a delegate, it must be removed from the delegate.

# Reflection

Reflection is the ability of a program to inspect in run-time the structure and state of the data with the possibility of modifying it. Languages as Java or C# incorporate such functionality by default. However, in C++ language it is not possible to obtain this kind of information directly.

## Classes

Noesis provides a few macros to easily incorporate reflection information to *classes* and *structs*. This is normally used to expose reflection information from client code to Noesis, for example when using [Data Binding](DataBindingTutorial.md) connecting *Views* and *Models*.

There are two kind of macros, a declaration macro (*NS\_DECLARE\_REFLECTION*) that you normally use in headers:

```
struct Quest: public BaseComponent
{
    bool completed;
    NsString title;
    NsString description;
    Ptr<ImageSource> image;

    NS_DECLARE_REFLECTION(Quest, BaseComponent)
};

class ViewModel final: public NotifyPropertyChangedBase
{
public:
    void SetSelectedQuest(Quest* value);
    Quest* GetSelectedQuest() const;

private:
    Ptr<ObservableCollection<Quest>> _quests;
    Ptr<Quest> _selectedQuest;

    NS_DECLARE_REFLECTION(ViewModel, NotifyPropertyChangedBase)
};
```

And the implementation macro (*NS\_IMPLEMENT\_REFLECTION*), to be used in *.cpp* files:

```
NS_IMPLEMENT_REFLECTION(Quest)
{
    NsProp("Title", &Quest::title);
    NsProp("Image", &Quest::image);
    NsProp("Description", &Quest::description);
    NsProp("Completed", &Quest::completed);
}

NS_IMPLEMENT_REFLECTION(ViewModel)
{
    NsProp("Quests", &ViewModel::_quests);
    NsProp("SelectedQuest", &ViewModel::GetSelectedQuest, &ViewModel::SetSelectedQuest);
}
```

Instead of using two macros, you can use only one, but it is not recommended because it will add extra bloating to your headers slightly increasing build time. If possible avoid it although sometimes is mandatory, for example with templates.

```
template<class T> struct Vector2
{
    T x;
    T y;

    NS_IMPLEMENT_INLINE_REFLECTION(Vector2, NoParent)
    {
        NsProp("x", &Vector2::x);
        NsProp("y", &Vector2::y);
    }
}
```

Note how *NsProp* can be used to directly expose member variables, getters and setters or just getters (for read-only properties). For example:

```
class Game final: public NotifyPropertyChangedBase
{
public:
    void SetSelectedTeam(int selectedTeam)
    {
        if (_selectedTeam != selectedTeam)
        {
            _selectedTeam = selectedTeam;
            OnPropertyChanged("SelectedTeam");
        }
    }

    int GetSelectedTeam() const
    {
        return _selectedTeam;
    }

    Collection<BaseComponent>* GetVisibleTeams() const
    {
        return _visibleTeams;
    }

private:
    int _selectedTeam;
    Ptr<Collection<BaseComponent>> _visibleTeams;

    NS_IMPLEMENT_INLINE_REFLECTION(Game, NotifyPropertyChangedBase)
    {
        NsProp("SelectedTeam", &Game::GetSelectedTeam, &Game::SetSelectedTeam);
        NsProp("VisibleTeams", &Game::GetVisibleTeams);
    }
};
```

## Enumerations

Enumerations require a different set of macros. *NS\_DECLARE\_REFLECTION\_ENUM*, for the header, must be used in the *global* namespace.

```
namespace Scoreboard
{
    enum class Team
    {
        Alliance,
        Horde,
    };

    enum class Class
    {
        Fighter,
        Rogue,
        Hunter,
        Mage,
        Cleric,
    };
}

NS_DECLARE_REFLECTION_ENUM(Scoreboard::Team)
NS_DECLARE_REFLECTION_ENUM(Scoreboard::Class)
```

And *NS\_IMPLEMENT\_REFLECTION\_ENUM* for the implementation file.

```
NS_IMPLEMENT_REFLECTION_ENUM(Scoreboard::Team, "Scoreboard.Team")
{
    NsVal("Alliance", Team::Alliance);
    NsVal("Horde", Team::Horde);
}

NS_IMPLEMENT_REFLECTION_ENUM(Scoreboard::Class, "Scoreboard.Class")
{
    NsVal("Fighter", Scoreboard::Class::Fighter);
    NsVal("Rogue", Scoreboard::Class::Rogue);
    NsVal("Hunter", Scoreboard::Class::Hunter);
    NsVal("Mage", Scoreboard::Class::Mage);
    NsVal("Cleric", Scoreboard::Class::Cleric);
}
```

NOTE

Similar to classes, you can use just a single macro, NS\_IMPLEMENT\_INLINE\_REFLECTION\_ENUM

## Factory

In case you need to instantiate a class from a XAML, for example a converter or user control, it must be registered in the component factory before it can be used in XAML. Our application framework expose a virtual function for that purpose, *RegisterComponents*. Find more information about in the [Extending NoesisGUI](ExtendingTutorial.md) tutorial.

```
class AppLauncher final: public ApplicationLauncher
{
private:
    void RegisterComponents() const override
    {
        RegisterComponent<Scoreboard::MainWindow>();
        RegisterComponent<Scoreboard::App>();
        RegisterComponent<Scoreboard::ThousandConverter>();
        RegisterComponent<EnumConverter<Scoreboard::Team>>();
        RegisterComponent<EnumConverter<Scoreboard::Class>>();
    }
};
```

NOTE

Enums are not directly registered. EnumConverter must be used for that purpose.

Once a class is registered in the factory it can be used in XAML. For example:

```
<UserControl
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="clr-namespace:Scoreboard"
    x:Class="Scoreboard.MainWindow"
    FontFamily="Fonts/#Cheboygan">

  <UserControl.Resources>
    <ResourceDictionary>
        <local:ThousandConverter x:Key="ThousandConverter"/>
    </ResourceDictionary>
  </UserControl.Resources>
</UserControl>
```

## Interfaces

In the rare case you need to implement interfaces, *NsImpl* helper must be used in the corresponding reflection section.

NOTE

NS\_IMPLEMENT\_INTERFACE\_FIXUP must also be used to automatically implement a few internal functions needed by Noesis::Interface

```
class NotifyPropertyChangedBase: public BaseComponent, public INotifyPropertyChanged
{
public:
    /// From INotifyPropertyChanged
    //@{
    PropertyChangedEventHandler& PropertyChanged() override final;
    //@}

    NS_IMPLEMENT_INTERFACE_FIXUP

protected:
    void OnPropertyChanged(const char* name);

private:
    PropertyChangedEventHandler _propertyChanged;

    NS_DECLARE_REFLECTION(NotifyPropertyChangedBase, BaseComponent)
};
```

```
NS_IMPLEMENT_REFLECTION(NotifyPropertyChangedBase)
{
    NsImpl<INotifyPropertyChanged>();
}
```

# RTTI

Having reflection macros in a class also enables safe casts at run-time. This is very similar to the standard *dynamic\_cast* but using *DynamicCast* instead. For example:

```
Freezable* IsFreezableValue(BaseComponent* value)
{
    Freezable* freezable = DynamicCast<Freezable*>(value);
    if (freezable != 0 && !freezable->IsFrozen())
    {
        return freezable;
    }
    else
    {
        return nullptr;
    }
}
```

*DynamicPtrCast* is also available in case a dynamic cast from *Ptr<>* to *Ptr<>* is needed. Note that this is more efficient than manually getting the pointer using *GetPtr()* and doing the cast with *DynamicCast*.

```
Ptr<BaseComponent> value = GetLocalValue();
Ptr<BaseBindingExpression> expr = DynamicPtrCast<BaseBindingExpression>(value);
BaseBindingExpression* expr_ = DynamicCast<BaseBindingExpression*>(value.GetPtr());
```