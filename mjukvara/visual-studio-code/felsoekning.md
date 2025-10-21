# Felsökning

Visual Studio Code är ganska nytt och inte ett lika "färdigt paket" som Visual Studio. Därför kan det ibland bli krångel, lite beroende på vad man har på sin dator i övrigt, och hur den mår. Här nedan finns några saker man kan göra för att felsöka.

## Allmänna saker att testa

* Starta om Visual Studio Code.
* Uppdatera Visual Studio Code.
* Kolla om du har Visual Studio 2017 eller 2019 installerad. Om du har det, starta Visual Studio Installer och _uppdatera_ Visual Studio.
  * Eller avinstallera Visual Studio 2017/2019 helt.
* Dubbelkolla att [DotNet Core SDK](https://dotnet.microsoft.com/download) är installerat
  * Du kan dubbelkolla att en tillräckligt ny version av DotNet Core SDK är installerat genom att öppna terminalen i Visual Studio Code och skriva "`dotnet --version`". Du bör få en siffra med en version, och du bör ha minst version 9.

## The nuclear option

Om ingenting fungerar så kan du testa en fullständig ominstallation.

* Avinstallera (alla versioner av) DotNet Core SDK
* Avinstallera (alla versioner av) Visual Studio
* Avinstallera Visual Studio Code
* Öppna Utforskaren (Windows + E)
  * Gå till din användarmapp
  * Visa → Dolda objekt
  * Ta bort mappen .vscode

Installera sedan DotNet Core SDK och Visual Studio Code igen, och de tillägg du vill ha.

## Jag får ingen kodkomplettering i Unity!

Ladda ner och installera [.NET Framework 4.7.1](https://dotnet.microsoft.com/download/dotnet-framework/thank-you/net471-developer-pack-offline-installer).
