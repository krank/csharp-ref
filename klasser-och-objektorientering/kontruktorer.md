# Konstruktorer

En konstruktor är en metod som anropas automatiskt när en instans skapas. Den skrivs in i klassen som en publik metod utan returtyp och med samma namn som klassen.

{% tabs %}
{% tab title="Fighter.cs" %}
```csharp
class Fighter
{
  private string name = "";
  private int strength = 0;
  private Random generator = new Random();

  public Fighter()
  {
    strength = generator.Next(5,10);
  }
}
```
{% endtab %}
{% endtabs %}

När man skapar en instans av klassen Fighter så ges instansen nu enligt koden ovan ett slumpat strength-värde.

## Parametrar och konstruktorer

Precis som andra metoder kan konstruktorer ta emot en eller flera parametrar. Det brukar till exempel användas som ett snabbt och enkelt sätt att skjuta in information som ska lagras i instansens variabler.

{% tabs %}
{% tab title="Fighter.cs" %}
```csharp
class Fighter
{
  private string name = "";
  private int strength = 0;
  private Random generator = new Random();

  public Fighter(string n)
  {
    name = n;
    strength = generator.Next(5,10);
  }
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Program.cs" %}
```csharp
Fighter heroFighter = new Fighter("Britta-Lena");
Fighter enemyFighter = new Fighter("Börje");
```
{% endtab %}
{% endtabs %}

## Konstruktorer i arv

När en basklass och en subklass har varsin konstruktor så kommer _båda_ konstruktorerna att köras när en instans av subklassen skapas. Först körs basklassens konstruktor, därefter körs subklassens konstruktor.

{% tabs %}
{% tab title="Character.cs" %}
```csharp
class Character
{
  int hp;
  string name = "";
  public Character()
  {
    hp = 100;
  }
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Thief.cs" %}
```csharp
class Thief: Character
{
  public Thief()
  {
    name = "Thief";
    hp = 20;
  }
}
```
{% endtab %}
{% endtabs %}

I exemplet ovan kommer med andra ord en instans av Thief först 100 i hp när basklassens konstruktor körs, och sedan ändras hp till 20 och name till "Thief".

## Konstruktorer med parametrar i arv

Etersom både basklassens och subklassens konstruktor körs, så betyder det att om basklassens konstruktor kräver ett parametervärde så måste det värdet stoppas in på något sätt även när det är subklassen som instansieras.

I exemplet nedan måste Character-klassens konstruktor få ett string-värde som parameter.

{% tabs %}
{% tab title="Character.cs" %}
```csharp
class Character
{
  public string name;
  public int hp = 100;

  public Character(string n)
  {
    name = n;
  }
}
```
{% endtab %}
{% endtabs %}

För att ange vilket värde som ska skickas till basklassens konstruktor så använder man base\(\).

{% tabs %}
{% tab title="Hero.cs" %}
```csharp
class Hero : Character
{
  public Hero(string na, int h) : base(na)
  {
    hp = h;
  }
}
```
{% endtab %}
{% endtabs %}

Här tar subklassens konstruktor emot två parametrar - na och h - och skickar vidare värdet som lagras i parametern na till basklassens konstruktor.

