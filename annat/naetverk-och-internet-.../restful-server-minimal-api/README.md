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

Dessa metoder kopplar en [HTTP-metod](../rest-och-crud.md) (GET, POST, PUT eller DELETE) och en [REST-resurs](../url-er-och-rest.md#rest-resurs) till en specifik C#-metod.

```csharp
app.MapGet("/pokemon/", GimmePokemon);
```

Om någon sedan gör en request till serverns adress, och requesten har metoden GET och inkluderar /pokemon/ (t.ex. https://localhost:7174/pokemon, så kommer det response som skickas tillbaka vara det som returneras från GimmePokemon-metoden.

MapGet kopplar till GET-requests, MapPost till POST-requests, MapPut till PUT-requests och MapDelete till DELETE-requests.

C#-metoden kan vara en statisk metod, en instansmetod eller ett [Lambda-uttryck](../../../grundlaeggande/delegates.md#lambdas).

### Parametrar

### Returnera JSON-serialiserade instanser

## Results

