# Ojektorienterade mönster

## Simpla

### Passera som argument

Eftersom klasser fungerar som datatyper, kan man skicka med dem som parametervärden. Och eftersom de är referenstyper så behöver man inte returnera dem.

{% code title="Fighter.cs" %}
```csharp
public class Fighter
{
  public void Attack(Enemy target)
  {
    target.Hurt(10);
  }
}
```
{% endcode %}

{% code title="Enemy.cs" %}
```csharp
public class Enemy
{
  private int hp = 100;
  public void Hurt(int amount)
  {
    hp -= amount; 
  }
}
```
{% endcode %}

```csharp
Fighter fabio = new();
Enemy egon = new();
fabio.Attack(egon);
```

Det här gör att objekten kan påverka varandra _direkt_, istället för att behöva ha kod som flyttar data mellan dem.

Det här fungerar såklart också med [polymorfism](../klasser-och-objektorientering/polymorfism/) (i exempelkoden kan man skicka in även andra sorters enemies), så man kan använda både [abstrakta klasser](../klasser-och-objektorientering/abstract.md) och [interfaces](../klasser-och-objektorientering/interface.md).

### Lokal referens

Om ett objekt ofta behöver referera till ett annat, och det andra objektet sällan byts ut, så kan man lagra referensen i en klassvariabel.

{% code title="Level.cs" %}
```csharp
public class Level
{
  public bool IsGround(int z, int y)
  {
    // kod...
    return true;
  }
}
```
{% endcode %}

```csharp
public class Player
{
  private Level _level;
  private int _x, _y;
  
  public Player(Level level)
  {
    _level = level;
  }
  
  public voidd Update()
  {
    if (_level.IsGround(_x, _y)
    {
      // kod...
    }
  }
}
```

## Factory pattern

## Observer pattern

## Singleton pattern

## Component pattern
