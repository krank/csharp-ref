# Visual Studio Code \[…\]

Visual Studio Code \(VS Code\) är en ny kod-editor från Microsoft som är betydligt snabbare och enklare än vanliga Visual Studio. Den funkar också bättre till många saker, även om den saknar en del av de mer avancerade verktygen som finns i det större programmet.

Ladda ner Visual Studio Code: [https://code.visualstudio.com/](https://www.google.com/url?q=https%3A%2F%2Fcode.visualstudio.com%2F&sa=D&sntz=1&usg=AFQjCNFfrd2nqbS9PitDdShdvXIIGWl04g)

För att du ska kunna skapa och kompilera C\#-projekt behöver du också Dotnet Core SDK: [https://dotnet.microsoft.com/download](https://www.google.com/url?q=https%3A%2F%2Fdotnet.microsoft.com%2Fdownload&sa=D&sntz=1&usg=AFQjCNEZyeRMV73INiktjzYkeKEh8y7vUQ)

## Användbara extensions

VS Code är väldigt modulärt. Det betyder att det finns en ganska liten "grund" och sedan lägger man till de funktioner man behöver genom att installera _extensions_.

* [C\#](https://www.google.com/url?q=https%3A%2F%2Fmarketplace.visualstudio.com%2Fitems%3FitemName%3Dms-vscode.csharp&sa=D&sntz=1&usg=AFQjCNGOzgSFj14Pbd9ut66JAvh0loJsEw) – Ger Visual Studio Code stöd för C\#
* [VSCode Solution Explorer](https://www.google.com/url?q=https%3A%2F%2Fmarketplace.visualstudio.com%2Fitems%3FitemName%3Dfernandoescolar.vscode-solution-explorer&sa=D&sntz=1&usg=AFQjCNGrjx53ssn_Mj8MSoVXhjH6YQfAig) – Ger en panel där man kan få enkel översikt över sina solutions och projekt
* [VS Sharper for C\#](https://www.google.com/url?q=https%3A%2F%2Fmarketplace.visualstudio.com%2Fitems%3FitemName%3Deservice-online.vs-sharper&sa=D&sntz=1&usg=AFQjCNFDXsmYvQKXt1e_mMjIz7bylUL2Cw) – gör det lite lättare att arbeta med C\# i VSCode
* [Auto-Using for C\#](https://marketplace.visualstudio.com/items?itemName=Fudge.auto-using) – hjälper till att lägga in using-statements när det behövs, t.ex. för listor så lägger den till `using System.Collections.Generic`.
* [gitignore](https://www.google.com/url?q=https%3A%2F%2Fmarketplace.visualstudio.com%2Fitems%3FitemName%3Dcodezombiech.gitignore&sa=D&sntz=1&usg=AFQjCNHu8aUEHuuoWIdAZQcCdvDqnSWhSQ) – Underlättar arbetet med git och Visual Studio Code. Om du söker efter den, se till att ta den av CodeZombie!
* [NuGet Gallery](https://www.google.com/url?q=https%3A%2F%2Fmarketplace.visualstudio.com%2Fitems%3FitemName%3Dpatcx.vscode-nuget-gallery&sa=D&sntz=1&usg=AFQjCNGESnjNCe20EX_KwyQS6_sTUBYv5A) – Underlättar installationen av externa bibliotek och paket, t.ex. Raylib.
* [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare) – Realtids-samarbete; flera personer kan skriva kod tillsammans samtidigt.

## Praktiska inställningar

Under Settings \(Kugghjulet och sen Settings, eller kortkommandot Ctrl+, \) finns en hel massa användbara inställningar.

### Få bort "references"

* Sök efter "lens", och kryssa ur "Csharp › References Code Lens: Enabled".

### Visa mappar ordentligt

VSCode gillar att visa mappar "kompakt". Det betyder att den "sammanfattar" mappstrukturer i vissa fall, så att trädet under Explore blir konstigt.

> ![](../../.gitbook/assets/image%20%2827%29.png)   
> _Med compact folders_

> ![](../../.gitbook/assets/image%20%2826%29.png)   
> _Utan compact folders_

* För att stänga av det – sök efter "compact" och kryssa ur "Explorer: Compact Folders".

### Automatiskt pusha commits

För att få VS Code att automatiskt göra en Git Push direkt efter varje Commit \(se [Git](../git-and-github/) för mer info om commit och push\):

Sök efter inställningen "Git: Post Push Command" och välj Push eller Sync istället för None.

