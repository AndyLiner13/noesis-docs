Source: https://www.noesisengine.com/docs/Gui.Core.ProvidersTutorial.html

# Resource Providers

In Noesis, the resource loading process is facilitated through the installation of custom providers. These specialized providers play a pivotal role in handling various resource types, such as XAML, Texture, and Font. Providers can be installed globally, for a specific [Uri](/Gui.Providers/_Uri.md) scheme or even to a particular assembly name.

# Global Providers

After initializing Noesis, it is essential to install the global providers for each type of resource. These providers handle requests that aren't resolved by any other more specific ones.

```
Noesis::GUI::Init();

// Install global providers
Noesis::GUI::SetXamlProvider(xamlProvider);
Noesis::GUI::SetTextureProvider(textureProvider);
Noesis::GUI::SetFontProvider(fontProvider);
```

These three kinds of providers share the same abstraction for sequence of bytes, the *Stream* abstract class.

```
class Stream: public BaseComponent
{
public:
    /// Set the current position within the stream
    virtual void SetPosition(uint32_t pos) = 0;

    /// Returns the current position within the stream
    virtual uint32_t GetPosition() const = 0;

    /// Returns the length of the stream in bytes
    virtual uint32_t GetLength() const = 0;

    /// Reads data at the current position and advances it by the number of bytes read
    /// Returns the total number of bytes read. This can be less than the number of bytes requested
    virtual uint32_t Read(void* buffer, uint32_t size) = 0;

    /// Returns the starting address for the whole data or null if not supported
    /// It is recommended, especially when reading fonts, to return a non-null value
    virtual const void* GetMemoryBase() const = 0;

    /// Closes the current stream and releases any resources associated with the current stream
    virtual void Close() = 0;
};
```

Note

Although the implementation of the method 'GetMemoryBase' is optional, we highly recommend implementing it for faster loading of assets.

# Scheme/Assemby Providers

Besides the global resource providers, it's also possible to install providers specific to a particular assembly or scheme. For example, the following code will install a handler for pack [Uris](/Gui.Providers/_Uri.md) that contain the assembly name "*MyExtensions*".

```
// This will handle uris like '/MyExtensions;component/MainWindow.xaml'
Noesis::GUI::SetAssemblyXamlProvider("MyExtensions", xamlProvider);
```

Likewise, a similar process applies to installing handlers for specific [Uri](/Gui.Providers/_Uri.md) schemes. For example, the following code will handle all [Uris](/Gui.Providers/_Uri.md) using the "*noesis*" scheme.

```
// This will handle uris like 'noesis:///MainWindow.xaml'
Noesis::GUI::SetSchemeXamlProvider("noesis", xamlProvider);
```

Additionally, both scheme and assembly can be specified using the following API:

```
/// This will handle uris like 'noesis:///MyExtensions;component/MainWindow.xaml'
Noesis::GUI::SetSchemeAssemblyXamlProvider("noesis", "MyExtensions", xamlProvider);
```

# Categories

A unique base class exists for each provider, providing a foundation for their implementation.

## Xaml provider

The base class from implementing a provider of XAMLs is *XamlProvider*.

```
class XamlProvider: public BaseComponent
{
public:
    /// Loads XAML from the specified URI. Returns null when xaml is not found
    virtual Ptr<Stream> LoadXaml(const Uri& uri) = 0;
};
```

The implementation is straightforward. You basically must provide a stream for each [Uri](/Gui.Providers/_Uri.md) that is requested. You can find two *XamlProvider* implementations in our [Application Framework](/Gui.Core/ApplicationTutorial.md): *LocalXamlProvider* for loading XAMLs from disk and *EmbeddedXamlProvider* for loading XAMLs embedded in the executable.

## Texture provider

Texture providers are a bit more complex because you need to implement two different functions. At the main thread the layout process needs information about the dimensions of the texture. You provide that information through the *GetTextureInfo* function. The method in charge of uploading the texture to the GPU is *LoadTexture* and it is always called from the render thread.

```
class TextureProvider: public BaseComponent
{
public:
    /// Returns metadata for the texture at the given URI or empty rectangle if texture is not found
    virtual TextureInfo GetTextureInfo(const Uri& uri) = 0;

    /// Returns a texture compatible with the given device or null if texture is not found
    virtual Ptr<Texture> LoadTexture(const Uri& uri, RenderDevice* device) = 0;
};
```

Note that since NoesisGUI 3.1.6, *TextureInfo* contains rectangle information to implement texture atlas.

```
// Texture metadata returned by TextureProvider::GetTextureInfo()
// The rectangle [x, y, width, height] defines the logical surface used by the texture
// Note that the provider can reuse the same texture with different names and rectangles to
// implementing texture atlas compatible with standard XAML. For example:
//
//  - ItemA ==> Atlas.png [0,   0, 100, 100]
//  - ItemB ==> Atlas.png [0, 100, 100, 200]
//
//  <StackPanel>
//    <Image Source="ItemA.png"/>
//    <Image Source="ItemB.png"/>
//  </StackPanel>
//
// The member 'dpiScale' can be used for scaling (eg: 96 dpi = 1.0, 72 dpi = 0.75 (72/96))
struct TextureInfo
{
    uint32_t width = 0;
    uint32_t height = 0;
    uint32_t x = 0;
    uint32_t y = 0;

    float dpiScale = 1.0f;
};
```

The [Application Framework](/Gui.Core/ApplicationTutorial.md) provides a helper class, *FileTextureProvider*, that will create textures from image files stored on disk. It exposes a virtual function that must be implemented to load the requested filename at the given [Uri](/Gui.Providers/_Uri.md).

```
class FileTextureProvider: public TextureProvider
{
protected:
    virtual Ptr<Stream> OpenStream(const Uri& uri) const = 0;
};
```

Similar to *XamlProvider* you can find *LocalTextureProvider* and *EmbeddedTextureProvider* implementations within the [Application Framework](/Gui.Core/ApplicationTutorial.md).

## Font provider

The font provider is the most complex to implement. The base class in charge of loading fonts is *FontProvider*.

```
class FontProvider: public BaseComponent
{
public:
    /// Finds the font in the given URI that best matches the specified properties
    /// Returns null stream when there are not matches
    virtual FontSource MatchFont(const Uri& baseUri, const char* familyName, FontWeight& weight,
        FontStretch& stretch, FontStyle& style) = 0;

    /// Returns true if the requested font family exists in given URI
    virtual bool FamilyExists(const Uri& baseUri, const char* familyName) = 0;
};
```

To help with the implementation of this provider there is an intermediate class, *CachedFontProvider*, that scans folders and extracts family information from *TrueType* and *OpenType* files. It also implements the font matching algorithm.

*CachedFontProvider* exposes two virtual functions, *ScanFolder* and *OpenFont*:

- In *ScanFolder* you must register all the fonts available in the requested folder. Each font is registered by calling *RegisterFont*.
- *OpenFont* is the function in charge of providing the stream corresponding to each of the registered filenames.

```
class CachedFontProvider: public FontProvider
{
protected:
    /// Registers a font filename in the given folder. Each time this function is invoked, the
    /// given filename is opened and scanned (through OpenFont). It is recommended deferring
    /// this call as much as possible (for example, until ScanFolder is invoked)
    void RegisterFont(const Uri& folder, const char* filename);

    /// Registers a font face with given font properties. In comparison with the previous function
    /// this one doesn't open the filename to scan it. Always use this function if possible
    void RegisterFont(const Uri& folder, const char* filename, uint32_t index, const char* family,
        FontWeight weight, FontStretch stretch, FontStyle style);

    /// First time a font is requested from a folder, this function is invoked to give inheritors
    /// the opportunity to register faces found in that folder
    virtual void ScanFolder(const Uri& folder);

    /// Returns a stream to a previously registered filename
    virtual Ptr<Stream> OpenFont(const Uri& folder, const char* filename) const = 0;
};
```

The most efficient way to provide custom fonts for Noesis is creating a new class derived from *CachedFontProvider* and in its constructor registering a fixed list of fonts with its corresponding attributes using *RegisterFont*.

Similar to the rest of providers, *LocalFontProvider* and *EmbeddedFontProvider* are sample implementations available in the [Application Framework](/Gui.Core/ApplicationTutorial.md). We recommend using this classes instead of *CachedFontProvider*.

# Hot Reload

Providers also expose a delegate to inform when a resource needs to be [reloaded](/Gui.Core/HotReloadTutorial.md). Each time this delegate is invoked the corresponding resource will be hot reloaded. *RaiseXamlChanged*, *RaiseTextureChanged* and *RaiseFontChanged* are the corresponding functions in charge of notifying Noesis that a resource needs to be reloaded.

```
class XamlProvider: public BaseComponent
{
public:
    /// Delegate to notify changes to the XAML file text
    typedef Delegate<void (const Uri&)> XamlChangedDelegate;
    XamlChangedDelegate& XamlChanged() { return mXamlChanged; }
    void RaiseXamlChanged(const Uri& uri) { mXamlChanged(uri); }
};
```

This architecture also allows loading resources in a worker thread, for example, for textures:

- First time a texture is requested, a small preloaded thumbnail is returned and a job is sent to a worker thread to start loading the real texture.
- When the worker thread finishes, *RaiseTextureChanged* is invoked in the corresponding texture provider.
- Noesis will reload the texture in all places where it is being used.

Note

Our file implementations (*LocalXamlProvider*, *LocalTextureProvider* and *LocalFontProvider*) already implement support for Hot Reloading using a filesystem watcher. Although our examples use Embedded implementations by default, this can be overridden with the '--root' command line switch. For example:

```
Samples.HelloWorld --root W:/Noesis/NoesisSDK/Native/Src/Packages/Samples/HelloWorld/Data
```

This way, the content of the example can be modified with any editor and reloaded without restarting.