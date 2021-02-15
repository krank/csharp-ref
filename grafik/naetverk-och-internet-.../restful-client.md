# RESTful client

## Användbara nuggets

Använd NuGet Gallery för att installera följande:

* RestSharp – för att göra anrop till REST-tjänster
* Newtonsoft JSON – för att hantera JSON-data

Lägg till dessa using-statements:

```csharp
using RestSharp;
using Newtonsoft.Json;
```

## Göra en request

### RestClient – Skapa ett klientobjekt

```csharp
RestClient client = new RestClient("https://pokeapi.co/api/v2/");
```

Skapar ett klientobjekt som kommer att skicka requests till PokeAPI.

### RestRequest – Skapa ett request-objekt

Request-objekt inkluderar vilken resurs och vilka parametrar som ska skickas som en förfrågan till servern.

```csharp
// Skapar ett request-objekt för resursen pokemon/ditto.
RestRequest request = new RestRequest("pokemon/ditto");
```

```csharp
// Lägger till parametern "uid" med värdet "ANMA0000032338"
request.AddParameter("uid", "ANMA0000032338");
```

Ofta när ett API kräver att man har en API-nyckel så behöver den anges som parameter.

### Gör en Get-operation med klienten

```csharp
IRestResponse response = client.Get(request);
```

### Använda svarets innehåll som en string

```csharp
string content = response.Content;
Console.WriteLine(content);
```

### Deserialisera svarets innehåll till ett objekt

Undersök den JSON-kod man får i svaret.

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
(...)
}
```

Välj ut vilka egenskaper som är intressanta. Skapa en klass som har dessa egenskaper som publika variabler av rätt datatyp.

Detta är lättast att göra med de som inte är listor/objekt, utan som är av enkel datatyp t.ex. siffror, texter och booleska värden.

{% tabs %}
{% tab title="Pokemon.cs" %}
```csharp
class Pokemon
{
  public string name;
  public int id;
}
```
{% endtab %}
{% endtabs %}

Använd JsonConvert för att deserialisera JSON-koden från REST-svaret till ett objekt baserat på den klassen:

```csharp
Pokemon ditto = JsonConvert.DeserializeObject<Pokemon>(result);
```

Instansens variabler kommer då att ha värden hämtade från REST-tjänsten.

