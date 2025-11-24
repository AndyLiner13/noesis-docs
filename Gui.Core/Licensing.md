Source: https://www.noesisengine.com/docs/Gui.Core.Licensing.html

# NoesisGUI Licensing

# Evaluation

Our SDKs are designed to be evaluated without requiring a license. During the evaluation period, you can use Noesis for up to **10 minutes per session**. After 10 minutes of rendering from the start of execution, a warning message will appear. This limit allows you to test and evaluate Noesis with your specific needs and requirements.

Once you have validated Noesis and decided to continue using it, you will need to acquire a license to continue development.

For more information about the cost of licenses, please visit our [Pricing](https://www.noesisengine.com/licensing.php) page. If you have any questions or need assistance, please contact our team to get a license that best suits your needs.

# Setting the License

NoesisGUI keys are a combination of numbers and letters associated with a project name. This information is provided upon purchasing a NoesisGUI license. The following example assumes you already have a valid key similar to this one:

```
NAME: Globex Corporation
KEY : 0KrZJjrt2SYwlUcIzZMGor47iaWruwED83qFJSQR9QXgAKqQ
```

The method for applying this key depends on the specific SDK and technology being used. The following sections describe each possible scenario.

## C++ SDK

If NoesisGUI is being used without our [Application Framework](/Gui.Core/ApplicationTutorial.md), the license must be set before initialization. For example:

C++

```
Noesis::GUI::SetLicense("Globex Corporation", "0KrZJjrt2SYwlUcIzZMGor47iaWruwED83qFJSQR9QXgAKqQ");
```

When using the *Application Framework*, license is set using the preprocessor macros *NS\_LICENSE\_NAME* and *NS\_LICENSE\_KEY*. These macros must be defined globally in your project. They can also be set in the header file '*NoesisLicense.h*' located in '*$(SDK\_ROOT)/Include*'.

Include/NoesisLicense.h

```
// NS_LICENSE_NAME and NS_LICENSE_KEY must be replaced with values your were given when purchasing
// your Noesis license. If you don't want to modify this file (it will be overwritten with each new
// version) you can globally define NS_LICENSE_NAME and NS_LICENSE_KEY in your project.

#define NS_LICENSE_NAME "Globex Corporation"
#define NS_LICENSE_KEY "0KrZJjrt2SYwlUcIzZMGor47iaWruwED83qFJSQR9QXgAKqQ"
```

## C# SDK

If NoesisGUI is being used without our [Application Framework](/Gui.Core/ApplicationTutorial.md), the license must be set before initialization. For example:

C#

```
Noesis.GUI.SetLicense("Globex Corporation", "0KrZJjrt2SYwlUcIzZMGor47iaWruwED83qFJSQR9QXgAKqQ");
```

When using the *Application Framework*, the license is set in a text file, '*NoesisLicense.txt*', which is embedded into the application. In our examples, this file is located at '*$(SDK\_ROOT)/Src/NoesisLicense.txt*'.

Src/NoesisLicense.txt

```
Globex Corporation
0KrZJjrt2SYwlUcIzZMGor47iaWruwED83qFJSQR9QXgAKqQ
```

## Unity

To set the NoesisGUI license in Unity, follow these steps:

- Click on the Unity menu option '*Tools* -> *NoesisGUI* -> *Settings*'. This will open an inspector window displaying global options for NoesisGUI.
- Alternatively, you can access the same window by navigating to '*Project Settings* -> *NoesisGUI*'.
- In the NoesisGUI settings window, locate the fields '*License Name*' and '*License Key*'.
- Enter your license information into these fields.

![LicensingImg1.png](/LicensingImg1/png.md)

## Unreal

To set the NoesisGUI license in Unreal Engine, follow these steps:

- Click on the Unreal menu option '*NoesisGUI* -> *Settings*'. This will open a window displaying global options for NoesisGUI.
- Alternatively, you can access the same window by navigating to '*Project Settings* -> *Plugins* -> *NoesisGUI*'.
- In the NoesisGUI settings window, locate the fields '*License Name*' and *License Key*'.
- Enter your license information into these fields.

![LicensingImg2.png](/LicensingImg2/png.md)