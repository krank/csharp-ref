# JSON-serialisering

JSON-serialisering och deserialisering följer samma principer som [serialisering och deserialisering av XML.](xml-serialisering.md) Man omvandlar alltså objekt till JSON-kod eller tvärtom. JSON är Javascript Object Notation, så för den som är van vid Javascript kanske det ser bekant ut.

## Bibliotek för enkel deserialisering

Använd NuGet Gallery för att installera **Newtonsoft JSON**.

Lägg till detta using-statement:

```csharp
using Newtonsoft.JSON;
```

## Deserialisering av JSON

### Förberedelser

Utgå från den JSON-kod du ska deserialisera.

```javascript
{
  "form_name": "",
  "form_names": [],
  "form_order": 1,
  "id": 132,
  "is_battle_only": false,
  "is_default": true,
  "is_mega": false,
  "name": "ditto",
  "names": [],
  "order": 198, 
  // (...)
}
```

Skapa en publik klass som har publika variabler som motsvarar de egenskaper du är intresserad av.

{% tabs %}
{% tab title="Pokemon.cs" %}
```csharp
class Pokemon
{
  public string name;
  public int id;
  public bool is_default;
}
```
{% endtab %}
{% endtabs %}

### DeserializeObject

Används för att deserialisera ett objekt från en JSON-string

```csharp
Pokemon ditto = JsonConvert.DeserializeObject<Pokemon>(jsonString);
```

### Deserialisering av objekt i flera led

Ibland beskriver JSON-kod objekt som innehåller andra objekt.

```javascript
{
  "name": "ditto",
  "species":
  {
    "name": "ditto",
    "url": "https://pokeapi.co/api/v2/pokemon-species/132/"
  }
}
```

För att deserialisera dessa, skapa klasser som beskriver de inre objekten.

{% tabs %}
{% tab title="PokemonSpecies.cs" %}
```csharp
class PokemonSpecies
{
  public string name;
  public string url;
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Pokemon.cs" %}
```csharp
class Pokemon
{
  public string name;
  public PokemonSpecies species  
}
```
{% endtab %}
{% endtabs %}

### Deserialisering av listor

Ibland beskriver JSON-kod listor av objekt eller värden. De kännetecknas av att ge omges av hakparenteser `[]`.

```javascript
{
  "name": "ditto",
  "forms":
  [
    0: "Ditto"
    1: "Exempel"
  ]
}
```

För att deserialisera dessa, skapa helt enkelt publika [listor ](../grundlaeggande/listor-och-arrayer.md#list)i klassen.

{% tabs %}
{% tab title="Pokemon.cs" %}
```csharp
class Pokemon
{
  public string name;
  public List<string> forms;
}
```
{% endtab %}
{% endtabs %}

## Serialisering till JSON

\[INTE KLART\]



