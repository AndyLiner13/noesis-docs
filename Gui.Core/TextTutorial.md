# Text Tutorial

![github](https://www.noesisengine.com/docs/github.png)

[Tutorial Data](https://github.com/Noesis/Tutorials/tree/master/Snippets/Text)

Read-only text in XAML is mainly displayed using [TextBlock](https://www.noesisengine.com/docs/Gui.Core._TextBlock.html) elements. A TextBlock defines the content property Text where the user can specify any string. FontFamily, FontSize, FontStyle, FontWeight, FontStretch, Foreground and Background control how text displays within the element.

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      HorizontalAlignment="Center" VerticalAlignment="Center">

  <TextBlock Text="Hello World!"/>

</Grid>
```

# Inlines

[Inlines](https://www.noesisengine.com/docs/Gui.Core._Inline.html) can also be used to modify the aspect of specific blocks.

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Background="White"
      TextElement.FontFamily="Fonts/#Roboto"
      TextElement.FontSize="30"
      TextElement.Foreground="Black">

  <Grid.Resources>
    <Style TargetType="Hyperlink">
      <Setter Property="Foreground" Value="DodgerBlue"/>
    </Style>
    <Decorator x:Key="Context" Tag="DataContext bound text."/>
  </Grid.Resources>

  <Grid HorizontalAlignment="Center" VerticalAlignment="Center" Margin="0" Background="WhiteSmoke"
        DataContext="{StaticResource Context}">
    <Decorator x:Name="NamedElement" Tag="Named element bound text."/>
    <TextBlock Margin="20">
      <Bold>Lorem</Bold> ipsum <Italic>dolor</Italic> sit <Underline>amet</Underline>.
      <LineBreak/>
      <Bold FontWeight="Normal">
        Lorem <Span FontWeight="Bold">
          ipsum <Italic>
            sit <Underline>amet</Underline>
          </Italic>
        </Span>
      </Bold>.
      <LineBreak/>
      Click the <Hyperlink NavigateUri="www.test.com">hyperlink</Hyperlink> now!
      <LineBreak/>
      This is also a <Hyperlink TextDecorations="None">
        <Bold>hyperlink</Bold>
      </Hyperlink>.
      <LineBreak/>
      <Span>
        <Span FontStyle="Italic">
          <Run Text="{Binding Tag, ElementName=NamedElement}"/>
        </Span>
        <LineBreak/>
        <Span FontWeight="Bold">
          <Run Text="{Binding Tag}"/>
        </Span>
      </Span>
    </TextBlock>
  </Grid>
</Grid>
```

![TextTutorialImg1.jpg](https://www.noesisengine.com/docs/TextTutorialImg1.jpg)

# Font Family

The default font is taken from the active theme. This can be overridden by using the FontFamily property. FontFamily includes an [URI](https://www.noesisengine.com/docs/Gui.Providers._Uri.html) to the directory where the font is located plus the family name separated by a '#' character.

```xml
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
    <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
        <TextBlock Text="Using Different Fonts" HorizontalAlignment="Center"
          FontFamily="Fonts/#K22 Ambelyn Condensed" FontSize="70"/>
        <TextBlock Text="Using Different Fonts" HorizontalAlignment="Center"
          FontFamily="Fonts/#Laffayette Comic Pro" FontSize="28"/>
        <TextBlock Text="Using Different Fonts" HorizontalAlignment="Center"
          FontFamily="Fonts/#Monkirta Pursuit NC" FontSize="30"/>
    </StackPanel>
</Grid>
```

![TextTutorialImg2.jpg](https://www.noesisengine.com/docs/TextTutorialImg2.jpg)

Note that if you don't use the '#' separator or don't provide a directory, the font is searched globally in the system folder.

```xml
<StackPanel xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">
  <TextBlock FontFamily="Arial">This is a system font</TextBlock>
  <TextBlock FontFamily="#Arial">This is also a system font</TextBlock>
</StackPanel>
```

Thanks to property value inheritance, the FontFamily property enables child elements in a tree of elements to obtain the value from parent elements.

```xml
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center"
   TextElement.FontFamily="Fonts/#Laffayette Comic Pro">
    <TextBlock Text="One"/>
    <TextBlock Text="Two"/>
    <TextBlock Text="Three"/>
    <TextBlock Text="Four"/>
  </StackPanel>
</Grid>
```

# Style properties

TextBlock defines three properties that describe the style, weight and stretch of the text:

- FontStyle: Represents the style of a font face as normal, italic, or oblique.
- FontWeight: Represents the density of a typeface, in terms of the lightness or heaviness of the strokes.
- FontStretch: Represents the degree to which a font has been stretched compared to a font's normal aspect ratio.

```xml
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Background="White"
  TextElement.FontFamily="Fonts/#Absolut Reduced"
  TextElement.FontSize="30"
  TextElement.Foreground="Black">

  <Grid HorizontalAlignment="Center" VerticalAlignment="Center" Margin="0" Background="WhiteSmoke">
    <Grid.ColumnDefinitions>
      <ColumnDefinition Width="2*"/>
      <ColumnDefinition Width="3*"/>
    </Grid.ColumnDefinitions>
    <Grid.RowDefinitions>
      <RowDefinition/>
      <RowDefinition/>
    </Grid.RowDefinitions>
    <StackPanel Grid.Row="0" Grid.Column="0" Margin="10,10,0,0">
      <TextBlock Text="Thin" FontWeight="Thin"/>
      <TextBlock Text="Light" FontWeight="Light"/>
      <TextBlock Text="Regular" FontWeight="Normal"/>
      <TextBlock Text="Medium" FontWeight="Medium"/>
      <TextBlock Text="Bold" FontWeight="Bold"/>
      <TextBlock Text="Black" FontWeight="Black"/>
    </StackPanel>
    <StackPanel Grid.Row="0" Grid.Column="1" Margin="30,10,10,0">
      <TextBlock Text="Thin Italic" FontWeight="Thin" FontStyle="Italic"/>
      <TextBlock Text="Light Italic" FontWeight="Light" FontStyle="Italic"/>
      <TextBlock Text="Regular Italic" FontWeight="Normal" FontStyle="Italic"/>
      <TextBlock Text="Medium Italic" FontWeight="Medium" FontStyle="Italic"/>
      <TextBlock Text="Bold Italic" FontWeight="Bold" FontStyle="Italic"/>
      <TextBlock Text="Black Italic" FontWeight="Black" FontStyle="Italic"/>
    </StackPanel>
    <StackPanel Grid.Row="1" Grid.Column="0" Margin="10,20,0,10">
      <TextBlock Text="Condensed Thin" FontWeight="Thin" FontStretch="Condensed"/>
      <TextBlock Text="Light Condensed" FontWeight="Light" FontStretch="Condensed"/>
      <TextBlock Text="Regular Condensed" FontWeight="Normal" FontStretch="Condensed"/>
      <TextBlock Text="Medium Condensed" FontWeight="Medium" FontStretch="Condensed"/>
      <TextBlock Text="Bold Condensed" FontWeight="Bold" FontStretch="Condensed"/>
      <TextBlock Text="Black Condensed" FontWeight="Black" FontStretch="Condensed"/>
    </StackPanel>
    <StackPanel Grid.Row="1" Grid.Column="1" Margin="30,20,10,10">
      <TextBlock Text="Condensed Thin Italic" FontWeight="Thin" FontStyle="Italic" FontStretch="Condensed"/>
      <TextBlock Text="Condensed Light Italic" FontWeight="Light" FontStyle="Italic" FontStretch="Condensed"/>
      <TextBlock Text="Condensed Regular Italic" FontWeight="Normal" FontStyle="Italic" FontStretch="Condensed"/>
      <TextBlock Text="Condensed Medium Italic" FontWeight="Medium" FontStyle="Italic" FontStretch="Condensed"/>
      <TextBlock Text="Condensed Bold Italic" FontWeight="Bold" FontStyle="Italic" FontStretch="Condensed"/>
      <TextBlock Text="Condensed Black Italic" FontWeight="Black" FontStretch="Condensed"/>
    </StackPanel>
  </Grid>
</Grid>
```

![TextTutorialImg3.jpg](https://www.noesisengine.com/docs/TextTutorialImg3.jpg)

# Layout properties

As any other UI element in Noesis, a TextBlock can be positioned relative to the parent container using the HorizontalAlignment and VerticalAlignment properties from [FrameworkElement](https://www.noesisengine.com/docs/Gui.Core._FrameworkElement.html). The layout process uses these properties to assign a rectangle to the TextBox where the text will be displayed. How text is aligned inside that rectangle can be specified using the TextAlignment property, which accepts the Left (default), Center, Justify and Right values.

```xml
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Background="White"
  TextElement.FontFamily="Fonts/#Roboto"
  TextElement.FontSize="16"
  TextElement.Foreground="Black">

  <Viewbox>
    <StackPanel Margin="10" HorizontalAlignment="Center" VerticalAlignment="Center" Orientation="Horizontal">
      <StackPanel Width="370">
        <TextBlock Margin="0,5" Background="WhiteSmoke" Padding="10" TextWrapping="Wrap" TextAlignment="Left">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
eiusmod tempor
          incididunt ut labore et dolore magna aliqua
        </TextBlock>
        <TextBlock Margin="0,5" Background="WhiteSmoke" Padding="10" TextWrapping="Wrap" TextAlignment="Justify">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
eiusmod tempor
          incididunt ut labore et dolore magna aliqua
        </TextBlock>
        <TextBlock Margin="0,5" Background="WhiteSmoke" Padding="10" TextWrapping="Wrap" TextAlignment="Center">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
eiusmod tempor
          incididunt ut labore et dolore magna aliqua
        </TextBlock>
        <TextBlock Margin="0,5" Background="WhiteSmoke" Padding="10" TextWrapping="Wrap" TextAlignment="Right">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
eiusmod tempor
          incididunt ut labore et dolore magna aliqua
        </TextBlock>
      </StackPanel>
    </StackPanel>
  </Viewbox>
</Grid>
```

![TextTutorialImg4.jpg](https://www.noesisengine.com/docs/TextTutorialImg4.jpg)

In addition to text alignment, user can specify how text behaves when it reaches the edge of the containing box. This can be done through the TextWrapping property which can be set to NoWrap (default), Wrap and WrapWithOverflow. When text overflows the content area the property TextTrimming defines the text trimming behavior. Valid values are: None (default), CharacterEllipsis and WordEllipsis.

```xml
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Background="White" UseLayoutRounding="True"
  TextElement.Foreground="Black">
  <Grid HorizontalAlignment="Center" VerticalAlignment="Center">
    <Grid.RowDefinitions>
      <RowDefinition/>
      <RowDefinition/>
      <RowDefinition/>
      <RowDefinition/>
      <RowDefinition/>
      <RowDefinition/>
    </Grid.RowDefinitions>
    <Grid.ColumnDefinitions>
      <ColumnDefinition/>
      <ColumnDefinition/>
      <ColumnDefinition/>
      <ColumnDefinition/>
      <ColumnDefinition/>
      <ColumnDefinition/>
      <ColumnDefinition/>
      <ColumnDefinition/>
      <ColumnDefinition/>
      <ColumnDefinition/>
    </Grid.ColumnDefinitions>

    <TextBlock Grid.Row="2" Grid.Column="0" Text="Justify" TextAlignment="Right" FontWeight="Bold"
        VerticalAlignment="Center"/>
    <TextBlock Grid.Row="3" Grid.Column="0" Text="Left" TextAlignment="Right" FontWeight="Bold"
        VerticalAlignment="Center"/>
    <TextBlock Grid.Row="4" Grid.Column="0" Text="Center" TextAlignment="Right" FontWeight="Bold"
        VerticalAlignment="Center"/>
    <TextBlock Grid.Row="5" Grid.Column="0" Text="Right" TextAlignment="Right" FontWeight="Bold"
        VerticalAlignment="Center"/>

    <Border Grid.Row="0" Grid.Column="1" Grid.ColumnSpan="3" Background="LightGray" Margin="5,1" Padding="0,2">
      <TextBlock Text="NoWrap" TextAlignment="Center" FontWeight="Bold"/>
    </Border>
    <Border Grid.Row="0" Grid.Column="4" Grid.ColumnSpan="3" Background="LightGray" Margin="5,1" Padding="0,2">
      <TextBlock Text="Wrap" TextAlignment="Center" FontWeight="Bold"/>
    </Border>
    <Border Grid.Row="0" Grid.Column="7" Grid.ColumnSpan="3" Background="LightGray" Margin="5,1" Padding="0,2">
      <TextBlock Text="WrapWithOverflow" TextAlignment="Center" FontWeight="Bold"/>
    </Border>

    <TextBlock Grid.Row="1" Grid.Column="1" Text="NoTrimming" TextAlignment="Center" FontWeight="Bold"/>
    <TextBlock Grid.Row="1" Grid.Column="2" Text="CharTrimming" TextAlignment="Center" FontWeight="Bold"/>
    <TextBlock Grid.Row="1" Grid.Column="3" Text="WordTrimming" TextAlignment="Center" FontWeight="Bold"/>

    <TextBlock Grid.Row="1" Grid.Column="4" Text="NoTrimming" TextAlignment="Center" FontWeight="Bold"/>
    <TextBlock Grid.Row="1" Grid.Column="5" Text="CharTrimming" TextAlignment="Center" FontWeight="Bold"/>
    <TextBlock Grid.Row="1" Grid.Column="6" Text="WordTrimming" TextAlignment="Center" FontWeight="Bold"/>

    <TextBlock Grid.Row="1" Grid.Column="7" Text="NoTrimming" TextAlignment="Center" FontWeight="Bold"/>
    <TextBlock Grid.Row="1" Grid.Column="8" Text="CharTrimming" TextAlignment="Center" FontWeight="Bold"/>
    <TextBlock Grid.Row="1" Grid.Column="9" Text="WordTrimming" TextAlignment="Center" FontWeight="Bold"/>

    <Border Grid.Row="2" Grid.Column="1" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Justify" TextWrapping="NoWrap" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="2" Grid.Column="2" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Justify" TextWrapping="NoWrap" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="2" Grid.Column="3" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Justify" TextWrapping="NoWrap" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>

    <Border Grid.Row="2" Grid.Column="4" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Justify" TextWrapping="Wrap" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="2" Grid.Column="5" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Justify" TextWrapping="Wrap" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="2" Grid.Column="6" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Justify" TextWrapping="Wrap" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>

    <Border Grid.Row="2" Grid.Column="7" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Justify" TextWrapping="WrapWithOverflow" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="2" Grid.Column="8" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Justify" TextWrapping="WrapWithOverflow" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="2" Grid.Column="9" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Justify" TextWrapping="WrapWithOverflow" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>

    <Border Grid.Row="3" Grid.Column="1" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Left" TextWrapping="NoWrap" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="3" Grid.Column="2" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Left" TextWrapping="NoWrap" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="3" Grid.Column="3" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Left" TextWrapping="NoWrap" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>

    <Border Grid.Row="3" Grid.Column="4" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Left" TextWrapping="Wrap" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="3" Grid.Column="5" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Left" TextWrapping="Wrap" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="3" Grid.Column="6" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Left" TextWrapping="Wrap" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>

    <Border Grid.Row="3" Grid.Column="7" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Left" TextWrapping="WrapWithOverflow" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="3" Grid.Column="8" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Left" TextWrapping="WrapWithOverflow" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="3" Grid.Column="9" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Left" TextWrapping="WrapWithOverflow" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>

    <Border Grid.Row="4" Grid.Column="1" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Center" TextWrapping="NoWrap" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="4" Grid.Column="2" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Center" TextWrapping="NoWrap" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="4" Grid.Column="3" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Center" TextWrapping="NoWrap" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>

    <Border Grid.Row="4" Grid.Column="4" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Center" TextWrapping="Wrap" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="4" Grid.Column="5" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Center" TextWrapping="Wrap" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="4" Grid.Column="6" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Center" TextWrapping="Wrap" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>

    <Border Grid.Row="4" Grid.Column="7" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Center" TextWrapping="WrapWithOverflow" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="4" Grid.Column="8" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Center" TextWrapping="WrapWithOverflow" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="4" Grid.Column="9" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Center" TextWrapping="WrapWithOverflow" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>

    <Border Grid.Row="5" Grid.Column="1" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Right" TextWrapping="NoWrap" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="5" Grid.Column="2" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Right" TextWrapping="NoWrap" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="5" Grid.Column="3" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Right" TextWrapping="NoWrap" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>

    <Border Grid.Row="5" Grid.Column="4" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Right" TextWrapping="Wrap" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="5" Grid.Column="5" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Right" TextWrapping="Wrap" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="5" Grid.Column="6" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Right" TextWrapping="Wrap" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>

    <Border Grid.Row="5" Grid.Column="7" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Right" TextWrapping="WrapWithOverflow" TextTrimming="None"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="5" Grid.Column="8" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Right" TextWrapping="WrapWithOverflow" TextTrimming="CharacterEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
    <Border Grid.Row="5" Grid.Column="9" BorderBrush="Black" BorderThickness="1" Margin="5,3" Width="100">
      <TextBlock TextAlignment="Right" TextWrapping="WrapWithOverflow" TextTrimming="WordEllipsis"
          Text="Some text to tryout quitedifferentorsimilar alignments"/>
    </Border>
  </Grid>
</Grid>
```

![TextTutorialImg5.png](https://www.noesisengine.com/docs/TextTutorialImg5.png)

# Color properties

TextBlock defines the following properties to set the color of the text and its background:

- The Foreground property is used to specify the color of the text.
- The Background property is used to specify the color that fills the arrangement rectangle of the TextBlock.

We also provide extensions to add stroking capabilities to TextBlock elements. These extensions are defined under the namespace NoesisGUIExtensions that should be included in the root element of the XAML file. Attached properties Text.Stroke and Text.StrokeThickness can be used to specify the color of the stroke and stroke thickness respectively (see highlighted lines in the following example).

```xml
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  xmlns:noesis="clr-namespace:NoesisGUIExtensions">
  <StackPanel VerticalAlignment="Center" Width="200" TextElement.FontSize="25">
    <TextBlock Text="Foreground" TextAlignment="Center" Margin="4" Foreground="DodgerBlue"/>
    <TextBlock Text="Background" TextAlignment="Center" Margin="3" Padding="1" Background="DodgerBlue"/>
    <TextBlock Text="Stroke" TextAlignment="Center" Margin="4"
      noesis:Text.Stroke="DodgerBlue"
      noesis:Text.StrokeThickness="2.5"/>
  </StackPanel>
</Grid>
```

![TextTutorialImg6.jpg](https://www.noesisengine.com/docs/TextTutorialImg6.jpg)

Note that you can also use gradients for both foreground and background properties.

```xml
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Background="White"
  TextElement.FontFamily="Fonts/#Roboto"
  TextElement.FontSize="32"
  TextElement.Foreground="Black">

  <Viewbox>
    <StackPanel Margin="40" VerticalAlignment="Center" HorizontalAlignment="Left">
      <TextBlock>
        <Bold FontSize="20" Foreground="Gray">SolidColorBrush</Bold>
        <LineBreak/>
        <Bold>
          <Span Foreground="Red">Different</Span>
          <Span Foreground="YellowGreen">solid</Span>
          <Span Foreground="Orange">colors</Span>
        </Bold>
        for the
        <Italic Foreground="DodgerBlue">Foreground</Italic>

        <LineBreak/>
        <LineBreak/>

        <Bold FontSize="20" Foreground="Gray">LinearGradientBrush</Bold>
        <LineBreak/>
        <Bold>
          <Span>
            <Span.Foreground>
              <LinearGradientBrush StartPoint="0,0" EndPoint="1,0">
                <GradientStop Color="Red" Offset="0"/>
                <GradientStop Color="YellowGreen" Offset="1"/>
              </LinearGradientBrush>
            </Span.Foreground>
            Different
          </Span>
          <Span>
            <Span.Foreground>
              <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">
                <GradientStop Color="Green" Offset="0"/>
                <GradientStop Color="Gold" Offset="1"/>
              </LinearGradientBrush>
            </Span.Foreground>
            linear
          </Span>
          <Span>
            <Span.Foreground>
              <LinearGradientBrush StartPoint="0,0" EndPoint="1,1">
                <GradientStop Color="Orange" Offset="0"/>
                <GradientStop Color="DodgerBlue" Offset="1"/>
              </LinearGradientBrush>
            </Span.Foreground>
            gradients
          </Span>
        </Bold>
        for the
        <Italic>
          <Italic.Foreground>
            <LinearGradientBrush StartPoint="0,1" EndPoint="1,0">
              <GradientStop Color="DodgerBlue" Offset="0"/>
              <GradientStop Color="Magenta" Offset="1"/>
            </LinearGradientBrush>
          </Italic.Foreground>
          Foreground
        </Italic>

        <LineBreak/>
        <LineBreak/>

        <Bold FontSize="20" Foreground="Gray">RadialGradientBrush</Bold>
        <LineBreak/>
        <Bold>
          <Span>
            <Span.Foreground>
              <RadialGradientBrush GradientOrigin="0,0" Center="0,0" SpreadMethod="Reflect">
                <GradientStop Color="Red" Offset="0"/>
                <GradientStop Color="YellowGreen" Offset="1"/>
              </RadialGradientBrush>
            </Span.Foreground>
            Different
          </Span>
          <Span>
            <Span.Foreground>
              <RadialGradientBrush>
                <GradientStop Color="Green" Offset="0"/>
                <GradientStop Color="Gold" Offset="1"/>
              </RadialGradientBrush>
            </Span.Foreground>
            radial
          </Span>
          <Span>
            <Span.Foreground>
              <RadialGradientBrush GradientOrigin="1,1" Center="1,1" SpreadMethod="Reflect">
                <GradientStop Color="Orange" Offset="0"/>
                <GradientStop Color="DodgerBlue" Offset="1"/>
              </RadialGradientBrush>
            </Span.Foreground>
            gradients
          </Span>
        </Bold>
        for the
        <Italic>
          <Italic.Foreground>
            <RadialGradientBrush RadiusX="0.2" SpreadMethod="Repeat">
              <GradientStop Color="DodgerBlue" Offset="0"/>
              <GradientStop Color="Magenta" Offset="1"/>
            </RadialGradientBrush>
          </Italic.Foreground>
          Foreground
        </Italic>
      </TextBlock>
    </StackPanel>
  </Viewbox>
</Grid>
```

![TextTutorialImg7.jpg](https://www.noesisengine.com/docs/TextTutorialImg7.jpg)

# Variable Fonts

[Variable fonts](https://fonts.google.com/knowledge/introducing_type/introducing_variable_fonts) are an innovative type of font technology that allows a single font file to contain multiple styles and weights, providing designers with unprecedented flexibility and control. Unlike traditional fonts, which require separate files for each weight and style, variable fonts use continuous ranges of values, enabling smooth transitions between styles, weights, widths, and other attributes. This results in reduced file sizes and enhanced performance. Variable fonts also empower designers to achieve more dynamic and responsive typography, adapting seamlessly to various screen sizes and resolutions. This versatility marks a significant advancement in digital typography, offering both creative and functional benefits.

Parametric axes in variable fonts are specific dimensions along which a font's attributes can be adjusted. These axes allow for fine-tuned customization of the font's appearance, enabling a vast range of typographic expressions from a single font file.

The standard axes for Weight, Width, and Italic are automatically translated to the properties FontWeight, FontStretch, and FontStyle, respectively.

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">

  <StackPanel>
    <TextBlock FontFamily="./#Anybody" FontWeight="Black">The quick brown fox</TextBlock>
    <TextBlock FontFamily="./#Anybody" FontWeight="Normal">The quick brown fox</TextBlock>
    <TextBlock FontFamily="./#Anybody" FontWeight="Light">The quick brown fox</TextBlock>
  </StackPanel>

</Grid>
```

Variable fonts contain predefined named instances, such as 'Recursive Light' These instances represent fixed positions on the axes, defined by the type designer, and can be set in the FontFamily property.

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">

  <StackPanel>
    <TextBlock FontFamily="./#Anybody Black">The quick brown fox</TextBlock>
    <TextBlock FontFamily="./#Anybody Medium">The quick brown fox</TextBlock>
    <TextBlock FontFamily="./#Anybody Light">The quick brown fox</TextBlock>
  </StackPanel>

</Grid>
```

Individual axes can also be set in the FontFamily property by specifying the name of the axis followed by a colon and its value, such as 'wght:700'.

```xml
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">

  <StackPanel>
    <TextBlock FontFamily="./#Anybody wght:700 wdth:110">The quick brown fox</TextBlock>
    <TextBlock FontFamily="./#Anybody wght:500 wdth:100">The quick brown fox</TextBlock>
    <TextBlock FontFamily="./#Anybody wght:300 wdth:90">The quick brown fox</TextBlock>
  </StackPanel>

</Grid>
```

## Additional Links

- [HOME](https://www.noesisengine.com/) - NoesisGUI
- [FEATURES](https://www.noesisengine.com/noesisgui) - NoesisGUI Features
- [STUDIO](https://www.noesisengine.com/studio) - NoesisGUI Studio
- [PRICING](https://www.noesisengine.com/licensing.php) - NoesisGUI Pricing
- [DEVELOPER](https://www.noesisengine.com/forums) - NoesisGUI Developer Resources
- [CONTACT](https://www.noesisengine.com/contact.php) - Noesis Contact
- [FORUMS](https://www.noesisengine.com/forums) - NoesisGUI Forums
- [SAMPLES](https://www.noesisengine.com/developers/samples.php) - NoesisGUI Samples
- [XAMLTOY](https://www.noesisengine.com/xamltoy) - NoesisGUI XamlToy
- [DOWNLOADS](https://www.noesisengine.com/developers/downloads.php) - NoesisGUI Downloads
- [DOCUMENTATION](https://www.noesisengine.com/docs/Gui.Core.Index.html) - NoesisGUI Documentation
- [BUGTRACKER](https://www.noesisengine.com/bugs/my_view_page.php) - NoesisGUI Bug Tracker
- [ROADMAP](https://www.noesisengine.com/bugs/roadmap_page.php) - roadmap

[NoesisGUI GitHub](https://github.com/Noesis)  
[NoesisGUI Linkedin](https://www.linkedin.com/company/noesis-technologies-sl)  
[NoesisGUI Twitter](https://twitter.com/noesisengine)  
[NoesisGUI Youtube](https://www.youtube.com/user/NoesisTechnologies)

© 2013 Noesis Technologies  
[Privacy](https://www.noesisengine.com/legal/privacy.php)  
[Terms & Conditions](https://www.noesisengine.com/legal/terms-of-use.php)