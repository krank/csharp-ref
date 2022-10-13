# Arv

När man bygger en klass som bygger på en annan klass så kallas det **arv**. Arvet innebär att subklassen får samma variabler och metoder som basklassen.

{% code title="Character.cs" lineNumbers="true" %}
```csharp
class Character
{
  public string name;
  public int hp = 100;
  public int x = 0;
  public int y = 0;

  public void Hurt(int amount)
  {
    hp -= amount;
  }
}
```
{% endcode %}

{% code title="Hero.cs" lineNumbers="true" %}
```csharp
class Hero: Character
{
  int xp = 0;
  int level = 1;
  
  public AddExperience(int amount)
  {
    xp += amount;
    level = 1 + xp / 10;
  }
}
```
{% endcode %}

{% code title="Program.cs" lineNumbers="true" %}
```csharp
Hero myHero = new Hero();

myHero.name = "Britt-Marie";

myHero.Hurt(3);
myHero.AddExperience(12);
```
{% endcode %}

Hero bygger på Character, så alla instanser av Hero-klassen har egna name, hp, x och y-variabler. Dessutom har de egna kopior av Hurt-metoden, som då påverkar Hero-instansens egen hp.

Dessutom tillför Hero-klassen ett par egna variabler och en egen metod.
