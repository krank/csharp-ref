# Abstract

## Abstrakta klasser

En abstrakt klass kan aldrig instansieras, utan kan bara användas som basklass för arv.

{% tabs %}
{% tab title="Character.cs" %}
```csharp
abstract class Character
{
  public string name;
  public int hp = 100;

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

## Abstrakta metoder

Den huvudsakliga anledningen till att göra en basklass abstrakt är för att man vill kunna använda sig av abstrakta metoder. En abstrakt metod saknar kod, och måste overridas i alla subklasser. Det är med andra ord ett sätt att tvinga de som skapar subklasser att bygga egna versioner av den metoden.

Abstrakta metoder fungerar bäst i de fall där det inte finns någon lämplig "standardversion" av metoden som kan ingå i basklassen

{% tabs %}
{% tab title="Character.cs" %}
```csharp
abstract class Character
{
  public string name;
  public int hp = 100;
  public int strength = 5;
  public int level = 1;
  public int xp = 0;
  public string[] attacks = {"Kick", "Punch"}

  public abstract void LevelUp();
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Warrior.cs" %}
```csharp
class Warrior : Character
{
  public override void LevelUp()
  {
    level = xp / 10;
    if (level == 3)
    {
      attacks = new string[] { "Kick", "Punch", "Bite" };
    }
  }
}
```
{% endtab %}
{% endtabs %}

I exemplet ovan är det alltså tänkt att metoden LevelUp ska anropas för att ge karaktärer ny level, ifall de fått tillräckligt med xp. I och med att olika karaktärer ska ha olika progression baserat på vilken klass de tillhör \(t.ex. Warrior\) så kan man låta LevelUp-metoden vara abstrakt och ha en egen implementation för varje subklass.

