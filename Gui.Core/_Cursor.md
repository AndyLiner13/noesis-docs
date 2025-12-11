Source: https://www.noesisengine.com/docs/Gui.Core._Cursor.html

# Cursor Class

## namespace [Noesis](_ClassHierarchy.md#noesis-namespace) | [MSDN](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.cursor)

Represents the image used for the mouse pointer.

The [Cursors](_Cursors.md) class contains a set of default cursors. Custom cursors can be created from specified .ani or .cur files.

```
<StackPanel xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">
  <Rectangle Height="100" Fill="Red" Cursor="Hand"/>
  <Rectangle Height="100" Fill="Blue" Cursor="Resources/Cursors/link.cur"/>
</StackPanel>
```

# Inheritance Hierarchy

• *Cursor*

# Properties

| Name | Description |
| --- | --- |
| ○ *Filename* | For custom cursors this returns the filename or empty string for built in cursors |
| ○ *Type* | Returns the cursor type |

● Dependency Property   ○ Reflection Property

# Attached Properties

Cursor has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *ToString()* | Generates a string representation of the cursor. Returns the standard cursor name, or the path for the custom cursor file |

# Events

Cursor has no events