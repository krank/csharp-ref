# Raylib setup

Skapa ett nytt konsollprojekt som vanligt.

* Ta fram kommandopaletten (F1) och sök efter NuGet Gallery (som du såklart [behöver ha installerat](https://marketplace.visualstudio.com/items?itemName=patcx.vscode-nuget-gallery)).
* I galleriet, sök efter Raylib. Välj senaste versionen av "Raylib\_cs".
* Kryssa i ditt projekt, klicka Install.
* Om du vill använda bilder eller andra filer i ditt spel, se till att [konfigurera din csproj för att hantera resursfiler](../../filhantering/resursfiler.md#loesning-3-kopiera-filerna-automatiskt-till-malmappen).

### Inkludera Raylib <a href="#h.p_juwpvkt-mpln" id="h.p_juwpvkt-mpln"></a>

{% hint style="warning" %}
**OBSERVERA:** För att du ska kunna använda Raylib så måste du skriva in följande bland dina using-rader högst upp i programfilen:

```csharp
using Raylib_cs;
```
{% endhint %}
