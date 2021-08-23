# Kompilering och publicering

## Kompilering och debug-körning

Medan du arbetar med projektet så skapar du s.k. "debug builds", särskilda versioner av programmets exe- och dll-filer som fungerar bra ihop med vscode och dess olika verktyg.

Genom att trycka F5 skapas en mapp som heter "bin", och i den finns en mapp som heter "Debug". Där finns ytterligare en undermapp som heter "net5.0" \(om du använder .NET Core 5\). I den mappen läggs dina tillfälliga debug builds.

Så snart .net skapat din debug build så körs den, så normalt märker du inte ens att det blir exe- eller dll-filer – du ser bara koden, och sedan att programmet körs.

## Publicering

För att skapa en version av ditt program som är lämpligt att distribuera till andra, gå till terminalen i Visual Studio Code \(eller någon annan terminal; se till att vara i samma mapp som SLN-filen\).

Skriv detta, och tryck enter:

```text
dotnet publish -c Release
```

Resultatet bör se ut ungefär såhär:

![](.gitbook/assets/image%20%2831%29.png)

I ditt projekt bör du nu ha en mapp som heter "bin" och i den finns en mapp som heter "Release". Där finns ytterligare en undermapp som heter "net5.0" \(om du använder .NET Core 5\), och under den finns en som heter "publish". Filerna i publish-mappen är de du kan distribuera till andra.

![](.gitbook/assets/image%20%2832%29.png) 

### Överkurs: standalone

Vill man ha en exe-fil som inte kräver att man har .NET Core 5 installerat, så kan skriva man såhär när man publicerar \(om det nu är windows 10 64-bitarsversionen man bygger till\):

```markup
dotnet publish -r win-x64 -c Release -p:PublishSingleFile=true -p:PublishTrimmed=true --self-contained true
```

Då kommer filerna i publish-mappen fortfarande vara ganska få, men exe-filen kommer att vara betydligt större. Mappstrukturen blir också lite annorlunda, men det bör inte vara svårt att hitta rätt filer att publicera.

Vill man verkligen bara ha _en_ exe-fil så kan man lägga till ytterligare en parameter:

```markup
dotnet publish -r win-x64 -c Release -p:PublishSingleFile=true -p:PublishTrimmed=true -p:IncludeNativeLibrariesForSelfExtract=true --self-contained true
```

