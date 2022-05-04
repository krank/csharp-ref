# Polymorfism \[…]

Se också [Virtual och Override](virtual-override.md).

Polymorfism inom programmering är när flera olika saker liknar varandra så pass mycket att de kan ersätta varandra, eller när man kan använda ett och samma namn för att referera till flera olika saker.

Ett exempel på detta är [metodöverlagring](../../grundlaeggande/egna-metoder.md#oeverlagring), där man använder samma namn på flera olika metoder, och C# använder parametervärden för att avgöra vilken metod som ska köras.

## Polymorfism, klasser och arv

Inom objektorientering används polymorfism genom att en variabel vars datatyp är satt till en basklass kan innehålla instanser av subklasser till den basklassen.

{% tabs %}
{% tab title="Character.cs" %}
```csharp
class Character
{
  public string Name {get; set;}
  public int Hp {get; set;} = 100;
  
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
  int Xp {get; set;} = 0;
  int Level {get; set;} = 1;
  
  public void AddExperience(int amount)
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
Character myHero = new Hero();
```
{% endtab %}
{% endtabs %}

Det här är praktiskt när man till exempel vill ha en lista med alla karaktärer i spelet:

{% tabs %}
{% tab title="Program.cs" %}
```csharp
List<Character> characters = new List<Character>();

characters.Add(new Hero());
```
{% endtab %}
{% endtabs %}

Ett problem med detta är att man då bara har tillgång till de publika variabler och metoder som ingår i basklassen. I exemplet ovan kan man med andra ord anropa myHero.Hurt eller characters\[0].Hurt men man kan inte anropa AddExperience eftersom den bara finns i subklassen.

Därför är det en bra idé att tillföra så få nya metoder som behöver anropas utifrån som möjligt, när man designar subklasser som ska kunna fungera polymorfiskt. I idealfallet ingår alltså alla metoder och variabler som ska vara åtkomliga utifrån redan i basklassen.

## Tvingad tolkning

[As](../../grundlaeggande/typkonvertering.md#as) och framför allt [Is](../../grundlaeggande/typkonvertering.md#is) ger praktiska verktyg att arbeta med polymorfa klasser. Det är användbart framför allt när subklasser till exempel lägger till nya metoder eller properties.

```csharp
foreach(Character c in characters)
{
  if (c is Hero h)
  {
    h.AddExperience(10);
  }
}
```
