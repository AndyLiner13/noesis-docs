Source: https://www.noesisengine.com/docs/Gui.Core._Typography.html

# Typography Class

## namespace [Noesis](/Gui.Core/_ClassHierarchy.md#noesis-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.documents.typography.aspx)

Provides access to a rich set of OpenType typography properties.

The [Typography](/Gui.Core/_Typography.md) object exposes the set of features that an OpenType font supports. All properties have an attached property usage in XAML so they can be used in all text element types.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <TextBlock FontFamily="Fonts/#Arial" Typography.CapitalSpacing="True">
    <Run>CAPITALS</Run>
    <Run Typography.Capitals="SmallCaps">Capitals</Run>
    <Run Typography.Capitals="AllSmallCaps">Capitals</Run>
  </TextBlock>
</Grid>
```

# Inheritance Hierarchy

• *Typography*

# Properties

| Name | Description |
| --- | --- |
| ● *AnnotationAlternates* | Gets or sets a value that specifies the index of an alternate annotation form.The default value is 0 |
| ● *CapitalSpacing* | Gets or sets a value that determines whether inter-glyph spacing for all-capital text is globally adjusted to improve readability.The default value is false |
| ● *Capitals* | Gets or sets a FontCapitals enumerated value that indicates the capital form of the selected font. The default value is Normal |
| ● *CaseSensitiveForms* | Gets or sets a value that determines whether glyphs adjust their vertical position to better align with uppercase glyphs. The default value is false |
| ● *ContextualAlternates* | Gets or sets a value that determines whether custom glyph forms can be used based upon the context of the text being rendered. The default value is true |
| ● *ContextualLigatures* | Gets or sets a value that determines whether contextual ligatures are enabled. The default value is true |
| ● *ContextualSwashes* | Gets or sets a value that specifies the index of a contextual swashes form. The default value is 0 |
| ● *DiscretionaryLigatures* | Gets or sets a value that determines whether discretionary ligatures are enabled. The default value is false |
| ● *EastAsianExpertForms* | Gets or sets a value that determines whether the standard Japanese font forms have been replaced with the corresponding preferred typographic forms. The default value is false |
| ● *EastAsianLanguage* | Gets or sets a FontEastAsianLanguage enumerated value that indicates the version of glyphs to be used for a specific writing system or language. The default value is Normal |
| ● *EastAsianWidths* | Gets or sets a FontEastAsianWidths enumerated value that indicates the proportional width to be used for Latin characters in an East Asian font. The default value is Normal |
| ● *Fraction* | Gets or sets a FontFraction enumerated value that indicates the fraction style. The default value is Normal |
| ● *HistoricalForms* | Gets or sets a value that determines whether historical forms are enabled. The default value is false |
| ● *HistoricalLigatures* | Gets or sets a value that indicates whether historical ligatures are enabled. The default value is false |
| ● *Kerning* | Gets or sets a value that indicates whether kerning is enabled. The default value is true |
| ● *MathematicalGreek* | Gets or sets a value that indicates whether standard typographic font forms of Greek glyphs have been replaced with corresponding font forms commonly used in mathematical notation. The default value is false |
| ● *NumeralAlignment* | Gets or sets a FontNumeralAlignment enumerated value that indicates the alignment of widths when using numerals. The default value is Normal |
| ● *NumeralStyle* | Gets or sets a FontNumeralStyle enumerated value that determines the set of glyphs that are used to render numeric alternate font forms. The default value is Normal |
| ● *SlashedZero* | Gets or sets a value that indicates whether a nominal zero font form should be replaced with a slashed zero. The default value is false |
| ● *StandardLigatures* | Gets or sets a value that indicates whether standard ligatures are enabled. The default value is true |
| ● *StandardSwashes* | Gets or sets a value that specifies the index of a standard swashes form. The default value is 0 |
| ● *StylisticAlternates* | Gets or sets a value that specifies the index of a stylistic alternates form. The default value is 0 |
| ● *StylisticSet1* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet10* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet11* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet12* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet13* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet14* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet15* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet16* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet17* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet18* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet19* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet2* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet20* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet3* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet4* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet5* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet6* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet7* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet8* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *StylisticSet9* | Gets or sets a value that indicates whether a stylistic set of a font form is enabled. The default value is false |
| ● *Variants* | Gets or sets a FontVariants enumerated value that indicates a variation of the standard typographic form to be used. The default value is Normal |

● Dependency Property   ○ Reflection Property

# Attached Properties

Typography has no attached properties

# Methods

Typography has no methods

# Events

Typography has no events