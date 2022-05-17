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
  * När det nya fönstret öppnas, välj sln-filen.
  * När dialogrutan dyker upp och frågar, svara "Yes" på att du vill skapa filerna som krävs.
  * Dubbelkolla så OmniSharp går igång (den lilla eldsflamman nere till vänster).
  * Om du vill: plocka bort Namespace, class och Main-kodblocken som automatiskt läggs till i dotnet 5-projekt och tidigare.
* **GÖR SÅ PROJEKTET KAN KÖRAS**
  * Run (ikonen med play-knapp och insekt)
    * Ser du inget här: F1 → ".NET: Generate Assets for Build and Debug"
  * Kugghjulet för att öppna launch.json
  * Leta rätt på "console": "internalConsole". Bör vara på rad 17.
  * Byt ut "internalConsole" mot "externalTerminal"
  * Spara och stäng launch.json
* **SKAPA GIT-REPOSITORY**
  * F1 → Add gitignore
    * Välj Visual Studio
  * F1 → Add gitignore
    * Välj Visual Studio Code
    * Välj Append
  * Gå till Source Control
  * Initialize Repository
  * Skriv in ditt första commit-meddelande och stage:a alla filer du vill ha med (manuellt eller automatiskt)
  * Nere i vänstra kanten av programmet, klicka på det lilla molnet ("Publish to GitHub")
  * Välj "Publish to GitHub public repository"
  * Om du behöver logga in eller göra något annat kommer VSCode att säga till. Följ instruktionerna.
