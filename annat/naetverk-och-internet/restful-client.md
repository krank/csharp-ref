# RESTful client

## Snabbstart

Nedanstående exempelkod skapar ett klientobjekt och ett requestobjekt, skickar requesten genom klienten för att få ett response, och deserialiserar response-objektets text till en instans av Pokemon-klassen.

```csharp
using RestSharp;
using System.Text.Json;

RestClient client = new RestClient("https://pokeapi.co/api/v2/");
RestRequest request = new RestRequest("pokemon/ditto");
RestResponse response = client.GetAsync(request).Result;
Pokemon p = JsonSerializer.Deserialize<Pokemon>(response.Content);

```

## RestSharp

RestSharp är ett bibliotek som förenklar skickandet av Rest-requests till en RESTful API-server.

Använd [NuGet Gallery](../../grundlaeggande/anvaenda-bibliotek-using.md#nuget-gallery) för att installera RestSharp. Lägg till detta using-statement högst upp:

```csharp
using RestSharp;
```

## RestClient

En klass som sköter kommunikationen med API-servern.

```csharp
RestClient client = new RestClient("https://pokeapi.co/api/v2/");
```

Skapar ett klientobjekt som kommer att skicka requests till PokeAPI.

### GetAsync, PostAsync, PutAsync, DelAsync

Dessa metoder används för att skicka en request till en RESTful API-server och leverera resultatet.

Välj rätt metod:

<table><thead><tr><th width="160.33333333333331">Metod</th><th width="139">HTTP-metod</th><th width="245.66666666666669">Aktivitet</th></tr></thead><tbody><tr><td>PostAsync</td><td>POST</td><td>Skapa en ny resurs</td></tr><tr><td>GetAsync</td><td>GET</td><td>Hämta data om en resurs</td></tr><tr><td>PutAsync</td><td>PUT</td><td>Ändra en resurs</td></tr><tr><td>DelAsync</td><td>DELETE</td><td>Ta bort en resurs</td></tr></tbody></table>

Metoderna tar alla emot en [RestRequest](restful-client.md#restrequest)-instans och returnerar en [Task](../threading/task.md). Denna Task ger sedan ifrån sig, som Result, ett [RestResponse](restful-client.md#restresponse).

```csharp
RestResponse response = client.GetAsync(request).Result;
```

GetAsync är, som namnet antyder, en [asynkron metod](../threading/task.md). Med andra ord går det att använda await istället för .Result om man är i en asynkron metod.

```csharp
async string GetPokemon(string pokemonName)
{
  Task<RestResponse> task = client.GetAsync(request);
  
  // gör något annat medan klienten hämtar resultatet
  
  await task;
  return task.Result;
}
```

## RestRequest

Instanser av RestRequest används för att skicka requests till servern, via till exempel [GetAsync](restful-client.md#get).

Request-objekt inkluderar vilken resurs som ska efterfrågas.

```csharp
// Skapar ett request-objekt för resursen pokemon/ditto.
RestRequest request = new RestRequest("pokemon/ditto");
```

### AddParameter

I vissa API:er kan man lägga till ytterligare parametrar till sin request för att t.ex. skicka med en API-nyckel eller begränsa hur många resultat man får.

```csharp
// Lägger till parametern "apikey" med värdet "DEMO_KEY"
request.AddParameter("apikey", "DEMO_KEY");
```

### AddJsonBody

I vissa fall – t.ex. när man ska göra en PUT eller en POST – vill man skicka med ett objekt. Om API:et då förväntar sig JSON-data så kan man enklast använda AddJsonBody för att få automatisk serialisering.

```csharp
Fighter f = new Fighter();
request.AddJsonBody(f);
```

## RestResponse

Som svar på den request man skickat till API-servern får man ett RestResponse-objekt.

```csharp
RestResponse response = client.GetAsync(request).Result;
```

### StatusCode

I response-objektet ingår en StatusCode. Dess datatyp är en [Enum](../../grundlaeggande/datatyper/enum.md) som heter HttpStatusCode och finns i biblioteket System.Net. Dess möjliga värden är alla existerande, definierade statuskoder från HTTP-standarden. Till exempel Ok och NotFound.

```csharp
  if (response.StatusCode == System.Net.HttpStatusCode.NotFound)
  {
    Console.WriteLine("Not found!");
  }
```

För att slippa skriva System.Net hela tiden kan du använda ett using-statement högst upp i filen:

```csharp
using System.Net;
```

### Content

Content är en string som innehåller textsvaret på den request som skickades till servern.

```csharp
string jsonText = response.Content;
Console.WriteLine(jsonText);
```

Ofta är Content JSON eller XML-format, och då kan informationen deserialiseras till ett objekt antingen via [JSON-deserialisering](../../filhantering/serialisering-.../json-serialisering.md#jsonserializer.deserialize-less-than-greater-than) eller [XML-deserialisering](../../filhantering/serialisering-.../xml-serialisering.md#deserialize).

## Kommunicera med en lokal server

Om du vill anropa en lokal server (localhost) men får ett felmeddelande om ett SSL-fel, så kan du kör denna kod i terminalen för att det ska fungera:

```powershell
dotnet dev-certs https --trust
```

## Öppna databas-API:er

* [Pokemon API](https://pokeapi.co/)
* [Digimon API](https://digimon-api.herokuapp.com/)
* [Star Wars API](https://swapi.py4e.com/)
* [Star Trek API](http://stapi.co/)
* Steam-API
  * [Skaffa en API-nyckel](https://steamcommunity.com/dev/apikey)
  * [Dokumentation](https://partner.steamgames.com/doc/webapi)
* [Marvel API](https://developer.marvel.com/)
