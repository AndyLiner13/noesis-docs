# FrameworkPropertyMetadata Class

## namespace Noesis

Reports or applies metadata for a dependency property, specifically adding framework-specific property system characteristics.

# Inheritance Hierarchy

 • PropertyMetadata • UIPropertyMetadata • FrameworkPropertyMetadata

# Properties

## From PropertyMetadata

| Property | Description |
|----------|-------------|
| CoerceValueCallback | Gets or sets a CoerceValueCallback implementation specified in this metadata |
| PropertyChangedCallback | Gets or sets a PropertyChangedCallback implementation specified in this metadata |
| Uncached | Determines if the values of the property using this metadata should not be cached prop |

# Attached Properties

FrameworkPropertyMetadata has no attached properties

# Methods

## From PropertyMetadata

| Method | Description |
|--------|-------------|
| ClearInheritedValues() | Remove inherited values from ancestors |
| GetDefaultValueObject() | Gets default value as a boxed object |
| GetDefaultValueStorage() | Gets or sets the default value of the dependency property |
| GetValueManager() | Gets DefaultValue memory manager |
| HasCoerceValueCallback() | Indicates if this metadata has a CoerceValueCallback set |
| HasDefaultValue() | Indicates if this metadata has a DefaultValue set |
| HasPropertyChangedCallback() | Indicates if this metadata has a PropertyChangedCallback set |
| IsUncached() | Indicates if this metadata has a the Uncached flag set |
| Merge(ancestor) | Inherit ancestor values if they are not local in this class |

## Own Methods

| Method | Description |
|--------|-------------|
| AffectsArrange() | Indicates if the property affects arrange layout pass |
| AffectsMeasure() | Indicates if the property affects measure layout pass |
| AffectsParentArrange() | Indicates if the property affects parent arrange layout pass |
| AffectsParentMeasure() | Indicates if the property affects parent measure layout pass |
| AffectsRender() | Indicates if the property affects render pass |
| BindsTwoWayByDefault() | Indicates whether the property binds two-way by default |
| ClearInheritedValues() | Remove inherited values from ancestors |
| Create() | Helper functions to create a new PropertyMetadata |
| DefaultUpdateSourceTrigger() | Gets or sets the default for UpdateSourceTrigger to use when bindings for the property with this metadata are applied, which have their UpdateSourceTrigger set to Default. |
| Inherits() | Indicates if the property inherits its value from logical tree ancestors |
| IsNotDataBindable() | Indicates whether the dependency property supports data binding |
| Journal() | Indicates if the value of this property should be saved/restored when journaling by Uri |
| Merge(ancestor) | Inherit ancestor values if they are not local in this class |
| OverridesInheritanceBehavior() | Indicates whether the property value inheritance evaluation should span across certain content boundaries in the logical tree of elements |
| SubPropertiesDoNotAffectRender() | Indicates whether sub-properties of the dependency property do not affect the rendering of the containing object |

# Events

FrameworkPropertyMetadata has no events