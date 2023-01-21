# RESTful server (Minimal API)\*

Nedan är instruktioner för att skapa en enkel API-server som svarar på GET-anrop.

## Skapa projektet

Skapa projektets solution som vanligt, men välj **Minimal Web API** som projekttyp istället för **Console application**.

## Ett minimalt projekt

Nedanstående är ett absolut minimalt, enkelt projekt som helt enkelt skickar "Hello World!" till den som skickar en get-request till programmet:

{% code lineNumbers="true" %}
```csharp
// Skapa en webbapplikation-instans
var app = WebApplication.Create(args);

// Använd HTTPS
app.UseHttpsRedirection();

// När en GET-request kommer för "/" så svarar servern med det som 
//  returneras från GimmeHello
app.MapGet("/", GimmeHello);

// Kör webbapplikationen
app.Run();

// Metoden som ska köras när någon gör en GET-request
static string GimmeHello()
{
  return "Hello World!";
}
```
{% endcode %}

## MapGet(), MapPost(), MapPut() och MapDelete()

Dessa metoder kopplar en [HTTP-metod](../rest-och-crud.md) (GET, POST, PUT eller DELETE) och en [REST-resurs](../url-er-och-rest.md#rest-resurs) till en specifik C#-metod. Detta kallas "mapping".

```csharp
app.MapGet("/pokemon/", GimmePokemon);
```

Om någon sedan gör en request till serverns adress, och requesten har metoden GET och inkluderar /pokemon/ (t.ex. **https://localhost:7174/pokemon**, så kommer det response som skickas tillbaka vara det som returneras från GimmePokemon-metoden.

MapGet kopplar till GET-requests, MapPost till POST-requests, MapPut till PUT-requests och MapDelete till DELETE-requests.

C#-metoden kan vara en statisk metod, en instansmetod eller ett [Lambda-uttryck](../../../grundlaeggande/delegates.md#lambdas).

```csharp
app.MapGet("/hello/", () => "Say hello!");
```

### Parametrar

C#-metoden kan förses med parametervärden via URL:en.

```csharp
app.MapGet("/double/{num}/", Double);

static string Double(int num)
{
  return (num * 2).ToString();
}
```

När man i exemplet ovan besöker t.ex. **https://localhost:7174/double/7** så blir det 14 som skickas tillbaka som HTTP-response.

### Returnera Objekt som JSON

Om metoden som mappas returnerar ett objekt, så kommer det objektet serialiseras till JSON innan det skickas tillbaka som ett HTTP-response.

{% code title="Hero.cs" %}
```csharp
public class Hero
{
  public string Name { get; set; }
  public int Hitpoints { get; set; }
}
```
{% endcode %}

```csharp
app.MapGet("/hero/superman/", GetSuperman);

static Hero GetSuperman()
{
  Hero h = new Hero();
  h.Name = "Superman";
  h.Hitpoints = 100;
  return h;
}
```

Resultatet om man skickar en GET-request till **/hero/superman**:

```
{
  "name": "Superman",
  "hitpoints": 100
}
```

### Skicka in nya objekt via POST/PUT och JSON

(Kommer)

## Results

För att skicka någon annan statuskod än OK, gör så att C#-metoderna returnerar Results.

```csharp
static IResult GetBatman()
{
  Hero h = new Hero();
  h.Name = "Batman";
  h.Hitpoints = 30;
  return Results.Ok(h);
}
```

Det finns en hel del olika HTTP-statuskoder, till exempel:

* **Results.Ok** – allt gick bra.
* **Results.NotFound** – det du frågade efter fanns inte.
* **Results.BadRequest** – den request du skickade kunde inte tolkas, eller innehöll fel.

## Komma åt servern från andra datorer

Normalt sett kan servern inte kommas åt från andra datorer än den den körs på; den kallas "localhost". För att också kunna komma åt den från andra datorer på samma nätverk, lägg till en URL med wildcard (\*):

```csharp
app.Urls.Add("http://localhost:3000");
app.Urls.Add("http://*:3000");
```

Ovanstående gör att man kan komma åt servern både genom url:en localhost:3000 (på den lokala datorn) och genom att skriva datorns ip-nummer följt av 3000 (på den lokala datorn eller på någonnannan dator på samma nätverk).
