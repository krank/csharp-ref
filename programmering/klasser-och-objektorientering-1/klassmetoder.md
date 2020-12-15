# Klassmetoder

Det går utmärkt att lägga in metoder i klasser. De anropas då genom att man skriver instansens namn följt av metodens namn, och lägger in parametrar och hanterar returneringar som vanligt.

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

{% tabs %}
{% tab title="Program.cs" %}
```csharp
Fighter f1 = new Fighter();

string n = f1.GetName();
Console.WriteLine(n);
```
{% endtab %}
{% endtabs %}

När en metod som ingår i en klass vill använda en variabel som ingår i samma klass så kan den göra detta genom att använda dess namn rakt av. Man behöver alltså inte skriva instansens namn.

Om man vill vara tydlig med att man använder en intern klassvariabel så kan man skriva this. framför.

{% tabs %}
{% tab title="Fighter.cs" %}
```csharp
class Fighter
{
  private string name = "";
  
  public void WriteName()
  {
    Console.WriteLine(this.name);
  }
}
```
{% endtab %}
{% endtabs %}

