# DependencyProperty Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace)

Represents a dependency property that is registered in the property system. Dependency properties provide support for value expressions, property invalidation and dependent-value coercion, default values, inheritance, data binding, animation, property change notification, and styling.

# Inheritance Hierarchy

 • DependencyProperty

# Properties

| Property | Description |
|----------|-------------|
| Name | Gets property name |
| OwnerType | Gets property owner type |
| Type | Gets property type |
| ValueManager | Gets the object that manages value storage for this property |

# Attached Properties

DependencyProperty has no attached properties

# Methods

| Method | Description |
|--------|-------------|
| CheckType(valueType) | Indicates if the value type is valid for this property |
| CheckType(value) | Indicates if the boxed value is valid for this property type |
| ClearAnimation(obj) | Clears animation value for this property |
| FindTypeMetaData() | Finds a metaData in the corresponding reflection property Returns metaData of the specified type if found, otherwise it returns null |
| FindTypeProperty() | Looks for a reflection property in the owner type of this dependency property with the same name. If not found, null is returned |
| GetBaseValueObject(obj) | Gets the boxed baseValue of this property in the given dependency object |
| GetDefaultValue(forType) | Gets property default value for the specified type |
| GetDefaultValueObject(forType) | Gets property default value as a boxed object for the specified type |
| GetMetadata(forType) | Gets property metaData |
| GetSize() | Returns size of the property type |
| GetUnsetValue() | Returns a static value that is used by the property system rather than a null Ptr to indicate that the property exists, but does not have its value set by the property system. |
| GetValidateValueCallback() | Gets the callback used to validate property value |
| GetValue(obj) | Gets the raw value of the property from the specified dependency object |
| GetValueObject(value) | Gets the a boxed value or Ptr object for this property from a raw pointer |
| GetValueObject(obj) | Gets the boxed value of this property in the given dependency object |
| IsReadOnly() | Checks if property is read-only |
| IsSameValue(obj, value) | Compares the value of this property in the specified dependency object with the supplied value and returns true if they are the same |
| IsSameValue(left, right) | Compares 2 values and returns true when they are the same value |
| IsSameValue(left, right) | Compares 2 values and returns true when they are the same value |
| IsValidValue(value) | Indicates if the specified value is valid for this property. The value is verifyed against property type and property validate callback |
| OverrideMetadata(forType, metadata) | Uses dependency property type information to override its metadata |
| SetValue(obj, value, priority, expression, metadata, destination) | Sets a new value for this property with in the specified destination |
| SetValueObject(obj, value, priority, expression, metadata, destination) | Sets a new value (boxed) for this property with in the specified destination |

# Events

DependencyProperty has no events