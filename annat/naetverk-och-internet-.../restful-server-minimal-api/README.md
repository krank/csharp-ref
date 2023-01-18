# RESTful server (Minimal API)\*

Nedan är instruktioner för att skapa en enkel API-server som svarar på GET-anrop.

## Skapa projektet

Skapa projektets solution som vanligt, men välj **Minimal Web API** som projekttyp istället för **Console application**.

## Ett minimalt projekt

Nedanstående är ett absolut minimalt, enkelt projekt som helt enkelt skickar "Hello World!" till den som skickar en get-request till programmet:

{% code lineNumbers="true" %}
```csharp
var app = WebApplication.Create(args);

app.UseHttpsRedirection();

// När en request kommer för "/" så svarar servern med det som 
//  returneras från GimmeHello
app.MapGet("/", GimmeHello);

app.Run();

static string GimmeHello()
{
  return "Hello World!";
}
```
{% endcode %}

## JSON-serialiserade instanser
