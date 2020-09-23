# Felsökning

Visual Studio Code är ganska nytt och inte ett lika "färdigt paket" som Visual Studio. Därför kan det ibland bli krångel, lite beroende på vad man har på sin dator i övrigt, och hur den mår. Här nedan finns några saker man kan göra för att felsöka.

## Det finns inget i Solution Explorer, jag kan inte högerklicka eller nånting

![](../../.gitbook/assets/image%20%288%29.png) 

Du har antagligen inte valt vilken mapp du ska arbeta i.

* Gå till File och Open Folder.
* Navigera till din mapp som du har för kursen \(prog 1 eller 2\).
* Tryck på "Ny mapp" och döp den nya mappen till något.
* Klicka på mappen och OK.

## Min Debug är tom!

![](../../.gitbook/assets/image%20%281%29.png) 

Testa följande:

* Starta om Visual Studio Code.
* Kolla "Output" \(View → Output\) och se om VSCode håller på och installerar OmniSharp, .NET Core Debugger och Razor Language Server. Om den håller på med det, vänta tills den är klar.
* Dubbelkolla att DotNet Core SDK och C\#-tillägget i Visual Studio Core är installerade
  * Du kan dubbelkolla att DotNet Core SD är installerat genom att öppna terminalen i Visual Studio Code och skriva "dotnet". Om du inte får något felmeddelande så är det installerat.
* Klicka på den lilla klockan längst ner till höger och se om du har en notification om att "Required assets to build and debug are missing". Om du har det, tryck "Yes".
  * Om du inte har det, testa att ta fram kommandopaletten \(F1 eller View → Command Palette\) och sök efter "Generate Assets for Build and Debug".

## Visual Studio Code säger att all min kod är fel!

Om VSCode klagar på att till och med din "using System" är fel, kolla om du har Visual Studio 2017 installerad. Om du har det, starta Visual Studio Installer och uppdatera Visual Studio.

\(Nej, jag förstår inte heller varför det funkar, men det gör det tydligen. Om du vill kan du istället avinstallera alla versioner av vanliga Visual Studio, både 2017 och 2019, och sedan ominstallera DotNet SDK\)

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

