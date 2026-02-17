# Factory pattern\*

Genom att skapa en _fabrik_ som konstruerar objekt istället för att använda new() så måste man ändra på färre ställen ifall man senare vill ändra på exakt vilken klass (eller subklass) objekten ska tillhöra.

<details>

<summary>Anledningar att använda Factory Pattern</summary>

* En factory kan hålla reda på övergripande information som behöver finnas kvar mellan skapandet av olika instanser, t.ex. om instanserna ska numreras.
* En factory gör att man kan återanvända komponenter, t.ex. om man vill att alla fiender ska ha samma komponent för att renderas ut till skärmen, samma textur etc. men man vill undvika att göra dessa static.
* En factory innebär ökad decoupling – koden som skapar och kör fabrikens kod behöver inte känna till existensen av någon av de klasser fabriken faktiskt skapar instanser av. Återanvänder man fabriken på olika ställen i koden blir det fortfarande bara ett ställe man behöver ändra, om man vill byta ut vilka objekt som skapas.

</details>

### Exempel

{% code title="Enemy.cs" %}
```csharp
public abstract class Enemy
{
  public string Name { get; set; }
  public abstract int Attack();
}
```
{% endcode %}

{% code title="Goomba.cs" %}
```csharp
public class Goomba : Enemy
{
  public Goomba() => Name = "Goomba";
  public override int Attack() => 6;
}
```
{% endcode %}

{% code title="Fireflower.cs" %}
```csharp
public class Fireflower : Enemy
{
  public Fireflower() =>Name = "Fireflower";
  public override int Attack() => 2;
}
```
{% endcode %}

{% code title="EnemyFactory.cs" %}
```csharp
public class EnemyFactory
{
  public Enemy Make()
  {
    if (Random.Shared.Next(2) == 0)
    {
      return new Goomba();
    }
    else
    {
      return new Fireflower();
    }
  }
}
```
{% endcode %}

{% code title="Program.cs" %}
```csharp
EnemyFactory factory = new();c#

Enemy e = factory.Make();
```
{% endcode %}

## Abstrakta factories\*
