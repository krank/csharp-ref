# Snippets

Snippets är ett slags "genvägar" som gör det lättare att skriva kod snabbt. En snippet fungerar genom att man skriver ett par tecken och sedan väljer rätt snippet hur autocomplete-listan.

Några inbyggda snippets:

* cw = System.Console.WriteLine\(\)
* if = en if-sats
* while = en while-loop
* for = en for-loop
* try = ett try-catch-block
* ctor = en konstruktor
* prop = en property

![](../../.gitbook/assets/image%20%286%29.png) 

![](../../.gitbook/assets/image%20%2810%29.png) 

## Lägga till egna snippets

Man kan skapa egna snippets. Man går då till File, Preferences och User Snippets. Där väljer man det språk man vill skapa snippets för. Då öppnas en json-fil där du kan skriva in dina snippets.

```javascript
{
  "Readline": {
      "prefix": ["cre", "readline"],
      "body": "Console.ReadLine()",
      "description": "Inserts a console readline"
  },
  "Hello": {
      "prefix": "hello",
      "body": "Console.WriteLine(\"Hello, World\")",
      "description": "Inserts a nice greeting"
  }
}
```

"Readline" och "Hello" är namnen på de två snippets som deklareras ovan.

**Prefixen** är de saker man kan skriva för att aktivera dem.

**Bodyn** är det som infogas.

Allt du behöver göra sedan är att spara filen.

Man kan läsa mer om att skriva egna snippets [här](https://www.google.com/url?q=https%3A%2F%2Fcode.visualstudio.com%2Fdocs%2Feditor%2Fuserdefinedsnippets&sa=D&sntz=1&usg=AFQjCNHxi86ymlDUghJiBvyTVgMRy2aJsg).

