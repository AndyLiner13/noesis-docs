Source: https://www.noesisengine.com/docs/Gui.Core._ResourceDictionary.html

# ResourceDictionary Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.resourcedictionary.aspx)

Provides a hash table implementation that contains resources used by the UI.

ResourceDictionaries are implicitly created when using the *Resources* property of tree elements. But a resource dictionary can also be declared as a single XAML file for later runtime load or for merging it into the [Application](/App.ApplicationLauncher/_Application.md) or a [FrameworkElement](/Gui.Core/_FrameworkElement.md).

```
<ResourceDictionary
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <SolidColorBrush x:Key="NormalBrush" Color="Silver"/>
  <Style TargetType="Button">
    <Setter Property="FontSize" Value="20"/>
    <Setter Property="Background" Value="Crimson"/>
  </Style>
</ResourceDictionary>
```

# Inheritance Hierarchy

• [BaseDictionary](/Gui.Core/_BaseDictionary.md)

• *ResourceDictionary*

# Properties

| Name | Description |
| --- | --- |
| ○ *MergedDictionaries* | Gets the collection of merged dictionaries |
| ○ *Source* | Get or set the source file for this dictionary |

● Dependency Property   ○ Reflection Property

# Attached Properties

ResourceDictionary has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *Add(key, value)* | Adds an element with the provided key and value to the dictionary |
|  *Clear()* | Removes all elements from the dictionary |
|  *Contains(key)* | Determines whether the dictionary contains an element with the specified key |
|  *Count()* | Returns the number of entries of the base dictionary (excluding merged dictionaries) |
|  *Find(key, resource)* | Looks for an element in the dictionary. Returns true if element was found, false otherwise |
|  *Get(key)* | Gets the value stored for the specified key |
|  *HasResourcesDefined()* | Indicates if this dictionary or any of the merged dictionaries contains a resource |
|  *IsReadOnly()* | Indicates if this dictionary is read-only |
|  *Remove(key)* | Removes the element with the specified key from the dictionary |
|  *Set(key, value)* | Sets the element with the specified key |

## From [BaseDictionary](/Gui.Core/_BaseDictionary.md)

| Name | Description |
| --- | --- |
|  *RemoveDictionaryChangedListeners()* | Removes listeners subscribed to DictionaryChanged event |

# Events

ResourceDictionary has no events