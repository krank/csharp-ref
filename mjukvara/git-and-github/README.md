# Git & GitHub

Saker som behövs:

* [Visual Studio Code](https://code.visualstudio.com/)
  * [Gitignore-extension](https://marketplace.visualstudio.com/items?itemName=codezombiech.gitignore)
* [Git-scm](https://git-scm.com/)
* Ett konto på [GitHub](https://github.com/).

## Arbeta med Git \(+GitHub\) och Visual Studio Code

### Skapa ett projekt och göra det till ett repository + koppla till GitHub \(en gång per projekt\)

* Se till att ha [git](https://git-scm.com/) installerat, och VSCode-tillägget "gitignore".
* Skapa projektet [som vanligt](../visual-studio-code/nya-projekt.md#skapa-nytt-konsollprojekt).
* Source Control → Initialize Repository.
* Tryck F1 och sök "add gitignore". Välj Visual Studio.
  * Gör samma sak igen, välj "Append" och "Visual Studio Code".
* Tryck "Publish to GitHub"
  * Längst ner till vänster, ser ut som en liten pil som pekar upp i ett moln: ![](../../.gitbook/assets/image%20%2830%29.png) 
  * Första gången: Följ instruktionerna för att knyta Visual Studio Code till github-kontot
* Välj namn för projektet, kryssa ur att projektet ska vara private om det ska lämnas in

### Commits \(då och då\)

* Gör ändringar i projektet.
* Gå till Source Control.
* \(Kryssa ur eventuella filer du inte vill ha med i committen.\)
* Fyll i en kort Summary.
* Tryck Commit \(Ctrl+Enter i Summary-rutan funkar också\).

### Push \(en gång per lektion\)

När du gjort alla commits för denna gång och t.ex. ska stänga av datorn eller lämna lektionen.

* Tryck Synchronize Changes \(längst ner till vänster\): ![](../../.gitbook/assets/image%20%2829%29.png) 

### Lämna in en Git-länk \(en gång per projekt\)

* Gå till projektsidan på github.com.
* Tryck på "Clone or download".
* Kopiera länken och lämna in. Numera kan man lägga till länkar direkt i sitt svar i Classroom!

### Göra ett projekt publikt

Om man råkat göra ett projekt privat på GitHub.com…

* Gå till projektsidan på github.com.
* Gå till "Settings".
* Bland knapparna längst ner finns "Make Public".
* Skriv in repots namn för att bekräfta.

