# RESTful client

Använd NuGet Gallery för att installera **RestSharp**.

Lägg till detta using-statement:

```csharp
using RestSharp;
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

Denna string kan sedan [deserialiseras till objekt](../../filhantering/serialisering-.../json-serialisering.md).

### Svarets status-kod

I response-objektet finns också en StatusCode. Dess datatyp är en [Enum](../../grundlaeggande/datatyper/enum.md) som heter HttpStatusCode och finns i System.Net. Dess möjliga värden är alla existerande, definierade statuskoder från HTTP-standarden. Till exempel Ok och NotFound.

```csharp
  if (response.StatusCode == System.Net.HttpStatusCode.NotFound)
  {
    Console.WriteLine("Not found!");
  }
```

## API-nycklar

I de flesta fall där API:er kräver API-nycklar anges de som parametrar i requesten.

## Öppna databas-API:er

* [Pokemon API](https://pokeapi.co)
* [Digimon API](https://digimon-api.herokuapp.com)
* [Star Wars API](https://swapi.dev)
* [Star Trek API](http://stapi.co)
* Steam-API
  * [Skaffa en API-nyckel](https://steamcommunity.com/dev/apikey)
  * [Dokumentation](https://partner.steamgames.com/doc/webapi)
* [Marvel API](https://developer.marvel.com)
* [Superhero API](https://superheroapi.com)
