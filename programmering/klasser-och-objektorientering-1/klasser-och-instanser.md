# Klasser och instanser

Klasser är ett sätt att klumpa ihop variabler och metoder som hör till samma "sak" i ett spel eller ett program. De gör det lättare att felsöka och lättare att hålla god struktur.

Man kan betrakta en **klass** som en ritning för något - "såhär ska fiender i spelet se ut - de ska ha de här egenskaperna".

Sedan skapar man **instanser** av klassen - de konkreta, faktiska fienderna. Alla goombas i Super Mario Bros och alla paladiner i World of Warcraft bygger på samma ritning. De har samma egenskaper och utseende i grunden, även om de skiljer sig åt i vilka värden en del av egenskaperna har. De befinner sig till exempel på olika positioner, även om de alla _har_ en position.

Så här skulle en enkel version av den klassen se ut:

{% tabs %}
{% tab title="Goomba.cs" %}
```csharp
class Goomba
{
 public int x = 0;
 public int y = 0;
 public bool isDead = false;
}
```
{% endtab %}
{% endtabs %}

Och så här skulle man sedan göra för att skapa instanser av klassen:

```csharp
Goomba g1 = new Goomba();
Goomba g2 = new Goomba();
```

Därefter kan man ändra på de inviduella instansernas variabler separat:

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

## Skapa klasser i Visual Studio Code

### Med VS Sharper for C\#

* Högerklicka på mappen du vill skapa klassen i.
* Välj "Add a new C\# Class file".
* Skriv in namnet på klassen – glöm inte stor bokstav!

### Med Solution Explorer

* Gå till Solution Explorer
* Högerklicks på ditt projekt
* Välj "Create file"

![](../../.gitbook/assets/image%20%2817%29.png) 

* Skriv in ett filnamn – lämpligen klassens namn punkt cs.

![](../../.gitbook/assets/image%20%2818%29.png) 

* Om du får upp en lista, välj "Class".



