# Reference vs value types\*

{% hint style="info" %}
**OBS:** Lite överkurs =)
{% endhint %}

## Identifiers

Variabelnamn är egentligen bara namn på specifika minnesplatser i datorns RAM-minne.

{% code lineNumbers="true" %}
```csharp
int t; // Reservera 32 bitar i datorns minne för att lagra heltal, 
       //  och namge den minnesadressen "t"
t = 8; // Lagra heltalet 8 i den minnesaddress som har namnet "t".
```
{% endcode %}

Namnet något får kallas för en **identifier**.

## Minnet – stacken och heapen

Förenklat delas datorns minne upp i två delar: **Stacken** och **heapen**.

**Stacken** är strukturerad, snabb och begränsad i storlek. Det man lägger i den finns bara kvar så länge det nuvarande kodblocket körs.

**Heapen** är ostrukturerad, stor och det man lägger i den lever kvar tills det tas bort. I en del språk betyder det att man alltid måste komma ihåg att ta bort saker som ligger där manuellt – i C# och en del andra språk finns s.k. Garbage Collection som då och då rensar bort saker i heapen som det inte längre finns någon identifier som pekar mot.

**Identifiers finns alltid i stacken.** I stacken skapas en koppling mellan identifiern och vad den är satt att identifiera.

(Bild: Stacken som en tabell med identifiers och något de identifierar)

## Value types

För datatyper som är **value types** lagras också **värdet** i stacken. Int är ett exempel på value type. Så när int-variabeln t skapas så är det i stacken namnet "t" associeras med ett 32-bitar stort minnesutrymme.

Exempel på value types:

* int, float och övriga numeriska typer.
* bool
* struct-typer

(Bild: Stack-tabellen med ett par ints och deras värden)

## Reference types

För datatyper som är reference types lagras själva objektet, datan, i heapen. Det enda som lagras på minnesadressen i stacken är en referens vidare till platsen i stacken där datan finns.

Så identifiern pekar på en plats i stacken, på den platsen finns en vidarepekning till en plats i heapen.

(Bild: Stack-tabellen och Heap-utrymmet med ett par pekare)

## Varför är det här viktigt?

### Tilldelning

Value types och reference types beter sig olika när tilldelnings-operatorn = används. Mer exakt beter de sig exakt lika – men eftersom de lagrar olika saker i stacken så blir effekten olika.

{% code lineNumbers="true" %}
```csharp
int a = 9;
int b = a; // Kopierar stack-positionen som identifiern a pekar på
           //  till stack-positionen som identifiern b pekar på.
```
{% endcode %}

(Bild: enkel stack-operation, före och efter)

{% code lineNumbers="true" %}
```csharp
Fighter f = new Fighter(); // Instans skapas av klassen Fighter.
                           // Instansen lagras i heapen.
                           // Identifiern f skapas och pekar mot en plats i stacken.
                           // På den platsen finns en pekning till instansens plats
                           //  i heapen.

Fighter f2 = f; // Identifiern f2 skapas.
                // Det som finns på platsen i stacken som f pekar mot
                // kopieras till platsen som f2 pekar på.
                // Inget nytt objekt skapas i heapen – både f1 och f2 pekar mot
                //  samma objekt.
```
{% endcode %}

(Bild: Stack-heap-operation)

### Parametervärden

Ovanstående gäller också parametrar i metoder.

{% code lineNumbers="true" %}
```csharp
int k = 9;

TakeInt(k); // talet 9 kopieras från k-identifiern till i-identifiern.

static void TakeInt(int i)
{
  // variabeln i pekar mot sin helt egna kopia av talet 9.
}
```
{% endcode %}

{% code lineNumbers="true" %}
```csharp
Fighter f = new Fighter();

TakeFight(f); // Referensen till fighter-instansen kopieras från f till localFighter

Console.WriteLine(f.hp); // visar att f's hp-värde ändrades inuti metodenc

static void TakeFight(Fighter localFighter)
{
  // Variabeln localFighter pekar mot samma instans som variabeln f.
  localFighter.hp -= 9; // Ändrar på instansens hp-värde
}
```
{% endcode %}

## Out och ref



{% embed url="https://www.c-sharpcorner.com/article/stack-heap-value-type-and-reference-type-in-c-sharp/" %}
