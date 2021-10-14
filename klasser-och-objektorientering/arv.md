# Arv

När man bygger en klass som bygger på en annan klass så kallas det **arv**. Arvet innebär att subklassen får samma variabler och metoder som basklassen.

{% tabs %}
{% tab title="Character.cs" %}
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
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Hero.cs" %}
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
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Program.cs" %}
```csharp
Hero myHero = new Hero();

myHero.name = "Britt-Marie";

myHero.Hurt(3);
myHero.AddExperience(12);
```
{% endtab %}
{% endtabs %}

Hero bygger på Character, så alla instanser av Hero-klassen har egna name, hp, x och y-variabler. Dessutom har de egna kopior av Hurt-metoden, som då påverkar Hero-instansens egen hp.

Dessutom tillför Hero-klassen ett par egna variabler och en egen metod.
