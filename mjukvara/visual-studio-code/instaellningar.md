# Inställningar

Under Settings (Kugghjulet och sen Settings, eller kortkommandot Ctrl+, ) finns en hel massa användbara inställningar.

![](<../../.gitbook/assets/image (3) (2).png>)

Man kan antingen bläddra själv, eller söka efter namnet på den inställning man vill ändra.

VS Code sparar alla inställningar i en JSON-fil, där varje inställning har ett unikt namn. Om man vill kan man redigera denna JSON-fil manuellt. För att få fram den, ta fram kommandopaletten (F1) och kör **Preferences: Open User Settings (JSON)**.

## Få bort "references"

Sök efter **csharp.referencesCodeLens.enabled**, och kryssa ur "Csharp › References Code Lens: Enabled".

## Ha en standardmapp för nya projekt

### Steg 1: Hämta adressen till mappen

* Gå till Utforskaren och bläddra till mappen där du vill lägga dina projekt.

![](<../../.gitbook/assets/image (34).png>)

* Klicka i adressfältet för att kunna markera och kopiera adressen till mappen
  * Exempel: `C:\Users\krank\Documents\Programmering 1`

### Steg 2: Skriv in adressen på rätt ställe.

* Gå till Visual Studio Code.
* Ha C# Toolbox of Productivity installerad och uppdaterad.
* Gå till inställningarna.
* Sök efter **csharp-snippet-productivity.defaultFolderForProjectCreation**. Klicka på "Edit in settings.json".
* Klistra in adressen inom citattecknen efter `"csharp-snippet-productivity.defaultFolderForProjectCreation"`.
  * OBS: Dubblera alla \\
  * Exempel: `"C:\\Users\\krank\\Documents\\Programmering 1"`

![](<../../.gitbook/assets/image (35).png>)

## Visa mappar ordentligt

VS Code gillar att visa mappar "kompakt". Det betyder att den "sammanfattar" mappstrukturer i vissa fall, så att trädet under Explore blir konstigt.

> <img src="../../.gitbook/assets/image (26).png" alt="" data-size="original"> \
> _Med compact folders_

> <img src="../../.gitbook/assets/image (27).png" alt="" data-size="original"> \
> _Utan compact folders_

* För att stänga av det – sök efter **explorer.compactFolders** och kryssa ur "Explorer: Compact Folders".

## Sortera filer enligt svensk bokstavsordning

VS Code sorterar normalt sett å och ä som om de vore "a" och ö som om det vore "o".

Sök på **explorer.sortOrderLexicographicOptions** och välj "unicode" i dropdown-listan. DÅ sorteras istället å, ä och ö som de ska längst ner i listan.

## Automatiskt pusha commits

För att få VS Code att automatiskt göra en Git Push direkt efter varje Commit (se [Git](../git-and-github/) för mer info om commit och push):

Sök efter **git.postCommitCommand** och välj Push eller Sync istället för None.
