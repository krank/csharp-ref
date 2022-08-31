# Lathund: Skapa projekt



* Starta Visual Studio Code
* **SKAPA PROJEKTET**
  * F1 → C# Toolbox: Create Project.
  * Template – oftast Console Application.
  * Projektnamnet – inga mellanslag, börja inte med siffror.
  * Location: Välj mapp för projektet.
  * Solution name: Genereras automatiskt från projektnamnet.
  * Framework: 5.0 eller 6.0
  * Tryck "Create Project"
  * När dialogrutan dyker upp och frågar, svara "Yes" på att du vill skapa filerna som krävs. Om den inte dyker upp, tryck på "Run & Debug" och klicka på den nedre knappen ("Generate assets…").
  * Dubbelkolla så OmniSharp går igång (den lilla eldsflamman nere till vänster).
  * Öppna csproj-filen och ta bort (eller kommentera bort) raden med `<Nullable>`.
  * (I Dotnet 5 och tidigare: plocka bort Namespace, class och Main-kodblocken som automatiskt läggs till i program.cs)
* **GÖR SÅ PROJEKTET KAN KÖRAS**
  * Run (ikonen med play-knapp och insekt)
    * Ser du inget här: Klicka på "Generate assets for build and debug".
  * Kugghjulet för att öppna launch.json
  * Leta rätt på "console": "internalConsole". Bör vara på rad 17.
  * Byt ut "internalConsole" mot "externalTerminal"
  * Spara och stäng launch.json
* **SKAPA GIT-REPOSITORY**
  * F1 → Add gitignore
    * Välj Visual Studio
  * Gå till Source Control
  * Initialize Repository
  * Skriv in ditt första commit-meddelande och stage:a alla filer du vill ha med (manuellt eller automatiskt)
  * Klicka på "Publish Branch".
  * Välj "Publish to GitHub **public** repository"
  * Om du behöver logga in eller göra något annat kommer VSCode att säga till. Följ instruktionerna.
