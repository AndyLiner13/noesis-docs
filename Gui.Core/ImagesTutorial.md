Source: https://www.noesisengine.com/docs/Gui.Core.ImagesTutorial.html

# Images Tutorial

# Using Images

![github](https://www.noesisengine.com/docs/github.png) [Tutorial Data](https://github.com/Noesis/Tutorials/tree/master/Snippets/Image)

The [Image](_Image.md) control is used to insert an image whose location is specified in the *Source* attribute using an [URI](../Gui.Providers/_Uri.md):

```
<Image Source="Images/melon1.png"/>
```

As the rest of controls, an *Image* is measured and arranged, so its size depends not only on the original image dimensions. Layout properties determine the space available for the Image, and the *Stretch* property defines how the image fills that available space:

- **None**: dimensions are preserved.
- **Fill**: the image fills the available space, dimensions are modified.
- **Uniform**: the image fills as much as possible the available space preserving the aspect ratio.
- **UniformToFill**: the image totally fills the available space preserving the aspect ratio and clipping the image if it is too large.

The following sample shows all the possible strecth modes of an *Image* control:

```
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Background="White" TextElement.Foreground="Black">
  <StackPanel VerticalAlignment="Center" HorizontalAlignment="Center">
    <TextBlock Text="Original Image" TextAlignment="Center"/>
    <Border BorderBrush="Black" BorderThickness="1" Margin="5,0" HorizontalAlignment="Center"
     VerticalAlignment="Center">
      <Image Source="Images/melon1.png" Stretch="None"/>
    </Border>
    <Grid Margin="0,10,0,0">
      <Grid.ColumnDefinitions>
        <ColumnDefinition/>
        <ColumnDefinition/>
        <ColumnDefinition/>
        <ColumnDefinition/>
      </Grid.ColumnDefinitions>
      <Grid.RowDefinitions>
        <RowDefinition/>
        <RowDefinition/>
      </Grid.RowDefinitions>
      <TextBlock Text="None" TextAlignment="Center" Grid.Column="0"/>
      <TextBlock Text="Fill" TextAlignment="Center" Grid.Column="1"/>
      <TextBlock Text="Uniform" TextAlignment="Center" Grid.Column="2"/>
      <TextBlock Text="UniformToFill" TextAlignment="Center" Grid.Column="3"/>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="120" Height="200" Grid.Column="0" Grid.Row="1">
        <Image Source="Images/melon1.png" Stretch="None"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="120" Height="200" Grid.Column="1" Grid.Row="1">
        <Image Source="Images/melon1.png" Stretch="Fill"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="120" Height="200" Grid.Column="2" Grid.Row="1">
        <Image Source="Images/melon1.png" Stretch="Uniform"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="120" Height="200" Grid.Column="3" Grid.Row="1">
        <Image Source="Images/melon1.png" Stretch="UniformToFill"/>
      </Border>
    </Grid>
  </StackPanel>
</Grid>
```

![ImagesTutorialImg1.jpg](https://www.noesisengine.com/docs/ImagesTutorialImg1.jpg)

# ImageBrush

[ImageBrush](_ImageBrush.md) uses an image to paint an area of a graphics object. It is normally applied to the *Background* property of a *Panel* or *Border* or to Fill a Shape. The *ImageSource* property is meant to hold the bitmap content.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <Grid.Background>
    <ImageBrush ImageSource="Images/melon1.png" Stretch="Uniform" TileMode="Tile"
                Viewport="0,0,0.25,0.25" />
  </Grid.Background>
</Grid>
```

*ImageBrush* derives from [TileBrush](_TileBrush.md). When you paint an area by using a *TileBrush* you control three elements: *content*, *tiles* and the *output* area.

![ImagesTutorialImg6.jpg](https://www.noesisengine.com/docs/ImagesTutorialImg6.jpg)

*TileBrush* defines some interesting properties that configure how tiles are placed in the output area.

## Stretch

This property specifies how the content stretches to fit its tiles. In the following example all stretch modes are applied to Rectangle elements:

```
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" Background="White"
      TextElement.Foreground="Black">
  <StackPanel VerticalAlignment="Center" HorizontalAlignment="Center">
    <TextBlock Text="Original Image" TextAlignment="Center"/>
    <Border BorderBrush="Black" BorderThickness="1" Margin="5,0" HorizontalAlignment="Center"
     VerticalAlignment="Center">
      <Rectangle Width="300" Height="300">
        <Rectangle.Fill>
          <ImageBrush ImageSource="Images/melon1.png" Stretch="None"/>
        </Rectangle.Fill>
      </Rectangle>
    </Border>
    <Grid Margin="0,10,0,0">
      <Grid.ColumnDefinitions>
        <ColumnDefinition/>
        <ColumnDefinition/>
        <ColumnDefinition/>
        <ColumnDefinition/>
      </Grid.ColumnDefinitions>
      <Grid.RowDefinitions>
        <RowDefinition/>
        <RowDefinition/>
      </Grid.RowDefinitions>
      <TextBlock Text="None" TextAlignment="Center" Grid.Column="0"/>
      <TextBlock Text="Fill" TextAlignment="Center" Grid.Column="1"/>
      <TextBlock Text="Uniform" TextAlignment="Center" Grid.Column="2"/>
      <TextBlock Text="UniformToFill" TextAlignment="Center" Grid.Column="3"/>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="120" Height="200" Grid.Column="0" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/melon1.png" Stretch="None"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="120" Height="200" Grid.Column="1" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/melon1.png" Stretch="Fill"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="120" Height="200" Grid.Column="2" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/melon1.png" Stretch="Uniform"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="120" Height="200" Grid.Column="3" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/melon1.png" Stretch="UniformToFill"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
    </Grid>
  </StackPanel>
</Grid>
```

![ImagesTutorialImg2.jpg](https://www.noesisengine.com/docs/ImagesTutorialImg2.jpg)

## Viewbox

This property specifies the subimage of the content that defines a tile. The *ViewboxUnits* property is used to indicate whether the *Viewbox* value is interpreted as a relative, the default, or absolute value.

The following example shows the effect of different *Stretch* modes on a *TileBrush* that has a *Viewbox* that is smaller than the output area. Notice that *TileBrush* contents are never clipped to the *Viewbox* (parts of the image that are outside the *Viewbox* are tinted to make it clear).

```
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Background="White" TextElement.Foreground="Black">
  <StackPanel VerticalAlignment="Center" HorizontalAlignment="Center">
    <Grid>
      <Grid.ColumnDefinitions>
        <ColumnDefinition/>
        <ColumnDefinition/>
      </Grid.ColumnDefinitions>
      <Grid.RowDefinitions>
        <RowDefinition/>
        <RowDefinition/>
      </Grid.RowDefinitions>
      <TextBlock Text="Original Image" TextAlignment="Center"/>
      <TextBlock Text="Viewbox=&quot;0.5,0.25,0.25,0.5&quot;" TextAlignment="Center"
                 Grid.Column="1"/>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0" HorizontalAlignment="Center"
       VerticalAlignment="Center" Grid.Row="1">
        <Rectangle Width="300" Height="300">
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/melon2.png" Stretch="None"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0" HorizontalAlignment="Center"
       VerticalAlignment="Center" Grid.Column="1" Grid.Row="1">
        <Rectangle Width="300" Height="300">
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/melon2-viewbox.png" Stretch="None"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
    </Grid>
    <Grid Margin="0,10,0,0">
      <Grid.ColumnDefinitions>
        <ColumnDefinition/>
        <ColumnDefinition/>
        <ColumnDefinition/>
        <ColumnDefinition/>
      </Grid.ColumnDefinitions>
      <Grid.RowDefinitions>
        <RowDefinition/>
        <RowDefinition/>
      </Grid.RowDefinitions>
      <TextBlock Text="None" TextAlignment="Center" Grid.Column="0"/>
      <TextBlock Text="Fill" TextAlignment="Center" Grid.Column="1"/>
      <TextBlock Text="Uniform" TextAlignment="Center" Grid.Column="2"/>
      <TextBlock Text="UniformToFill" TextAlignment="Center" Grid.Column="3"/>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="150" Height="150" Grid.Column="0" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/melon2-viewbox.png" Stretch="None"
             Viewbox="0.5,0.25,0.25,0.5"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="150" Height="150" Grid.Column="1" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/melon2-viewbox.png" Stretch="Fill"
             Viewbox="0.5,0.25,0.25,0.5"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="150" Height="150" Grid.Column="2" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/melon2-viewbox.png" Stretch="Uniform"
             Viewbox="0.5,0.25,0.25,0.5"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5,0"
              Width="150" Height="150" Grid.Column="3" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/melon2-viewbox.png" Stretch="UniformToFill"
             Viewbox="0.5,0.25,0.25,0.5"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
    </Grid>
  </StackPanel>
</Grid>
```

![ImagesTutorialImg3.jpg](https://www.noesisengine.com/docs/ImagesTutorialImg3.jpg)

## Viewport

This property specifies the position and dimensions of the tile in the output area. By default, a *TileBrush* has a single tile that fills the whole output area.

The *ViewportUnits* property is used to specify whether the *Viewport* uses absolute or relative coordinates. When relative, the default mode, the coordinates are relative to the size of the output area. The point (0,0) represents the upper-left corner of the output area, and (1,1) represents the lower-right corner of the output area.

## TileMode

The *TileMode* property allows you to specify how the content of a *TileBrush* is repeated to fill the output area. To create a pattern the property *TileMode* is set to *Tile*, *FlipX*, *FlipY* or *FlipXY* and the *Viewport* of the *TileBrush* is set so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which *TileMode* setting you use.

The following example shows the different tile modes:

```
<Grid xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Background="White" TextElement.Foreground="Black">
  <StackPanel VerticalAlignment="Center" HorizontalAlignment="Center">
    <Grid>
      <Grid.RowDefinitions>
        <RowDefinition/>
        <RowDefinition/>
      </Grid.RowDefinitions>
      <TextBlock Text="Original Image" TextAlignment="Center"/>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5" HorizontalAlignment="Center"
       VerticalAlignment="Center" Grid.Row="1">
        <Rectangle Width="100" Height="100">
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/tile.png" Stretch="None"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
    </Grid>
    <Grid Margin="0,10,0,0">
      <Grid.ColumnDefinitions>
        <ColumnDefinition/>
        <ColumnDefinition/>
        <ColumnDefinition/>
        <ColumnDefinition/>
        <ColumnDefinition/>
      </Grid.ColumnDefinitions>
      <Grid.RowDefinitions>
        <RowDefinition/>
        <RowDefinition/>
        <RowDefinition/>
      </Grid.RowDefinitions>
      <TextBlock Text="None" TextAlignment="Center" Grid.Column="0"/>
      <TextBlock Text="Tile" TextAlignment="Center" Grid.Column="1"/>
      <TextBlock Text="FlipX" TextAlignment="Center" Grid.Column="2"/>
      <TextBlock Text="FlipY" TextAlignment="Center" Grid.Column="3"/>
      <TextBlock Text="FlipXY" TextAlignment="Center" Grid.Column="4"/>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5"
              Width="100" Height="100" Grid.Column="0" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/tile.png" Stretch="None" ViewportUnits="Absolute"
             Viewport="0,0,25,25" TileMode="None"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5"
              Width="100" Height="100" Grid.Column="1" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/tile.png" Stretch="None" ViewportUnits="Absolute"
             Viewport="0,0,25,25" TileMode="Tile"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5"
              Width="100" Height="100" Grid.Column="2" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/tile.png" Stretch="None" ViewportUnits="Absolute"
             Viewport="0,0,25,25" TileMode="FlipX"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5"
              Width="100" Height="100" Grid.Column="3" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/tile.png" Stretch="None" ViewportUnits="Absolute"
             Viewport="0,0,25,25" TileMode="FlipY"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5"
              Width="100" Height="100" Grid.Column="4" Grid.Row="1">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/tile.png" Stretch="None" ViewportUnits="Absolute"
             Viewport="0,0,25,25" TileMode="FlipXY"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5"
              Width="100" Height="100" Grid.Column="0" Grid.Row="2">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/tile.png" Stretch="Fill"
             ViewportUnits="RelativeToBoundingBox" Viewport="0,0,0.1,0.2" TileMode="None"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5"
              Width="100" Height="100" Grid.Column="1" Grid.Row="2">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/tile.png" Stretch="Fill"
             ViewportUnits="RelativeToBoundingBox" Viewport="0,0,0.1,0.2" TileMode="Tile"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5"
              Width="100" Height="100" Grid.Column="2" Grid.Row="2">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/tile.png" Stretch="Fill"
             ViewportUnits="RelativeToBoundingBox" Viewport="0,0,0.1,0.2" TileMode="FlipX"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5"
              Width="100" Height="100" Grid.Column="3" Grid.Row="2">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/tile.png" Stretch="Fill"
             ViewportUnits="RelativeToBoundingBox" Viewport="0,0,0.1,0.2" TileMode="FlipY"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" Margin="5"
              Width="100" Height="100" Grid.Column="4" Grid.Row="2">
        <Rectangle>
          <Rectangle.Fill>
            <ImageBrush ImageSource="Images/tile.png" Stretch="Fill"
             ViewportUnits="RelativeToBoundingBox" Viewport="0,0,0.1,0.2" TileMode="FlipXY"/>
          </Rectangle.Fill>
        </Rectangle>
      </Border>
    </Grid>
  </StackPanel>
</Grid>
```

![ImagesTutorialImg4.jpg](https://www.noesisengine.com/docs/ImagesTutorialImg4.jpg)

# Resize quality

By default noesisGUI scales images using a high-quality re-sampling algorithm implemented in the GPU. Although most of the time the quality is fine this algorithm tends to blur the results to reduce aliasing. The default algorithm can be changed by using the *BitmapScalingMode* attached property on any *UIElement* descendant.

```
<StackPanel xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            UseLayoutRounding="True" Orientation="Horizontal">

  <Grid RenderOptions.BitmapScalingMode="Linear" Width="500">
    <Grid.Background>
      <ImageBrush ImageSource="Images/bg.jpg" Stretch="UniformToFill"
                  AlignmentX="Center" AlignmentY="Center"/>
    </Grid.Background>
    <TextBlock Text="Linear" Foreground="White" HorizontalAlignment="Left"
               VerticalAlignment="Top"  Margin="10" />
  </Grid>

  <Grid RenderOptions.BitmapScalingMode="HighQuality" Width="500">
    <Grid.Background>
      <ImageBrush ImageSource="Images/bg.jpg" Stretch="UniformToFill"
                  AlignmentX="Center" AlignmentY="Center"/>
    </Grid.Background>
    <TextBlock Text="HighQuality" Foreground="White" HorizontalAlignment="Left"
               VerticalAlignment="Top" Margin="10" />
  </Grid>
</StackPanel>
```

![ImagesTutorialImg41.jpg](https://www.noesisengine.com/docs/ImagesTutorialImg41.jpg)

# Texture Atlas

Texture atlases are large textures made up of many separate textures to improve performance. It is a method traditionally used to animate sprites on screen.

Although you can use the tool you wish, we provide a plugin for [TexturePacker](http://www.texturepacker.com/) that directly generates a valid XAML that can be used as an atlas in NoesisGui. The plugin can be found in our [github](https://github.com/Noesis/noesisgui-contrib). The following is an atlas generated with that tool:

```
<!-- Created using Noesis XAML exporter for TexturePacker (http://www.texturepacker.com) -->
<ResourceDictionary
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <ImageBrush x:Key="aladin01" ImageSource="aladin-atlas.png" Viewbox="145,58,33,54" ViewboxUnits="Absolute"
    Stretch="Fill"/>
  <ImageBrush x:Key="aladin02" ImageSource="aladin-atlas.png" Viewbox="180,58,30,54" ViewboxUnits="Absolute"
    Stretch="Fill"/>
  <ImageBrush x:Key="aladin03" ImageSource="aladin-atlas.png" Viewbox="73,61,27,57" ViewboxUnits="Absolute"
    Stretch="Fill"/>
  <ImageBrush x:Key="aladin04" ImageSource="aladin-atlas.png" Viewbox="39,2,33,57" ViewboxUnits="Absolute"
    Stretch="Fill"/>
  <ImageBrush x:Key="aladin05" ImageSource="aladin-atlas.png" Viewbox="112,2,38,54" ViewboxUnits="Absolute"
    Stretch="Fill"/>
  <ImageBrush x:Key="aladin06" ImageSource="aladin-atlas.png" Viewbox="74,2,36,56" ViewboxUnits="Absolute"
    Stretch="Fill"/>
  <ImageBrush x:Key="aladin07" ImageSource="aladin-atlas.png" Viewbox="152,2,31,54" ViewboxUnits="Absolute"
    Stretch="Fill"/>
  <ImageBrush x:Key="aladin08" ImageSource="aladin-atlas.png" Viewbox="185,2,27,54" ViewboxUnits="Absolute"
    Stretch="Fill"/>
  <ImageBrush x:Key="aladin09" ImageSource="aladin-atlas.png" Viewbox="41,61,30,57" ViewboxUnits="Absolute"
    Stretch="Fill"/>
  <ImageBrush x:Key="aladin10" ImageSource="aladin-atlas.png" Viewbox="2,2,35,58" ViewboxUnits="Absolute"
    Stretch="Fill"/>
  <ImageBrush x:Key="aladin11" ImageSource="aladin-atlas.png" Viewbox="102,60,41,55" ViewboxUnits="Absolute"
    Stretch="Fill"/>
  <ImageBrush x:Key="aladin12" ImageSource="aladin-atlas.png" Viewbox="2,62,37,57" ViewboxUnits="Absolute"
    Stretch="Fill"/>

</ResourceDictionary>
```

The following example shows how to reference that dictionary to use sprites in your XAML files:

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  UseLayoutRounding="True" Background="White" TextElement.Foreground="Black">

  <Grid.Resources>
    <ResourceDictionary>
      <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="Images/Aladin/aladin.xaml"/>
      </ResourceDictionary.MergedDictionaries>

      <Storyboard x:Key="AladinRun" RepeatBehavior="Forever" Duration="0:0:4.2">
        <DoubleAnimation Storyboard.TargetName="aladin" Storyboard.TargetProperty="RenderTransform.X"
          From="-30" To="500" Duration="0:0:4.2"/>
        <Storyboard Duration="0:0:0.6" RepeatBehavior="Forever">
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_01"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.00">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.05">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_02"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.00">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.05">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.10">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_03"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.00">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.10">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.15">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_04"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.00">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.15">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.20">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_05"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.00">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.20">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.25">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_06"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.00">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.25">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.30">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_07"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.00">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.30">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.35">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_08"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.00">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.35">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.40">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_09"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.00">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.40">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.45">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_10"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.00">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.45">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.50">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_11"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.0">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.50">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.55">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
          <ObjectAnimationUsingKeyFrames Storyboard.TargetName="aladin_sprite_12"
            Storyboard.TargetProperty="Visibility">
            <DiscreteObjectKeyFrame KeyTime="0:0:0.0">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.55">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Visible</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
            <DiscreteObjectKeyFrame KeyTime="0:0:0.60">
              <DiscreteObjectKeyFrame.Value>
                <Visibility>Hidden</Visibility>
              </DiscreteObjectKeyFrame.Value>
            </DiscreteObjectKeyFrame>
          </ObjectAnimationUsingKeyFrames>
        </Storyboard>
      </Storyboard>
    </ResourceDictionary>
  </Grid.Resources>

  <Grid.Triggers>
    <EventTrigger RoutedEvent="FrameworkElement.Loaded">
      <BeginStoryboard Storyboard="{StaticResource AladinRun}"/>
    </EventTrigger>
  </Grid.Triggers>

  <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">

    <TextBlock Text="Atlas Image" TextAlignment="Center"/>
    <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
      <Image Source="Images/Aladin/aladin-atlas.png" Stretch="None"/>
    </Border>

    <TextBlock Text="Image brushes for each sprite" TextAlignment="Center" Margin="0,10,0,0"/>
    <StackPanel Orientation="Horizontal" HorizontalAlignment="Center">
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin01}" Width="33" Height="54"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin02}" Width="30" Height="54"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin03}" Width="27" Height="57"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin04}" Width="33" Height="57"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin05}" Width="38" Height="54"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin06}" Width="36" Height="56"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin07}" Width="31" Height="54"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin08}" Width="27" Height="54"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin09}" Width="30" Height="57"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin10}" Width="35" Height="58"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin11}" Width="41" Height="55"/>
      </Border>
      <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Center" Margin="5">
        <Rectangle Fill="{StaticResource aladin12}" Width="37" Height="57"/>
      </Border>
    </StackPanel>

    <TextBlock Text="Animated sprites" TextAlignment="Center" Margin="0,10,0,0"/>
    <Border BorderBrush="Black" BorderThickness="1" Width="500" ClipToBounds="True">
      <Border.Background>
        <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">
          <GradientStop Offset="0" Color="Cyan"/>
          <GradientStop Offset="0.71" Color="White"/>
          <GradientStop Offset="0.72" Color="Green"/>
          <GradientStop Offset="1" Color="LightGreen"/>
        </LinearGradientBrush>
      </Border.Background>
      <Grid x:Name="aladin" HorizontalAlignment="Left" VerticalAlignment="Bottom" Margin="0,50,0,10">
        <Grid.RenderTransform>
          <TranslateTransform/>
        </Grid.RenderTransform>
        <Rectangle x:Name="aladin_sprite_01" Fill="{StaticResource aladin01}" Width="33" Height="54"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Visible"/>
        <Rectangle x:Name="aladin_sprite_02" Fill="{StaticResource aladin02}" Width="30" Height="54"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Hidden"/>
        <Rectangle x:Name="aladin_sprite_03" Fill="{StaticResource aladin03}" Width="27" Height="57"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Hidden"/>
        <Rectangle x:Name="aladin_sprite_04" Fill="{StaticResource aladin04}" Width="33" Height="57"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Hidden"/>
        <Rectangle x:Name="aladin_sprite_05" Fill="{StaticResource aladin05}" Width="38" Height="54"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Hidden"/>
        <Rectangle x:Name="aladin_sprite_06" Fill="{StaticResource aladin06}" Width="36" Height="56"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Hidden"/>
        <Rectangle x:Name="aladin_sprite_07" Fill="{StaticResource aladin07}" Width="31" Height="54"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Hidden"/>
        <Rectangle x:Name="aladin_sprite_08" Fill="{StaticResource aladin08}" Width="27" Height="54"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Hidden"/>
        <Rectangle x:Name="aladin_sprite_09" Fill="{StaticResource aladin09}" Width="30" Height="57"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Hidden"/>
        <Rectangle x:Name="aladin_sprite_10" Fill="{StaticResource aladin10}" Width="35" Height="58"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Hidden"/>
        <Rectangle x:Name="aladin_sprite_11" Fill="{StaticResource aladin11}" Width="41" Height="55"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Hidden"/>
        <Rectangle x:Name="aladin_sprite_12" Fill="{StaticResource aladin12}" Width="37" Height="57"
            HorizontalAlignment="Center" VerticalAlignment="Center" Visibility="Hidden"/>
      </Grid>
    </Border>

  </StackPanel>
</Grid>
```

![ImagesTutorialImg5.jpg](https://www.noesisengine.com/docs/ImagesTutorialImg5.jpg)

# 9-Slice Scaling

9-slice scaling is a nifty way that you can use to scale symbols without distorting them. This is especially useful when creating signs, speech bubbles, etc. The symbol is divided into 9 sections, and only the middle sections are stretched. The corners transform with the symbol but they aren't distorted.

![ImagesTutorialImg7.jpg](https://www.noesisengine.com/docs/ImagesTutorialImg7.jpg)

This technique, very common for flash designers, can be easily emulated by using a grid.

```
<Grid
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <Grid.Background>
    <RadialGradientBrush Center="0.6,0.7" GradientOrigin="0.6,0.7" RadiusX="0.6" RadiusY="0.7">
      <GradientStop Offset="0" Color="YellowGreen"/>
      <GradientStop Offset="1" Color="OliveDrab"/>
    </RadialGradientBrush>
  </Grid.Background>

  <Grid.Resources>
    <ImageBrush x:Key="WoodSignTL" ImageSource="Images/9slice.png"
                ViewboxUnits="Absolute" Viewbox="0,0,50,60"/>
    <ImageBrush x:Key="WoodSignT" ImageSource="Images/9slice.png"
                ViewboxUnits="Absolute" Viewbox="50,0,200,60"/>
    <ImageBrush x:Key="WoodSignTR" ImageSource="Images/9slice.png"
                ViewboxUnits="Absolute" Viewbox="250,0,50,60"/>

    <ImageBrush x:Key="WoodSignML" ImageSource="Images/9slice.png"
                ViewboxUnits="Absolute" Viewbox="0,60,50,80"/>
    <ImageBrush x:Key="WoodSignM" ImageSource="Images/9slice.png"
                ViewboxUnits="Absolute" Viewbox="50,60,200,80"/>
    <ImageBrush x:Key="WoodSignMR" ImageSource="Images/9slice.png"
                ViewboxUnits="Absolute" Viewbox="250,60,50,80"/>

    <ImageBrush x:Key="WoodSignBL" ImageSource="Images/9slice.png"
                ViewboxUnits="Absolute" Viewbox="0,140,50,60"/>
    <ImageBrush x:Key="WoodSignB" ImageSource="Images/9slice.png"
                ViewboxUnits="Absolute" Viewbox="50,140,200,60"/>
    <ImageBrush x:Key="WoodSignBR" ImageSource="Images/9slice.png"
                ViewboxUnits="Absolute" Viewbox="250,140,50,60"/>
  </Grid.Resources>

  <StackPanel Orientation="Horizontal" HorizontalAlignment="Center" VerticalAlignment="Center">

    <Grid Width="200" Height="150">
      <Grid.ColumnDefinitions>
        <ColumnDefinition Width="50"/>
        <ColumnDefinition Width="*"/>
        <ColumnDefinition Width="50"/>
      </Grid.ColumnDefinitions>
      <Grid.RowDefinitions>
        <RowDefinition Height="60"/>
        <RowDefinition Height="*"/>
        <RowDefinition Height="60"/>
      </Grid.RowDefinitions>

      <Rectangle Grid.Column="0" Grid.Row="0" Fill="{StaticResource WoodSignTL}"/>
      <Rectangle Grid.Column="1" Grid.Row="0" Fill="{StaticResource WoodSignT}"/>
      <Rectangle Grid.Column="2" Grid.Row="0" Fill="{StaticResource WoodSignTR}"/>

      <Rectangle Grid.Column="0" Grid.Row="1" Fill="{StaticResource WoodSignML}"/>
      <Rectangle Grid.Column="1" Grid.Row="1" Fill="{StaticResource WoodSignM}"/>
      <Rectangle Grid.Column="2" Grid.Row="1" Fill="{StaticResource WoodSignMR}"/>

      <Rectangle Grid.Column="0" Grid.Row="2" Fill="{StaticResource WoodSignBL}"/>
      <Rectangle Grid.Column="1" Grid.Row="2" Fill="{StaticResource WoodSignB}"/>
      <Rectangle Grid.Column="2" Grid.Row="2" Fill="{StaticResource WoodSignBR}"/>

      <TextBlock Grid.ColumnSpan="3" Grid.RowSpan="3" HorizontalAlignment="Center" VerticalAlignment="Center"
          FontFamily="#Another" FontSize="40" Foreground="#402000" Text="Welcome!"/>
    </Grid>

  </StackPanel>

</Grid>
```

# Runtime Images

Sometimes you need to generate images that are not available at compile time. For example, when you are downloading an image from the internet or when your application supports user generated images. For these cases, the [TextureSource](_TextureSource.md) class is provided. A *TextureSource* is initialized passing a native texture handle. Once initialized it must be set to the corresponding *Image* or *ImageBrush*.

Note

NoesisGUI expects texture with alpha in [premultiplied](https://shawnhargreaves.com/blog/premultiplied-alpha.html) format. Take this into account when you are passing texture handles.

[http://www.noesisengine.com/forums/viewtopic.php?f=3&t=194](https://www.noesisengine.com/forums/viewtopic.php?f=3&t=194)

C++

```
void SetTexture(ID3D11Texture2D* d3dTexture, FrameworkElement* root)
{
    Ptr<Texture> texture = D3D11Factory::WrapTexture(d3dTexture, 512, 512, 1,
      TextureFormat::BGRA8, false);
    Image* image = root->FindName<Image>("image");
    image->SetSource(MakePtr<TextureSource>(texture));
}
```

NoesisGUI directly understands the class *Texture2D* provided by Unity.

C# - Unity

```
Grid grid = (Grid)GetComponent<NoesisView>().Content;

Texture2D texture = (Texture2D)Resources.Load("Noesis");
TextureSource source = new TextureSource(texture);

Image image = (Image)grid.FindName("image");
image.SetSource(source);
```

Note

Although in this sample we use a Texture2D, RenderTexture and MovieTexture are also supported. In fact, all classes deriving from Texture are supported.