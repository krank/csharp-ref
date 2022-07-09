# Visual Studio Code \[…]

[Nya projekt](nya-projekt.md) | [Debugging](debugging.md) | [Snabbkommandon](snabbkommandon.md) | [Snippets](snippets.md) | [Felsökning](felsoekning.md)

Visual Studio Code (VS Code) är en ny kod-editor från Microsoft som är betydligt snabbare och enklare än vanliga Visual Studio. Den funkar också bättre till många saker, även om den saknar en del av de mer avancerade verktygen som finns i det större programmet.

Ladda ner Visual Studio Code: [https://code.visualstudio.com/](https://www.google.com/url?q=https%3A%2F%2Fcode.visualstudio.com%2F\&sa=D\&sntz=1\&usg=AFQjCNFfrd2nqbS9PitDdShdvXIIGWl04g)

För att du ska kunna skapa och kompilera C#-projekt behöver du också Dotnet Core SDK: [https://dotnet.microsoft.com/download](https://www.google.com/url?q=https%3A%2F%2Fdotnet.microsoft.com%2Fdownload\&sa=D\&sntz=1\&usg=AFQjCNEZyeRMV73INiktjzYkeKEh8y7vUQ)

## Användbara extensions

VS Code är väldigt modulärt. Det betyder att det finns en ganska liten "grund" och sedan lägger man till de funktioner man behöver genom att installera _extensions_.

**Grunduppsättning för C#:**

* [C#](https://www.google.com/url?q=https%3A%2F%2Fmarketplace.visualstudio.com%2Fitems%3FitemName%3Dms-vscode.csharp\&sa=D\&sntz=1\&usg=AFQjCNGOzgSFj14Pbd9ut66JAvh0loJsEw) – Ger Visual Studio Code stöd för C#
* [C# Toolbox of Productivity](https://marketplace.visualstudio.com/items?itemName=RichardZampieriprog.csharp-snippet-productivity) – Lägger till en del extra användbara genvägar och funktioner, t.ex. för att skapa nya projekt och klasser.
* [gitignore](https://www.google.com/url?q=https%3A%2F%2Fmarketplace.visualstudio.com%2Fitems%3FitemName%3Dcodezombiech.gitignore\&sa=D\&sntz=1\&usg=AFQjCNHu8aUEHuuoWIdAZQcCdvDqnSWhSQ) – Underlättar arbetet med git och Visual Studio Code. Om du söker efter den, se till att ta den av CodeZombie!
* [NuGet Gallery](https://www.google.com/url?q=https%3A%2F%2Fmarketplace.visualstudio.com%2Fitems%3FitemName%3Dpatcx.vscode-nuget-gallery\&sa=D\&sntz=1\&usg=AFQjCNGESnjNCe20EX\_KwyQS6\_sTUBYv5A) – Underlättar installationen av externa bibliotek och paket, t.ex. Raylib.

**Bonus:**

* [Thunder Client](https://marketplace.visualstudio.com/items?itemName=rangav.vscode-thunder-client) – gör att man kan testa API-anrop direkt i VScode, både mot lokala servrar som man bygger själv och servrar på det lokala nätverket eller internet.
* [Auto-Using for C#](https://marketplace.visualstudio.com/items?itemName=Fudge.auto-using) – hjälper till att lägga in using-statements när det behövs, t.ex. för listor så lägger den till `using System.Collections.Generic`.
* [Roslynator](https://marketplace.visualstudio.com/items?itemName=josefpihrt-vscode.roslynator) – Ger en hel del kodförslag och hjälp.
  * Vill du ha ännu mer pedantisk "hjälp"? Använd [NuGet Gallery](../../grundlaeggande/anvaenda-bibliotek-using.md#nuget-gallery) för att lägga till StyleCop.Analyzers till ditt projekt.
* [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare) – Realtids-samarbete; flera personer kan skriva kod tillsammans samtidigt.

## Praktiska inställningar

Under Settings (Kugghjulet och sen Settings, eller kortkommandot Ctrl+, ) finns en hel massa användbara inställningar.

### Få bort "references"

* Sök efter "lens", och kryssa ur "Csharp › References Code Lens: Enabled".

### Ha en standardmapp för nya projekt

**Steg 1: Hämta adressen till mappen**

* Gå till Utforskaren och bläddra till mappen där du vill lägga dina projekt.

![](<../../.gitbook/assets/image (34).png>)

* Klicka i adressfältet för att kunna markera och kopiera adressen till mappen
  * Exempel: `C:\Users\krank\Documents\Programmering 1`

**Steg 2: Skriv in adressen på rätt ställe.**

* Gå till Visual Studio Code.
* Ha C# Toolbox of Productivity installerad och uppdaterad.
* Gå till inställningarna.
* Sök efter "Default Folder For Project Creation". Klicka på "Edit in settings.json".
* Klistra in adressen inom citattecknen efter `"csharp-snippet-productivity.defaultFolderForProjectCreation"`.
  * OBS: Dubblera alla \\
  * Exempel: `"C:\\Users\\krank\\Documents\\Programmering 1"`

![](<../../.gitbook/assets/image (35).png>)

### Visa mappar ordentligt

VSCode gillar att visa mappar "kompakt". Det betyder att den "sammanfattar" mappstrukturer i vissa fall, så att trädet under Explore blir konstigt.

> <img src="../../.gitbook/assets/image (26).png" alt="" data-size="original"> \
> _Med compact folders_

> <img src="../../.gitbook/assets/image (27).png" alt="" data-size="original"> \
> _Utan compact folders_

* För att stänga av det – sök efter "compact" och kryssa ur "Explorer: Compact Folders".

### Automatiskt pusha commits

För att få VS Code att automatiskt göra en Git Push direkt efter varje Commit (se [Git](../git-and-github/) för mer info om commit och push):

Sök efter inställningen "Git: Post Push Command" och välj Push eller Sync istället för None.
