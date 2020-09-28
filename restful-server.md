# RESTful server

{% hint style="danger" %}
OBSERVERA: DENNA DEL ÄR EJ FÄRDIG ENS LITEGRANN
{% endhint %}

## Enkel REST-server som svarar på GET

Börja med att skapa och förbereda projektet.

### Visual Studio Code

* Skapa projektets solution som vanligt, men välj .NET Core Web API som projekttyp istället för Console application.

### Visual Studio 2019:

* Starta Visual Studio Installer.
* Gå till Modify och Individual components.
* Leta rätt på "Web Development Tools plus .NET Core 2.1". Kryssa i, installera.
* Starta ett nytt projekt, välj ASP.NET Core Web Application som mall att utgå från.
* Skriv in namn och välj var projektet ska ligga.
* Välj API och tryck Create.
* När projektet skapats, tryck på den lilla nedåtpilen till höger om IIS Express och välj namnet på ditt projekt istället.

### Rensa bort Weather Forecast-delarna:

* Ta bort WeatherForecast.cs
* Ta bort WeatherForecastController, som ligger i Controllers-mappen.
  * LaunchSettings.json, ändra localhost till \*

