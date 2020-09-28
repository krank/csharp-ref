# Polymorfism

Polymorfism inom programmering är när flera olika saker liknar varandra så pass mycket att de kan ersätta varandra, eller när man kan använda ett och samma namn för att referera till flera olika saker.

Ett exempel på detta är [metodöverlagring](grundlaeggande/egna-metoder.md#oeverlagring), där man använder samma namn på flera olika metoder, och C\# använder parametervärden för att avgöra vilken metod som ska köras.

## Polymorfism, klasser och arv

Inom objektorientering används polymorfism genom att en variabel vars datatyp är satt till en basklass kan innehålla instanser av subklasser till den basklassen.

{% tabs %}
{% tab title="Character.cs" %}
```csharp
class Character
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

characters.Add(new Hero);
```
{% endtab %}
{% endtabs %}

Ett problem med detta är att man då bara har tillgång till de publika variabler och metoder som ingår i basklassen. I exemplet ovan kan man med andra ord anropa myHero.Hurt eller characters\[0\].Hurt men man kan inte anropa AddExperience eftersom den bara finns i subklassen.

Därför är det en bra idé att tillföra så få nya metoder som behöver anropas utifrån som möjligt, när man designar subklasser som ska kunna fungera polyformt. I idealfallet ingår alltså alla metoder och variabler som ska vara åtkomliga utifrån redan i basklassen.

## Tvingad tolkning

I nödfall kan man tvinga C\# att tillfälligt tolka variabeln som en instans av subklassen:

```csharp
Hero tmpHero = (Hero)myHero;

tmpHero.AddExperience(10);
```

Eller ännu kortare:

```csharp
((Hero)myHero).AddExperience(10);
```

Det innebär dock att man riskerar felmeddelanden ifall det nu visar sig att just den instansen faktiskt inte var någon Hero-instans utan kanske en Character-instans. Därför gäller det att vara försiktig, och kontrollera att instansen som lagrats i variabeln faktiskt _är_ en instans av just den efterfrågade subklassen.

```csharp
if (h.GetType() == typeof(Hero))
{
  ((Hero)myHero).AddExperience(10);
}
```

GetType\(\) returnerar en instans av datatypen Type, som beskriver klasser. Typeof är en metod som tar emot en klass som parameter, och returnerar också en instans av datatypen Type, som beskriver den klass som angavs som parameter. Det gör att de går att jämföra med varandra.

