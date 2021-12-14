# JSON-serialisering

JSON är Javascript Object Notation, så för den som är van vid Javascript kanske det ser bekant ut.

[Här hittar du Microsofts officiella dokumentation.](https://docs.microsoft.com/en-us/dotnet/standard/serialization/system-text-json-how-to)

## Bibliotek

Lägg till detta using-statement:

```csharp
using System.Text.Json;
```

## Klassdesign

Klassen vars instanser ska kunna serialiseras/deserialiseras måste vara public.

```csharp
public class Pokemon
{
  public string name {get; set;}
  public int id {get; set;}
  public bool is_default {get; set;}
}
```

Det är också enbart publika variabler samt properties med publika getters och setters som serialiseras.

Om du ska deserialisera JSON-kod som du får från något annat ställe och inte designat själv, så behöver du vara noga med att matcha namnet på dina publika variabler/[properties ](../../klasser-och-objektorientering/inkapsling-och-properties.md#properties)mot JSON-kodens. Serialiseringsprocessen är normalt känslig vad gäller stora och små bokstäver, men du kan ändra på detta (rekommenderas!).

{% tabs %}
{% tab title="Spaceship.cs" %}
```csharp
public class Pokemon
{
  public string name {get; set;}
  public int id {get; set;}
  public bool is_default {get; set;}
}
```
{% endtab %}

{% tab title="Ditto.json" %}
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
{% endtab %}
{% endtabs %}

## JsonSerializer.Serialize<>()

Används för att serialisera ett objekt till en JSON-string.

```csharp
  Pokemon poke = new Pokemon()
  {
    Name = "Ditto",
    Id = 132,
    IsDefault = true,
    Species = new PokemonSpecies() {
      Name = "ditto",
      Url = "https://pokeapi.co/api/v2/pokemon-species/132/"
    }
  };

  string json = JsonSerializer.Serialize<Pokemon>(poke);
```

Denna string kan sedan lagras i en textfil eller t.ex. skickas som svar på ett [REST](../../grafik/naetverk-och-internet-.../restful-server/)-anrop.

{% hint style="info" %}
OBS: Det finns inget sätt att automatiskt förvandla namnen på properties till snake\_case, vilket ju ofta används i JSON. Vill du serialisera med snake\_case så får du med andra ord använda JsonPropertyName-attributet.
{% endhint %}

## JsonSerializer.Deserialize<>()

Används för att deserialisera ett objekt från en JSON-string.

```csharp
// jsonString innehåller json-data. Den kan t.ex. läsas in från en json-fil
// eller hämtas från en REST-server.
Pokemon ditto = JsonSerializer.Deserialize<Pokemon>(jsonString);
```

### Små och stora bokstäver

Properties ska döpas med stor bokstav i C#, men i json döps egenskaper nästan alltid med liten bokstav. Deserialize är känsligt för skillnader mellan stora och små bokstäver. Det går att stänga av den känsligheten:

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true
};

// Nu kan property-namnen i Pokemon.cs döpas med stor bokstav
Pokemon ditto = JsonSerializer.Deserialize<Pokemon>(jsonString, options);
```

## Attribut

Mer om attribut [här](../../klasser-och-objektorientering/attribut.md).

{% hint style="info" %}
**OBS:** dessa kräver att du inkluderar `System.Text.Json.Serialization`.
{% endhint %}

### \[JsonIgnore]

Används för att se till så att en variabel eller property på C#-sidan inte serialiseras till JSON.

```javascript
using System.Text.Json.Serialization;

public class Pokemon
{
  public string Name {get; set;}
  public bool IsDefault {get; set;}
  
  [JsonIgnore]
  public int CurrentHp {get; set;}
}
```

### \[JsonPropertyName()]

Med attributet `[JsonPropertyName()]` kan man bestämma att en C#-klass' property ska matchas mot ett JSON-värde med annat namn.

{% tabs %}
{% tab title="Pokemon.cs" %}
```csharp
using System.Text.Json.Serialization;

class Pokemon
{
  public string Name {get; set;}
  public int Id {get; set;}
  
  [JsonPropertyName("is_default")]
  public bool IsDefault {get; set;}
}
```
{% endtab %}
{% endtabs %}

## Deserialisering av listor

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

För att deserialisera dessa, skapa helt enkelt publika [listor ](../../grundlaeggande/listor-och-arrayer.md#list)i klassen.

{% tabs %}
{% tab title="Pokemon.cs" %}
```csharp
class Pokemon
{
  [JsonPropertyName("name")]
  public string Name {get; set;}
  
  [JsonPropertyName("forms")]
  public List<string> Forms {get; set;}
}
```
{% endtab %}
{% endtabs %}

## Deserialisering av objekt i flera led

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
  [JsonPropertyName("name")]
  public string Name {get; set;}
  
  [JsonPropertyName("url")]
  public string Url {get; set;}
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Pokemon.cs" %}
```csharp
class Pokemon
{
  [JsonPropertyName("name")]
  public string Name {get; set;}
  
  [JsonPropertyName("species")]
  public PokemonSpecies Species {get; set;}
}
```
{% endtab %}
{% endtabs %}
