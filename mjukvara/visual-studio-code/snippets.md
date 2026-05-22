# Snippets

Snippets är ett slags "genvägar" som gör det lättare att skriva kod snabbt. En snippet fungerar genom att man skriver ett par tecken och sedan väljer rätt snippet hur autocomplete-listan.

Några inbyggda snippets:

* cw = System.Console.WriteLine()
* if = en if-sats
* while = en while-loop
* for = en for-loop
* try = ett try-catch-block
* ctor = en konstruktor
* prop = en property

<img src="../../.gitbook/assets/image (6).png" alt="" data-size="original">&#x20;

<img src="../../.gitbook/assets/image (7) (1).png" alt="" data-size="original">&#x20;

## Lägga till egna snippets

Man kan skapa egna snippets. Man går då till File, Preferences och User Snippets. Där väljer man det språk man vill skapa snippets för. Då öppnas en json-fil där du kan skriva in dina snippets.

```javascript
{
  "Readline": {
      "prefix": "cre",
      "body": "Console.ReadLine()",
      "description": "Inserts a console readline"
  },
  "Writeline":{
    "prefix": "cw",
    "body": "Console.WriteLine(\"$0\");",
    "description": "Inserts a console writeline"
  }
}
```

"Readline" och "Writeline" är namnen på de två snippets som deklareras ovan.

**Prefixen** är de saker man kan skriva för att aktivera dem.

**Bodyn** är det som infogas.

$0 betyder att det är där textmarkören hamnar när man använt snippeten.

Allt du behöver göra sedan är att spara filen.

Man kan läsa mer om att skriva egna snippets [här](https://www.google.com/url?q=https%3A%2F%2Fcode.visualstudio.com%2Fdocs%2Feditor%2Fuserdefinedsnippets\&sa=D\&sntz=1\&usg=AFQjCNHxi86ymlDUghJiBvyTVgMRy2aJsg).

## Exempel-snippetfiler

### C\#

{% code title="csharp.json" expandable="true" %}
```json
{
  "Readline": {
    "prefix": "cre",
    "body": "Console.ReadLine();"
  },
  "Writeline": {
    "prefix": "cw",
    "body": "Console.WriteLine($0);",
    "description": "Inserts a console writeline"
  },
  "Clear": {
    "prefix": "cc",
    "body": "Console.Clear();",
    "description": "Inserts a console clear"
  },
  "Random integer": {
    "prefix": "rnd",
    "body": "Random.Shared.Next($0);",
    "description": "Inserts a random next int"
  },
  "Raylib-boilerplate": {
    "prefix": "rayl",
    "body": [
      "using Raylib_cs;\n",
      "Raylib.InitWindow(${1:800}, ${2:600}, \"${3:Title}\");",
      "Raylib.SetTargetFPS(60);\n",
      "while (!Raylib.WindowShouldClose())",
      "{",
      "  $0\n",
      "  Raylib.BeginDrawing();",
      "  Raylib.ClearBackground(Color.White);",
      "  Raylib.EndDrawing();",
      "}"
    ]
  },
  "For-nested": {
    "prefix": "forn",
    "body": [
      "for (int y = 0; y < $1; y++)",
      "{",
      "  for (int x = 0; x < $2; x++)",
      "  {",
      "    $0",
      "  }",
      "}"
    ]
  }
}
```
{% endcode %}

### XML (för csproj)

De här gör det enkelt att använda [resursfiler](../../filhantering/resursfiler.md).

{% code title="xml.json" expandable="true" %}
```json
{
  "Include content": {
    "prefix": "include",
    "body": "<Content Include=\"$0\" CopyToOutputDirectory=\"Always\"/>",
  },
  "Item group": {
    "prefix": "ig",
    "body": [
      "<ItemGroup>",
      "  $0",
      "</ItemGroup>"
    ]
  }
}
```
{% endcode %}
