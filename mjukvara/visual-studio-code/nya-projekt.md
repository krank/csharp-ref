# Nya projekt

## Skapa nytt konsollprojekt

Se till att åtminstone C\# och Solution Explorer-tilläggen är installerade i VSCode.

Börja med att gå till mappen där du vill ha ditt projekt, via File → Open folder.

**Skapa alltid en ny mapp om du startar ett nytt projekt.**

Välj sedan en av metoderna nedan.

### Metod 1 \(med solution\):

* Gå till Solution explorer.
* Högerklicka, välj "Create new empty solution". Ge din solution ett namn. Svara "Yes" på att du vill skapa templates-mapp.
* Högerklicka på din nya solution, välj "Add new project".
* Välj "Console application" och "C\#".
* Ge projektet ett namn. Det kan vara samma namn som din solution.
* Välj mappnamn för projektet. Det kan vara samma namn som projektet.

### Metod 2 \(utan solution\):

* Tryck F1 \(eller Fn+F1\) för att få fram kommandopaletten.
* Sök efter, och kör, "Add new project".
* Välj "Console application" och "C\#".
* Ge projektet ett namn. Det kan vara samma namn som din solution.
* Välj mappnamn för projektet. Det kan vara samma namn som projektet.

### Metod 3 \(utan solution\):

* Gå till terminalen \(Högerklicka i mappvyn → Open in Terminal.
* Skriv, i terminalen, "dotnet new console" och tryck enter.

### Oavsett metod:

Gå till din Program.cs.

Första gången du skapar ett nytt C\#-projekt på en ny dator så kommer C\#-tillägget i VSCode att ladda ner OmniSharp, .NET Core Debugger och Razor Language Server. Du kan kolla i Output för att se när det är klart.

Du bör få en ruta som meddelar att "required assets to build and debug are missing" och som frågar ifall dessa assets ska läggas till. **Svara "Yes"**.

Om du inte ser den rutan:

* Klicka på den lilla klockan \(🔔\) nere i högra hörnet. Då får du upp alla notifications och kan se om du bara missade den.
* Man kan göra det manuellt också – Gå till kommandopaletten \(F eller Fn+F1\) och sök efter "assets" så bör du hitta en som heter ".NET: Generate Assets for Build and Debug". Välj den.

## Kompilera och köra

Börja med att gå till Debug and run-panelen, den som ser ut som en insekt med ett kryss på.  
  
![](../../.gitbook/assets/image%20%283%29.png) 

Tryck på kugghjulet. Då öppnas config-filen för projektet.

Kring rad 17 bör det stå såhär:

```text
"console": "internalConsole",
```

Ändra så att det istället står såhär:

```text
"console": "externalTerminal",
```

Det behöver du bara göra en gång per projekt.

Nu kan du helt enkelt trycka på Play-knappen uppe vid "Debug and run".

Eller trycka på Debug → Start debugging.

Eller bara trycka F5.

## Koppla projektet till Git

Se instruktionerna här. \(Länk kommer\)

