# Models

{% hint style="danger" %}
OBSERVERA: DENNA DEL ÄR INTE FÄRDIG
{% endhint %}

Models, eller modeller, är helt enkelt klasser som används av en REST-server för att beskriva information.

## Modellklasser

Alla egenskaper som ska returneras av API:t måste vara publika [properties](../inkapsling-och-properties.md#properties).

{% tabs %}
{% tab title="Pokemon.cs" %}
```csharp
public class Pokemon
{
  public string Name {get; set;}
}
```
{% endtab %}
{% endtabs %}

## Returnera JSON-serialiserade instanser

För att en \[HttpGet\]-metod ska returnera en JSON-serialiserad version av en instans, behövs två saker: 

* När man deklarerar metoden säger man att den ska returnera ActionResult&lt;Something&gt;, där Something är namnet på klassen vars instanser ska serialiseras.
* När man kör Ok, så lägger man in en instans av den klassen inom parenteserna.

{% tabs %}
{% tab title="PokemonController.cs" %}
```csharp
namespace WebApplication1.Controllers
{
  [Route("api/[controller]")]
  [ApiController]
  public class PokemonController : ControllerBase
  {
    [HttpGet]
    public ActionResult<Pokemon> Get()
    {
      Pokemon p = new Pokemon();
      p.Name = "Pikachu";

      return Ok(p);
    }
  }
}
```
{% endtab %}
{% endtabs %}

Resultatet av ovanstående blir att följande JSON-kod skickas med i HTTP-response-bodyn:

```javascript
{
    "name": "Pikachu"
}
```

## Listor

