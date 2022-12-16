# Inställningar

Under Settings (Kugghjulet och sen Settings, eller kortkommandot Ctrl+, ) finns en hel massa användbara inställningar.

![](<../../.gitbook/assets/image (3).png>)

## Få bort "references"

* Sök efter "lens", och kryssa ur "Csharp › References Code Lens: Enabled".

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
* Sök efter "Default Folder For Project Creation". Klicka på "Edit in settings.json".
* Klistra in adressen inom citattecknen efter `"csharp-snippet-productivity.defaultFolderForProjectCreation"`.
  * OBS: Dubblera alla \\
  * Exempel: `"C:\\Users\\krank\\Documents\\Programmering 1"`

![](<../../.gitbook/assets/image (35).png>)

## Visa mappar ordentligt

VSCode gillar att visa mappar "kompakt". Det betyder att den "sammanfattar" mappstrukturer i vissa fall, så att trädet under Explore blir konstigt.

> <img src="../../.gitbook/assets/image (26).png" alt="" data-size="original"> \
> _Med compact folders_

> <img src="../../.gitbook/assets/image (27).png" alt="" data-size="original"> \
> _Utan compact folders_

* För att stänga av det – sök efter "compact" och kryssa ur "Explorer: Compact Folders".

## Automatiskt pusha commits

För att få VS Code att automatiskt göra en Git Push direkt efter varje Commit (se [Git](../git-and-github/) för mer info om commit och push):

Sök efter inställningen "Git: Post Push Command" och välj Push eller Sync istället för None.
