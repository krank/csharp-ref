# Git & GitHub

Saker som behövs:

* Visual Studio Code
  * Gitignore-extension
* Git-scm
* Ett konto på GitHub.

## Arbeta med Git \(+GitHub\) och Visual Studio Code

### Välj namn & mail för lokala git \(en gång per dator\)

Öppna en kommandoprompt \(eller PowerShell\)

```text
git config --global user.name DittNamn
git config --global user.email youremail@address.com
```

Använd den mailadress som du registrerade dig med på GitHub.

{% hint style="info" %}
Dessa används **bara** för att identifiera dig för andra som tittar på ditt arbete, dina uppladdningar etc.
{% endhint %}

### Skapa ett projekt och göra det till ett repository + koppla till GitHub \(en gång per projekt\)

* Se till att ha git installerat, och VSCode-tillägget "gitignore".
* Skapa projektet [som vanligt](../visual-studio-code/nya-projekt.md#skapa-nytt-konsollprojekt).
* Tryck F1 och sök "add gitignore". Välj Visual Studio.
  * Gör samma sak igen, välj "Append" och "Visual Studio Code".
* Source Control → Publish to GitHub
  * Första gången: Följ instruktionerna för att knyta Visual Studio Code till github-kontot
* Välj namn för projektet, kryssa ur att projektet ska vara private om det ska lämnas in

### Commits \(då och då\)

* Gör ändringar i projektet.
* Gå till Source Control.
* Kryssa ur eventuella filer du inte vill ha med i committen.
* Fyll i en kort Summary.
* Tryck Commit.

### Push \(en gång per lektion\)

När du gjort alla commits för denna gång och t.ex. ska stänga av datorn eller lämna lektionen.

* Gå till Source Control
* Tryck Synchronize Changes \(längst ner, ser ut som två pilar som går runt i en cirkel\)

### Lämna in en Git-länk \(en gång per projekt\)

* Gå till projektsidan på github.com.
* Tryck på "Clone or download".
* Kopiera länken och lämna in. Numera kan man lägga till länkar direkt i ens svar i Classroom!

### Göra ett projekt publikt

Om man råkat göra ett projekt privat på GitHub.com…

* Gå till projektsidan på github.com.
* Gå till "Settings".
* Bland knapparna längst ner finns "Make Public".
* Skriv in repots namn för att bekräfta.

