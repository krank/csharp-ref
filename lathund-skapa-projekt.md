# Lathund: Skapa projekt



* Starta Visual Studio Code
* File → Open folder.
  * Gå till din mapp för Programmering 2. Skapa en ny mapp. Döp den till projektets namn. Välj att öppna den.
* **SKAPA SOLUTION**
  * Solution Explorer. Högerklicka, "Create new empty solution". Döp den till projektets namn.
* **SKAPA PROJEKT**
  * När den är klar, högerklicka på din solution.
  * "Add New Project".
  * Välj rätt typ, oftast Console Application.
  * C\#.
  * Döp projektet.
  * Helt OK att ha samma namn på mappen.
* **GÖR SÅ PROJEKTET KAN KÖRAS**
  * Run \(ikonen med play-knapp och insekt\)
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
  * Source Control
  * Initialize Repository
  * Skriv in ditt första commit-meddelande och stage:a alla filer du vill ha med \(manuellt eller automatiskt\)
  * Nere i vänstra kanten av programmet, klicka på det lilla molnet \("Publish to GitHub"\)
  * Välj "Publish to GitHub public repository"
  * Om du behöver logga in eller göra något annat kommer VSCode att säga till. Följ instruktionerna.

