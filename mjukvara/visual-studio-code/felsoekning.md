# Felsökning

Visual Studio Code är ganska nytt och inte ett lika "färdigt paket" som Visual Studio. Därför kan det ibland bli krångel, lite beroende på vad man har på sin dator i övrigt, och hur den mår. Här nedan finns några saker man kan göra för att felsöka.

## Allmänna saker att testa

* Starta om Visual Studio Code.
* Kolla "Output" \(View → Output\) och se om VSCode håller på och installerar OmniSharp, .NET Core Debugger och Razor Language Server. Om den håller på med det, vänta tills den är klar.
* Dubbelkolla att [DotNet Core SDK](https://dotnet.microsoft.com/download) och [C\#-tillägget i Visual Studio Core](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) är installerade
  * Du kan dubbelkolla att en tillräckligt ny version av DotNet Core SDK är installerat genom att öppna terminalen i Visual Studio Code och skriva "`dotnet --version`". Du bör få en siffra med en version, och du bör ha minst version 3.1.
* Testa F1 \(eller Fn+F1\) för att få fram kommandopaletten, och kör "OmniSharp: Restart OmniSharp".
* Kolla om du har Visual Studio 2017 installerad. Om du har det, starta Visual Studio Installer och uppdatera Visual Studio.
  * Eller avinstallera Visual Studio helt.

## The nuclear option

Om ingenting fungerar så kan du testa en fullständig ominstallation.

* Avinstallera \(alla versioner av\) DotNet Core SDK
* Avinstallera \(alla versioner av\) Visual Studio
* Avinstallera Visual Studio Code
* Öppna Utforskaren \(Windows + E\)
  * Gå till din användarmapp
  * Visa → Dolda objekt
  * Ta bort mappen .vscode

Installera sedan DotNet Core SDK och Visual Studio Code igen, och de tillägg du vill ha.

## Det finns inget i Solution Explorer, jag kan inte högerklicka eller nånting

![](../../.gitbook/assets/image%20%288%29.png) 

Du har antagligen inte valt vilken mapp du ska arbeta i.

* Gå till File och Open Folder.
* Navigera till din mapp som du har för kursen \(prog 1 eller 2\).
* Tryck på "Ny mapp" och döp den nya mappen till något.
* Klicka på mappen och OK.

## Min Debug är tom!

![](../../.gitbook/assets/image%20%281%29.png) 

* Klicka på den lilla **klockan längst ner till höger** och se om du har en notification om att "Required assets to build and debug are missing". Om du har det, tryck "Yes".
  * Om du inte har det, testa att ta fram kommandopaletten \(F1 eller View → Command Palette\) och sök efter "**Generate Assets for Build and Debug**".

## Jag får ingen kodkomplettering i Unity!

Ladda ner och installera [.NET Framework 4.7.1](https://dotnet.microsoft.com/download/dotnet-framework/thank-you/net471-developer-pack-offline-installer).

