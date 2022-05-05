# Inkapsling och properties

Inkapsling innebär egentligen inte nödvändigtvis någon ny kod, utan är ett grundläggande tankesätt:

* **Exponera så lite som möjligt.**

Det här innebär att man undviker att ha variabler som är direkt tillgängliga utanför klassen - i princip ska inga variabler vara public, utan de ska alla vara private eller protected.

Istället används metoder för att läsa av och ändra på variablerna.

{% tabs %}
{% tab title="Character.cs" %}
```csharp
class Character
{
  private int hp = 100;

  public void SetHp(int newHp)
  {
    hp = newHp;
  }

  public int GetHp()
  {
    return hp;
  }  

}
```
{% endtab %}
{% endtabs %}

I exemplet ovan kan man fortfarande få tag i karaktärers hp utifrån, och även bestämma nya värden, men man måste gå via GetHp och SetHp. Den här sortens metoder, som används för att direkt läsa av eller bestämma en variabels värde, kallas _getters_ och _setters_.

En fördel med det här är att man kan välja att en variabel t.ex. enbart ska kunna läsas av - inte ändras utifrån. Då skapar man helt enkelt bara en getter och ingen setter.

En annan finess är att man får mer kontroll över vilka värden som ges till en variabel. I exemplet nedan hindras till exempel hp-värdet från att bli lägre än 0.

{% tabs %}
{% tab title="Character.cs" %}
```csharp
class Character
{
  private int hp = 100;

  public void SetHp(int newHp)
  {
    hp = Math.Max(newHp, 0);
  }
  
  public int GetHp()
  {
    return hp;
  }
}
```
{% endtab %}
{% endtabs %}

## Properties

Properties, även kallade **egenskaper**, fungerar som ett slags variabler med inbyggda getters och setters.

{% tabs %}
{% tab title="Character.cs" %}
```csharp
class Character
{
  private int hp = 100;

  public int Hitpoints {
    get
    {
      return hp;
    }
    set
    {
      hp = Math.Max(value, 0);
    }
  }
}
```
{% endtab %}
{% endtabs %}

Fördelen med att använda properties är att de kan anropas och användas som om de vore variabler:

{% tabs %}
{% tab title="Program.cs" %}
```csharp
haracter cha = new Character();

// Propertyns setter anropas automatiskt, och value sätts till 80.
cha.Hitpoints = 80; 

// Propertyns getter anropas automatiskt, 
// och returnerar värdet av den privata variabeln hp.
Console.WriteLine(cha.Hitpoints);
```
{% endtab %}
{% endtabs %}

## Auto-implementerade properties

Om man inte vill lägga in någon extra logik i en property så kan man deklarera den på följande vis:

{% tabs %}
{% tab title="Character.cs" %}
```csharp
class Character
{
  public int Hitpoints{ get; set; }
}
```
{% endtab %}
{% endtabs %}

Det här innebär att man blir av med den fördel properties ger jämfört med publika variabler, men å andra sidan blir det lätt att senare bygga ut propertyn till en fullvärdig sådan. På det här viset behöver man med andra ord inte i efterhand byta ut en publik variabel mot en property när man senare kommer på att man trots allt ville ha lite logik.

## Properties med värden som bara får läsas, inte skrivas

Ett användningsområde för automatiskt implementerade properties är s.k. read only-värden. Säg t.ex. att vi vill att karaktärens hitpoints ska kunna läsas, men inte ändras, utifrån. Då skriver man så här:

```csharp
class Character
{
  public int Hitpoints{ get; private set; }
}
```

Det innebär att propertyns setter bara kan anropas från andra av klassens metoder.
