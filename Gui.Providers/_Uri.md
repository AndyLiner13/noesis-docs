Source: https://www.noesisengine.com/docs/Gui.Providers._Uri.html

# Uri Class

## namespace [Noesis](../Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](https://docs.microsoft.com/en-us/dotnet/api/system.uri)

Provides a representation of a uniform resource identifier and easy access to parts of the URI.

In NoesisGUI, uniform resource identifiers (URIs) are used to identify and load resources like *Images*, *Fonts* and *Dictionaries*. Two kind of URIs are supported: absolute and relative.

Absolute URIs define a scheme preceding the path part. Paths beginning with a drive letter are also considered absolute (automatically normalized to a file scheme URI).

```
<Image Source="pack://application:,,,/Images/icon.png" />
<Image Source="file:///Images/icon.png" />
<Image Source="C:/Images/icon.png" />
<Image Source="http://www.noesisengine.com" />
```

A relative URI includes only the path.

```
<Image Source="Images/icon.png" />
```

Both absolute and relative URIs can have an optional assembly definition in the form of *'/Assembly;component/'* preceding the path.

```
<Image Source="pack://application:,,,/MyProject;component/Images/icon.png" />
<Image Source="/MyProject;component/Images/icon.png" />
```

By default, a relative URI is considered relative to the location of the XAML that contains the reference. If a leading slash is provided, however, the relative URI reference is then considered relative to the root of the application. For example, given the following project structure:

```
App.xaml
Page2.xaml
Folder/
+ Page1.xaml
+ Page2.xaml
```

If Page1.xaml contains a reference to *'Page2.xaml'*, it will point to *'Folder/Page2.xaml'* as the reference is considered relative to the XAML. If it refers to *'/Page2.xaml'* or *'/MyProject;component/Page2.xaml'*, it will point to the root *'Page2.xaml'* as the reference is considered relative to the root of the application.

# Inheritance Hierarchy

• *Uri*

# Properties

Uri has no properties

# Attached Properties

Uri has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *File(path)* | [Uri](_Uri.md) creation from file scheme ('<file:///path>') |
|  *FullPath()* | Gets path part of the [Uri](_Uri.md) including the assembly |
|  *GetAssembly(assembly)* | Gets assembly part of the [Uri](_Uri.md) |
|  *GetPath(path)* | Gets path part of the [Uri](_Uri.md) with the assembly removed |
|  *GetScheme(scheme)* | Gets scheme part of the [Uri](_Uri.md) |
|  *IsAbsolute()* | Indicates if this [Uri](_Uri.md) is absolute |
|  *IsValid()* | Indicates if this [Uri](_Uri.md) is valid |
|  *Pack(assembly, path)* | [Uri](_Uri.md) creation from pack scheme ('pack://application:,,,/assembly;component/path') |
|  *Str()* | Gets the original string that was passed to this [Uri](_Uri.md) constructor normalized |
|  *ToString()* | Generates a string representation of the [Uri](_Uri.md) |

# Events

Uri has no events