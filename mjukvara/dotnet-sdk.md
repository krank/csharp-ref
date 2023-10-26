# Dotnet SDK\*

För att du ska kunna skapa och kompilera C#-projekt behövs .NET SDK; ladda ner från [https://dotnet.microsoft.com/download](https://www.google.com/url?q=https%3A%2F%2Fdotnet.microsoft.com%2Fdownload\&sa=D\&sntz=1\&usg=AFQjCNEZyeRMV73INiktjzYkeKEh8y7vUQ) eller använd winget:

```powershell
winget install Microsoft.DotNet.SDK.7
```

När du installerat; öppna terminalen / powershell och skriv:

```
dotnet --list-sdks
```

Nu bör du få en lista med de versioner av .NET SDK som är installerade.

## MacOS

Ta reda på ifall din Mac kör Intel eller Apple Silicon (M1/M2).

Gå till [https://dotnet.microsoft.com/download](https://www.google.com/url?q=https%3A%2F%2Fdotnet.microsoft.com%2Fdownload\&sa=D\&sntz=1\&usg=AFQjCNEZyeRMV73INiktjzYkeKEh8y7vUQ) och välj rätt version att ladda ner.

Kör installationsprogrammet och skriv in lösenordet när det efterfrågas.

När du installerat: Se till så att Terminalen inte är öppen (stäng den isf). Öppna den. Skriv:

```
dotnet --list-sdks
```

Nu bör du få en lista med de versioner av .NET SDK som är installerade.

Om du har Homebrew installerat kan du också installera dotnet med:

```
brew install --cask dotnet-sdk
```

### Saker att testa om det inte funkar\*

* /usr/local/share/dotnet/dotnet – funkar det?
* echo $path för att se ifall /usr/local/share/dotnet finns med
  * Om inte: cd /etc/paths.d, nano dotnet, lägg in /usr/local/share/dotnet, Ctrl+x för att avsluta
