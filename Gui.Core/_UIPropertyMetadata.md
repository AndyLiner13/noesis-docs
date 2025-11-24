Source: https://www.noesisengine.com/docs/Gui.Core._UIPropertyMetadata.html

# UIPropertyMetadata Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace)

Provides property metadata for non-framework properties that do have rendering/user interface impact at the core level.

# Inheritance Hierarchy

• [PropertyMetadata](/Gui.DependencySystem/_PropertyMetadata.md)

• *UIPropertyMetadata*

• [FrameworkPropertyMetadata](/Gui.Core/_FrameworkPropertyMetadata.md)

# Properties

## From [PropertyMetadata](/Gui.DependencySystem/_PropertyMetadata.md)

| Name | Description |
| --- | --- |
| ○ *CoerceValueCallback* | Gets or sets a CoerceValueCallback implementation specified in this metadata |
| ○ *PropertyChangedCallback* | Gets or sets a PropertyChangedCallback implementation specified in this metadata |
| ○ *Uncached* | Determines if the values of the property using this metadata should not be cached prop |

● Dependency Property   ○ Reflection Property

# Attached Properties

UIPropertyMetadata has no attached properties

# Methods

## From [PropertyMetadata](/Gui.DependencySystem/_PropertyMetadata.md)

| Name | Description |
| --- | --- |
|  *ClearInheritedValues()* | Remove inherited values from ancestors |
|  *GetDefaultValueObject()* | Gets default value as a boxed object |
|  *GetDefaultValueStorage()* | Gets or sets the default value of the dependency property |
|  *GetValueManager()* | Gets *DefaultValue* memory manager |
|  *HasCoerceValueCallback()* | Indicates if this metadata has a CoerceValueCallback set |
|  *HasDefaultValue()* | Indicates if this metadata has a DefaultValue set |
|  *HasPropertyChangedCallback()* | Indicates if this metadata has a PropertyChangedCallback set |
|  *IsUncached()* | Indicates if this metadata has a the Uncached flag set |
|  *Merge(ancestor)* | Inherit ancestor values if they are not local in this class |

# Events

UIPropertyMetadata has no events