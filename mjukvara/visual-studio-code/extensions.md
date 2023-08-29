# Extensions

Extensions lägger till funktioner i Visual Studio Code. I grunden är ju Code en ganska simpel kod-editor utan stöd för specifika språk.

Klicka på den här ikonen i vänstermenyn för att se extensions:

![](<../../.gitbook/assets/image (7).png>)

Där syns vilka som just nu är installerade, och man kan även söka efter nya extensions.

Om man har en länk till en extension – som de nedan – kan man helt enkelt klicka på länken, sedan "Install" och sedan låta webbäsaren öppna Visual Studio Code och installera extensionen.

{% hint style="info" %}
**TIPS:** Man kan installera extensions via terminalen/kommandotolken också:

`code --install-extension ms-dotnettools.csdevkit`

`code --install-extension codezombiech.gitignore`

`code --install-extension patcx.vscode-nuget-gallery`

`code --install-extension eliostruyf.vscode-hide-comments`
{% endhint %}

## Användbara extensions

### Grunduppsättning för C\#

* [C# Dev Kit](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csdevkit) – Get Visual Studio Code stöd för C# & underlättar projekthantering.
  * **OBS:** Gå till "IntelliCode for C# Dev Kit" som automatiskt installeras, och stäng av (tryck Disable)! Den kan vara användbar, men inte medan man lär sig!
* [gitignore](https://marketplace.visualstudio.com/items?itemName=codezombiech.gitignore) – Underlättar arbetet med git och Visual Studio Code. Om du söker efter den, se till att ta den av CodeZombie!
* [NuGet Gallery](https://marketplace.visualstudio.com/items?itemName=patcx.vscode-nuget-gallery) – Underlättar installationen av externa bibliotek och paket, t.ex. Raylib.
* [Hide Comments](https://marketplace.visualstudio.com/items?itemName=eliostruyf.vscode-hide-comments) – Gömmer alla kommentarer. Används när du presenterar din kod.
* **INAKTUELLA:**
  * [C#](https://www.google.com/url?q=https%3A%2F%2Fmarketplace.visualstudio.com%2Fitems%3FitemName%3Dms-vscode.csharp\&sa=D\&sntz=1\&usg=AFQjCNGOzgSFj14Pbd9ut66JAvh0loJsEw) – Ger Visual Studio Code stöd för C# (Installeras automatiskt med C# Dev Kit)
  * [C# Toolbox of Productivity](https://marketplace.visualstudio.com/items?itemName=RichardZampieriprog.csharp-snippet-productivity) – Lägger till en del extra användbara genvägar och funktioner, t.ex. för att skapa nya projekt och klasser. (Har slutat utvecklas, och C# Dev Kit funkar bättre)

### Bonus

* [Thunder Client](https://marketplace.visualstudio.com/items?itemName=rangav.vscode-thunder-client) – gör att man kan testa API-anrop direkt i VScode, både mot lokala servrar som man bygger själv och servrar på det lokala nätverket eller internet.
* [Auto-Using for C#](https://marketplace.visualstudio.com/items?itemName=Fudge.auto-using) – hjälper till att lägga in using-statements när det behövs, t.ex. för listor så lägger den till `using System.Collections.Generic`.
* [Roslynator](https://marketplace.visualstudio.com/items?itemName=josefpihrt-vscode.roslynator) – Ger en hel del kodförslag och hjälp.
  * Vill du ha ännu mer pedantisk "hjälp"? Använd [NuGet Gallery](../../grundlaeggande/anvaenda-bibliotek-using.md#nuget-gallery) för att lägga till StyleCop.Analyzers till ditt projekt.
* [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare) – Realtids-samarbete; flera personer kan skriva kod tillsammans samtidigt.
