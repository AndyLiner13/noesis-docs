Source: https://www.noesisengine.com/docs/Core.TypeConverter.TypeConverter.html

# Type Converters

Type Converters are classes that implement the *ITypeConverter* interface to allow converting between different types. The conversions can be made in two ways:

- From: converts from the specified type into the type of the converter
- To: converts a converter's type value into the specified type

For the conversions, there are methods that test if the conversion between types is possible (*CanConvertFrom* and *CanConvertTo*) and methods that do the conversion (*ConvertFrom*, *ConvertFromString*, *ConvertTo* and *ConvertToString*). The most common use for a Type Converter is using the *ConvertFromString* method when parsing text files.

Examples:

```
Ptr<ITypeConverter> converter = NsCreateComponent<BooleanConverter>();
if (converter->CanConvertFrom(TypeOf<NsString>()))
{
    NsBool value = Boxing::Unbox<NsBool>(converter->ConvertFromString(NST("true")));
    NS_ASSERT(value);
}

if (converter->CanConvertTo(TypeOf<NsString>()))
{
    NsString str = converter->ConvertToString(Boxing::Box<NsBool>(true));
    NS_ASSERT(str == "True");
}
```

# Basic Converters

There are some predefined converters for the basic types in the TypeConverter package:

- BooleanConverter: for boolean type
- IntegerConverter<T>: where T is any of the integer types (NsInt, NsUInt, NsInt64, etc...)
- FloatConverter<T>: where T can be NsFloat32 or NsFloat64
- CharConverter: for NsChar type
- StringConverter: for NsString type
- SymbolConverter: for NsSymbol type
- EnumConverter<T>: where T is an enum type

The following table shows the available conversions using the basic converters

| ConvertFrom | | | | | | | --- | --- | --- | --- | --- | --- | --- | --- |
| Converter | Bool | Integer | Float | Char | String | Symbol | Enum |
| BooleanConverter | No | No | No | No | Yes | No | No |
| IntegerConverter | Yes | No | No | No | Yes | No | No |
| FloatConverter | Yes | No | No | No | Yes | No | No |
| CharConverter | No | No | No | No | Yes | No | No |
| StringConverter | No | No | No | No | Yes | No | No |
| SymbolConverter | No | No | No | No | Yes | No | No |
| EnumConverter | No | No | No | No | Yes | No | No |

| ConvertTo | | | | | | | --- | --- | --- | --- | --- | --- | --- | --- |
| Converter | Bool | Integer | Float | Char | String | Symbol | Enum |
| BooleanConverter | No | No | No | No | Yes | No | No |
| IntegerConverter | Yes | Yes (any) | Yes (any) | No | Yes | No | No |
| FloatConverter | Yes | Yes (any) | Yes (any) | No | Yes | No | No |
| CharConverter | No | No | No | No | Yes | No | No |
| StringConverter | No | No | No | No | Yes | No | No |
| SymbolConverter | No | No | No | No | Yes | No | No |
| EnumConverter | No | No | No | No | Yes | No | No |

# Other Converters

Converters for other types can be created implementing the ITypeConverter interface, or deriving from one the helper base classes:

- BaseConverterOneWay: Base class for converters that only implement the conversion From and To string
- BaseConverterBothWays: Base class for converters that only implement the conversion From string
- Converter: Helper class to create converters for classes that implement the method *Parse* and only supports the conversion From and To string