# Public, private och protected

## Public

Variabler och metoder som är publika kan läsas av och ändras på från andra delar av koden.

{% tabs %}
{% tab title="Fighter.cs" %}
```csharp
class Fighter
{
  public string Name = "";
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Program.cs" %}
```csharp
Fighter hero = new Fighter();
hero.Name = "Laban";
```
{% endtab %}
{% endtabs %}

## Private

Variabler och metoder som är publika kan läsas av och ändras på från andra delar av koden. Skriver man varken private, public eller protected framför en variabel eller metod i en klass så kommer den att bli private.

För att man ska kunna få ut värdet hos en privat variabel behöver man gå via en publik metod som returnerar dess värde. Metoden tillhör ju klassen, så _den_ får komma åt den privata variabeln

{% tabs %}
{% tab title="Fighter.cs" %}
```csharp
class Fighter
{
  private string name = "";
  
  public string GetName()
  {
    return name;
  }
}
```
{% endtab %}
{% endtabs %}

## Protected

Fungerar som private, men kan kommas åt i klasser som ärver från klassen där de deklareras.

{% tabs %}
{% tab title="Fighter.cs" %}
```csharp
class Fighter
{
  protected string name = "";
  
  public string GetName()
  {
    return name;
  }
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="StrongFighter.cs" %}
```csharp
class StrongFighter : Fighter
{
  public string GetName()
  {
    // kan använda name trots att variabeln tillhör basklassen
    return name + " The Strong";
  }
}
```
{% endtab %}
{% endtabs %}
