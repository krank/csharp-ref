# Lathund: Skapa projekt

* Starta Visual Studio Code
* **SKAPA PROJEKTET**
  * Stäng nuvarande projekt: File → Close folder
  * Explorer → Create .NET Project (C# Dev Kit)
  * Välj "Console App"
  * Skapa och välj en mapp att skapa projektet i.
  * Välj ett namn på projektet.
    * Namnet bör vara i formen PlatformGame (inga mellanslag, stor bokstav i början av varje ord)
  * Öppna csproj-filen och ta bort (eller kommentera bort) raden med `<Nullable>`.
* **GÖR SÅ PROJEKTET KAN KÖRAS**
  * Gå till "run and debug" (**Ctrl+Shift+D**, eller ikonen med play-knapp och insekt).
  * Klicka på "**create a launch.json file**". Välj "C#".
    * Se till så att du [**ställt in så kod körs i ett separat fönster**](mjukvara/visual-studio-code/instaellningar.md#koer-debugga-i-external-terminal).
  * Eller: Klicka på "**Show all automatic debug configurations**" och välj **C#** och sedan ditt projekt.
  * Alternativt: **F1 → .NET: Generate Assets for Build and Debug**
    * I den launch.json som skapas, byt ut `internalConsole` mot `externalTerminal`.
* **SKAPA GIT-REPOSITORY**
  * F1 → Add gitignore
    * Välj Visual Studio
  * Gå till Source Control
  * Initialize Repository
  * Skriv in ditt första commit-meddelande och stage:a alla filer du vill ha med (manuellt eller automatiskt)
  * Klicka på "Publish Branch".
  * Välj "Publish to GitHub **public** repository"
  * Om du behöver logga in eller göra något annat kommer VSCode att säga till. Följ instruktionerna.

## INAKTUELLT

**Skapa projektet**

* F1 → C# Toolbox: Create Project.
* Template – oftast Console Application.
* Projektnamnet – inga mellanslag, börja inte med siffror.
* Location: Välj mapp för projektet.
* Solution name: Genereras automatiskt från projektnamnet.
* Framework: 5.0 eller senare
* Tryck "Create Project"
* När dialogrutan dyker upp och frågar, svara "Yes" på att du vill skapa filerna som krävs. Om den inte dyker upp, tryck på "Run & Debug" och klicka på den nedre knappen ("Generate assets…").
* Dubbelkolla så OmniSharp går igång (den lilla eldsflamman nere till vänster).
