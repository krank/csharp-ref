# Klasser och instanser

Klasser är ett sätt att klumpa ihop variabler och metoder som hör till samma "sak" i ett spel eller ett program. De gör det lättare att felsöka och lättare att hålla god struktur.

Man kan betrakta en **klass** som en ritning för något - "såhär ska fiender i spelet se ut - de ska ha de här egenskaperna".

Sedan skapar man **instanser** av klassen - de konkreta, faktiska fienderna. Alla goombas i Super Mario Bros och alla paladiner i World of Warcraft bygger på samma ritning. De har samma egenskaper och utseende i grunden, även om de skiljer sig åt i vilka värden en del av egenskaperna har. De befinner sig till exempel på olika positioner, även om de alla _har_ en position.

## Skapa klasser

Generellt bör varje klass läggas i sin egen fil. Med C# Toolbox of Productivity finns ett snabbt och enkelt sätt:

* **Högerklicka på mappen** klassen/filen ska skapas i.
* Välj **"Add a new C# Class file"**.
* Skriv in namnet på klassen – **glöm inte stor bokstav**!
* **Ta bort namespace**-kodblocket kring klassen; det behöver vi sällan.

{% tabs %}
{% tab title="Goomba.cs" %}
```csharp
class Goomba
{
  // Klassvariabler
  public int X = 0;
  public int Y = 0;
  public bool IsDead = false;
}
```
{% endtab %}
{% endtabs %}

## Skapa instanser

Kodordet `new` skapar **nya instanser** i minnet (heapen).

Därefter behöver en [referens ](../grundlaeggande/reference-vs-value-types.md)till instansen lagras någonstans, till exempel i en variabel.

```csharp
Goomba g1 = new Goomba();
Goomba g2 = new Goomba();
```

Därefter kan man ändra på de individuella instansernas variabler separat:

```csharp
g1.x = 60;
g1.y = 20;
g2.x = 80;
g2.y = 25;
```

Man kan också tilldela värden till variablerna direkt när instansen skapas:

```csharp
Goomba g3 = new Goomba() {x = 10, y = 6};
```

### New()

Om man (som ovan) skapar en instans av exakt samma klass som variabeln så kan koden förenklas. Det gäller med andra ord nästan jämt – undantaget är vid [polymorfism](polymorfism/#polymorfism-klasser-och-arv).

```csharp
Goomba g4 = new();
Goomba g5 = new() {x = 100};
```



