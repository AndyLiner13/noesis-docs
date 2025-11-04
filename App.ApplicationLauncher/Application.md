# Application Class

## namespace [NoesisApp](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesisapp-namespace) | [MSDN](http://msdn.microsoft.com/en-us/library/system.windows.application.aspx)

Encapsulates a NoesisGUI application.

## Inheritance Hierarchy

- Application

## Properties

| Property | Description |
|----------|-------------|
| Arguments | Retrieves command line arguments |
| MainWindow | Gets the main window of the application |
| RenderContext | Gets the render context of the application |
| Resources | Gets or sets a collection of application-scope resources, such as styles and brushes |
| StartupUri | Gets or sets a UI that is automatically shown when application starts |

## Attached Properties

Application has no attached properties

## Methods

| Method | Description |
|--------|-------------|
| Activated() | Occurs when an application becomes the foreground application |
| Current() | Gets the current application object |
| Deactivated() | Occurs when an application stops being the foreground application |
| Exit() | Occurs just before an application shuts down |
| Init(display, arguments) | Initializes the application with on the given display and command line arguments |
| Shutdown(exitCode) | Shuts down an application that returns the specified exit code to the operating system |
| StartUp() | Occurs when the Application is initialized |
| Tick(time) | Ticks application |

## Events

Application has no events