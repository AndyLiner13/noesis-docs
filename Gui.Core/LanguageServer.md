Source: https://www.noesisengine.com/docs/Gui.Core.LanguageServer.html

# Language Server

The Noesis *Language Server* implements the [Language Server Protocol](https://microsoft.github.io/language-server-protocol/) for XAML documents.
When used with a compatible client, the *Language Server* provides rich editor features, including completion, error reporting, and render previews.

We offer a [Visual Studio Code](https://noesisengine.com/vscode) extension that serves as a client for the *Language Server*. This client is fully compatible with any Noesis instance, including Unity and Unreal

![LanguageServerImg1.png](/LanguageServerImg1/png.md)

Our plugin automatically launches the server when using Unity or Unreal editors. If you're working in vanilla C++ or C#, a custom *Language Server* implementation is required. In cases where no language servers are detected, the Visual *Studio Code* extension initiates an internal server binary. However, this binary exclusively supports core Noesis types. To incorporate your custom types, you'll need to compile a custom *Language Server* with the required type definitions.

# Application Framework

The [Application Framework](/Gui.Core/ApplicationTutorial.md) comes equipped with a custom *Language Server*, which is initially deactivated. To enable it, utilize the '--lang\_server' command line. For a seamless experience with the *Language Server*, we suggest utilizing the '--root projectpath' command line. This switch disables the [embedded file providers](/Gui.Core/ProvidersTutorial.md) and enables direct access to the filesystem, supporting [Hot Reload](/Gui.Core/HotReloadTutorial.md).

```
Samples.HelloWorld.exe --lang_server --root Packages\Samples\HelloWorld\Data
```

# Custom Language Server

If the *App Framework* isn't integrated into your application, running the *Language Server* is a straightforward process. The initial step involves setting the server's name. It must be completed before initializing the server. The name is shown in the *Visual Studio Code* status bar.

C++

```
LangServer::SetName("LostGhost");
```

Following that, it's essential to register the providers responsible for [loading files](/Gui.Core/ProvidersTutorial.md) on the server.

C++

```
LangServer::SetXamlProvider(MakePtr<LocalXamlProvider>());
LangServer::SetTextureProvider(MakePtr<LocalTextureProvider>());
LangServer::SetFontProvider(MakePtr<LocalFontProvider>());
```

Optionally, you can register a callback for generating render preview images. If this callback is not provided, XAML Previews will be disabled in VSCode.

C++

```
LangServer::SetRenderCallback(0, [](void*, UIElement* content, int renderWidth,
    int renderHeight, double renderTime, const char* savePath)
{
    RenderContext* context = RenderContext::Current();
    RenderPreview(context, content, renderWidth, renderHeight, renderTime, savePath);
});
```

After configuring everything, you can proceed to initialize the *Language Server*.

C++

```
LangServer::Init();
```

The server needs to be ticked per frame to process messages from the client.

C++

```
LangServer::RunTick();
```

At shutdown, be sure to close the server for proper cleanup.

C++

```
LangServer::Shutdown();
```

# VSCode Tools Settings

While your application is running, the extension will connect automatically to your *Language Server*.

Additionally, you have the option to configure the extension to launch your application when *Visual Studio Code* opens a XAML document. The extension will manage this process, starting and killing it as needed.

In *Visual Studio Code* open *File > Preferences > Settings > Extensions > NoesisGUI XAML Tools*.

Set the path to your *Language Server* binary in *Language Server Path*. If you require any command line switches, these can be set in *Language Server Args*. These changes will take effect immediately.