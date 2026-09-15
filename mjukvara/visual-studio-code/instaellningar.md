# Inställningar

Under Settings (Kugghjulet och sen Settings, eller kortkommandot Ctrl+, ) finns en hel massa användbara inställningar.

![](<../../.gitbook/assets/image (3) (2).png>)

Man kan antingen bläddra själv, eller söka efter namnet på den inställning man vill ändra.

Inställningarna har unika namn som man kan söka efter. Några exempel:

<details>

<summary><strong>Kör eller debugga i separat fönster</strong></summary>

I vanliga fall visas all output från koden i Visual Studio Codes egna interna terminalfönster. Det är inte idealiskt, så den här inställningen gör så att koden istället körs i ett separat terminalfönster.

Sök efter **csharp.debug.console** och ändra inställningen till "externalTerminal".

</details>

<details>

<summary><strong>Stänga av AI-grejer</strong></summary>

Kryssa i **chat.disableAIFeatures** för att stänga av AI-grejer

</details>

<details>

<summary><strong>Få bort "references"</strong></summary>

Kryssa ur **csharp.referencesCodeLens.enabled** för att slippa få "references" ovanför alla variabler.

</details>

<details>

<summary><strong>Mer kompakt/klassiskt utseende</strong></summary>

Nyligen infördes ett nytt utseende med mjukare former och annat utseende på flikar osv i VS Code. För att återgå till det gamla utseendet:

Sök efter **workbench.experimental.modernUI** och kryssa ur rutan.

</details>

<details>

<summary><strong>Färre knappar i title bar</strong></summary>

Kryssa ur **workbench.layoutControl.enabled** för att få bort de fyra knapparna som ändrar fönsterlayouten, alltså de här:

<figure><img src="../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

</details>

<details>

<summary><strong>Visa mappar ordentligt</strong></summary>

VS Code gillar att visa mappar "kompakt". Det betyder att den "sammanfattar" mappstrukturer i vissa fall, så att trädet under Explore blir konstigt.

För att stänga av det – sök efter **explorer.compactFolders** och kryssa ur "Explorer: Compact Folders".

</details>

<details>

<summary><strong>Automatiskt pusha commits</strong></summary>

För att få VS Code att automatiskt göra en Git Push direkt efter varje Commit (se [Git](../git-and-github/) för mer info om commit och push):

Sök efter **git.postCommitCommand** och välj Push eller Sync istället för None.

</details>

## settings.json

VS Code sparar alla inställningar i en [JSON-fil](../../filhantering/filformat/json.md), där varje inställning har ett unikt namn. Om man vill kan man redigera denna JSON-fil manuellt. För att få fram den, gå till Settings och tryck på ![](<../../.gitbook/assets/image (41).png>).

{% code title="settings.json" %}
```json
{
  "csharp.debug.console": "externalTerminal",
  "chat.disableAIFeatures": true,
  "csharp.referencesCodeLens.enabled": false,
  "workbench.experimental.modernUI": false,
  "workbench.layoutControl.enabled": false,
  "explorer.compactFolders": false,
  "git.postCommitCommand": "push"
}
```
{% endcode %}

