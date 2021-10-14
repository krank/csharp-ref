# Static

Statiska variabler och metoder tillhör klassen istället för instanserna. Alla instanser delar alltså på en och samma variabel/metod.

## Statiska variabler

När man läser eller ändrar på en statisk variabel utifrån skriver man klassens namn, sedan en punkt och därefter variabelns namn. Inuti klassmetoder kan man alltid bara använda variabeln som vilken som helst.

{% tabs %}
{% tab title="Fighter.cs" %}
```csharp
class Fighter
{
  // En statisk slumpgenerator som alla fighters delar på
  static Random generator = new Random();
  
  private int strength;
  
  // En konstruktor där slumpgeneratorn används
  public Fighter()
  {
    strength = generator.Next(10,20);
  }
  
}
```
{% endtab %}
{% endtabs %}

## Statiska metoder

När man anropar en statisk metod skriver man klassens namn, sedan en punkt och därefter metodens namn. Inuti icke-statiska klassmetoder kan man anropa statiska metoder som om de vore vanliga metoder.

{% hint style="warning" %}
En viktig detalj är att **inuti en statisk metod** kan man **bara** anropa de metoder i samma klass som **också är statiska**. Detta eftersom metoden tillhör just klassen och inte instanserna. Detta gäller också variabler - i en statisk metod kan man bara använda statiska klassvariabler.
{% endhint %}

{% tabs %}
{% tab title="Fighter.cs" %}
```csharp
class Fighter
{
  public static string GetRandomFighterName()
  {
    /* ... */
  }
}
```
{% endtab %}
{% endtabs %}
