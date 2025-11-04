# FormattedText Class

## namespace Noesis | MSDN

Provides low-level control for drawing text.

# Inheritance Hierarchy

 • FormattedText

# Properties

FormattedText has no properties

# Attached Properties

FormattedText has no attached properties

# Methods

| Method | Description |
|--------|-------------|
| BuildTextRuns(text, inlines, fontFamily, fontWeight, fontStretch, fontStyle, fontSize, strokeThickness, background, foreground, stroke, flowDirection, textDecorations, charSpacing) | Generates and keeps a collection of runs from the supplied InlineCollection and for the specified font properties |
| GetBounds() | Gets text bounds |
| GetGlyphPosition(chIndex, afterChar, x, y) | Gets x/y coordinates at where the specified glyph is positioned. If the glyph is outside layout limits then -10 is returned for both x/y coordinates |
| GetLineInfo(index) | Gets information about the specified line |
| GetNumLines() | Gets the number of lines based on the last layout |
| HasVisualBrush() | Indicates if this FormattedText uses any VisualBrush |
| HitTest(x, y, isInside, isTrailing) | Obtains the glyph index under the specified x/y coordinates, indicating if the point is inside the glyph bounds |
| IsEmpty() | Indicates if this FormattedText has no text |
| Layout(alignment, wrapping, trimming, maxWidth, maxHeight, padding, lineHeight, lineStacking, flowDirection, discardNonVisibleGlyphs) | Layouts and prepares text for rendering for the given constraints |
| Measure(alignment, wrapping, trimming, maxWidth, maxHeight, lineHeight, lineStacking, flowDirection) | Obtains the size of the stored runs for the given constraints |

# Events

FormattedText has no events