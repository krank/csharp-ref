# RESTful server

{% hint style="danger" %}
OBSERVERA: DENNA DEL ÄR EJ FÄRDIG ENS LITEGRANN
{% endhint %}

Nedan är instruktioner för att skapa en enkel API-server som svarar på GET-anrop.

## Skapa projektet

Skapa projektets solution som vanligt, men välj .NET Core Web API som projekttyp istället för Console application.

### Att skapa projektet i Visual Studio 2019

* Starta Visual Studio Installer.
* Gå till Modify och Individual components.
* Leta rätt på "Web Development Tools plus .NET Core 2.1". Kryssa i, installera.
* Starta ett nytt projekt, välj ASP.NET Core Web Application som mall att utgå från.
* Skriv in namn och välj var projektet ska ligga.
* Välj API och tryck Create.
* När projektet skapats, tryck på den lilla nedåtpilen till höger om IIS Express och välj namnet på ditt projekt istället.

### Rensa bort Weather Forecast-delarna

* Ta bort WeatherForecast.cs
* Ta bort WeatherForecastController, som ligger i Controllers-mappen.

## Controller

Skapa en ny klass i Controllers-mappen. Döp den till SomethingController. Du kan byta ut "Something" mot något annat om du vill.

```csharp
using Microsoft.AspNetCore.Mvc;

[Route("api/[controller]")]
[ApiController]
public class SomethingController : ControllerBase
{
  [HttpGet]
  public ActionResult Get()
  {
    return Ok("Hej");
  }
}
```

Route och ApiController är decorators. De talar om att den här klassen är en API-controller och att den ska kopplas till url:en api/Something. \[controller\] i Routen byts alltså ut automatiskt mot det som står innan Controller i klassens namn.

HttpGet är också en decorator, som talar om att metoden Get ska anropas när någon försöker hämta data från controllern \(via url:en\).

ActionResult är en klass som tillhandahålls av .Net och innehåller allt sådant som ett server-svar brukar behova innehålla.

Ok är en metod som returnerar ett färdigt ActionResult med HTTP-koden "ok". Resultatets meddelande blir det som anges som det första parametervärdet, i det här fallet alltså "hej".

## Köra och testa servern

### Gör så servern kan nås från andra datorer \(behöver göras 1 gång\)

* I Properties-mappen, öppna LaunchSettings.json
* Let rätt på "applicationUrl" en bit ner. Inte den som ligger i \[iissettings\], utan den som ligger kring rad 25.
* Ändra localhost till \*
* Ändra också "launchBrowser" till false.

![](../.gitbook/assets/image%20%2825%29.png)

### Starta servern

* Tryck på F5 som vanligt.

### Titta på API:et i en webbläsare.

* Starta t.ex. Chrome medan servern körs.
* Gå till `https://localhost:5001/api/Something`

