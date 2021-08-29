# Nya projekt

## Skapa nytt konsollprojekt

Se till att åtminstone C\# och C\# Toolbox-tilläggen är installerade i VSCode.

* Tryck F1 och sök/välj "C\# Toolbox: Create project".
* Project template: Console application.
* Project name: skriv något som beskriver projektet. **INGA MELLANSLAG**.
* Välj en mapp att lägga projektet i.
* Framework: 5.0.

Tryck på Create Project. Nu bör ditt nya projekt skapas och öppnas.

Du bör nu uppe i kommandopaletten få välja mellan en sln-fil och en csproj-fil. Välj sln-filen \(egentligen verkar det inte spela så stor roll\).

### De första stegen

Gå till din Program.cs.

Första gången du skapar ett nytt C\#-projekt på en ny dator, eller ifall C\#-tillägget uppdaterats, så kommer C\#-tillägget i VSCode att ladda ner OmniSharp, .NET Core Debugger och Razor Language Server. Du kan kolla i Output för att se när det är klart.

Du bör få en ruta som meddelar att "required assets to build and debug are missing" och som frågar ifall dessa assets ska läggas till. **Svara "Yes"**.

Om du inte ser den rutan:

* Klicka på den lilla klockan \(🔔\) nere i högra hörnet. Då får du upp alla notifications och kan se om du bara missade den.
* Man kan göra det manuellt också – Gå till kommandopaletten \(F1 eller Fn+F1\) och sök efter "assets" så bör du hitta en som heter ".NET: Generate Assets for Build and Debug". Välj den.

## Kompilera och köra

Börja med att gå till Debug and run-panelen, den som ser ut som en insekt på en play-knapp.  
  
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

[Se instruktionerna här.](../git-and-github/)

