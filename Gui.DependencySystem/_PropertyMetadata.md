Source: https://www.noesisengine.com/docs/Gui.DependencySystem._PropertyMetadata.html

# PropertyMetadata Class

## namespace [Noesis](../Gui.Core/_ClassHierarchy.md#noesis-namespace)

Defines certain behavior aspects of a dependency property as it is applied to a specific type, including conditions it was registered with.

# Inheritance Hierarchy

• *PropertyMetadata*

• [UIPropertyMetadata](../Gui.Core/_UIPropertyMetadata.md)

# Properties

| Name | Description |
| --- | --- |
| ○ *CoerceValueCallback* | Gets or sets a CoerceValueCallback implementation specified in this metadata |
| ○ *PropertyChangedCallback* | Gets or sets a PropertyChangedCallback implementation specified in this metadata |
| ○ *Uncached* | Determines if the values of the property using this metadata should not be cached prop |

● Dependency Property   ○ Reflection Property

# Attached Properties

PropertyMetadata has no attached properties

# Methods

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

PropertyMetadata has no events