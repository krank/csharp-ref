# Public, private och protected

## Public

Variabler och metoder som är **publika** kan läsas av och ändras på **utifrån**.

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

Variabler och metoder som inte är publika kan inte nås utifrån – men däremot kan de fortfarande nås **inifrån** metoder som ingår i samma klass. **Privata** variabler och metoder kan bara nås från metoder i **exakt** samma klass – så inte i någon subklass som ärver från den.

Om det **inte står något** framför en klassvariabel eller klassmetod är den **automatiskt private**.

För att man ska kunna få ut värdet hos en privat variabel behöver man gå via en publik metod som returnerar dess värde. Metoden tillhör ju klassen, så _den_ får komma åt den privata variabeln. Detta är en form av [inkapsling](inkapsling-och-properties.md).

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

Fungerar som private, men metoden/variabeln kan kommas åt i klasser som _ärver_ från klassen där de deklareras.

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
