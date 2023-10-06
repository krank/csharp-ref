# WinUI\*

(Under uppbyggnad)

* dotnet new install VijayAnand.WinUITemplates
* Windows App SDK
  * [https://learn.microsoft.com/en-us/windows/apps/windows-app-sdk/downloads](https://learn.microsoft.com/en-us/windows/apps/windows-app-sdk/downloads)
* dotnet new winui -n MyApp

```xml
<WindowsPackageType>None</WindowsPackageType>
<EnableMsixTooling>true</EnableMsixTooling>
<PublishProfile>win10-$(Platform).pubxml</PublishProfile>
```

* XAML
