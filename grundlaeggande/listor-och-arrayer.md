# Listor och arrayer

Både listor och arrayer är samlingar, som \(förenklat\) låter oss lagra flera värden av samma datatyp på samma ställe. Man kan till exempel ha en samling av en massa int-värden som är samlade på samma ställe, eller en samling strings.

* **Arrayer** kom först, är snabba och effektiva, men kan inte växa/krympa – de har ett fast antal platser.
* **Listor** är en senare uppfinning, är nästan lika snabba, och kan växa/krympa.

## Indexering

Alla föremål som lagrats i en samling ges normalt ett index, som beskriver föremålets position i samlingen och låter oss komma åt det.

I arrayer och listor är index alltid en siffra – en integer. Det första föremålet i listan har index 0, det andra har index 1, etc.

```csharp
string[] names = {"Benny", "Jenny", "Kenny", "Anna"};
// I denna array har Benny index 0, Jenny 1, Kenny 2 och Anna 3.
```

## Array

Arrayer har en **fast längd** som bestäms när arrayen skapas.

```csharp
// Skapa en int-array med tre tomma platser
int[] arrayHp = new int[3];

// Skapa en string-array med tre platser som redan från början ges värden
string[] choices = {"Start", "Options", "Quit"};
```

### Length

Variabel som är inbyggd i arrayer. Har alltid ett värde som är lika med arrayens storlek.

```csharp
// Skapa en integer-variabel och tilldela den värdet som motsvarar 
// arrayens storlek
int length = arrayHp.Length;
```

### Contains\(\)

Ett snabbt sätt att se ifall en sak finns i arrayen.

```csharp
string choice = Console.ReadLine();
bool validAnswer = choices.Contains(choice);
```

{% hint style="info" %}
OBSERVERA: Contains är en del av biblioteket Linq, så du behöver skriva detta längst upp bland dina andra using-statements:

**`using System.Linq;`**
{% endhint %}

### Att göra om en array till en lista

```csharp
// Skapa en string-lista baserat på arrayHp, med samma innehåll och storlek
List<string> lNamn = new List<string>(arrayHp);
```

## Flerdimensionella arrayer

En vanlig array är endimensionell – en lista. Varje sak i arrayen identifieras av ett index.

En tvådimensionell array är som ett rutnät. Varje sak i arrayen identifieras av två index.

```csharp
// Skapa en tvådimensionell array med 150 platser; 10 rader med 15 kolumner
int[,] grid = new int[10,15];

// Bestäm värdet på position 2,2 till 1
grid[2,2] = 1;
```

### GetLength

För att läsa av en flerdimensionell arrays längd i någon dimension, använd GetLength.

```csharp
for (int y = 0; y < grid.GetLength(1); y++)
{
  for (int x = 0; x < grid.GetLength(0); x++)
  {
    grid[x, y] = 0;
  }
}
```

## List

När listor skapas har de normalt sett en längd på 0, och de **växer dynamiskt** när man lägger till saker i dem.

```csharp
// Skapa en tom string-lista
List<string> listNamn = new List<string>();

// Skapa en string-lista som redan från början innehåller tre värden
List<string> choices = new List<string>() {"Start", "Options", "Quit"};
```

Mer information om List finns under [Generiska klasser](../klasser-och-objektorientering/generiska-klasser.md).

{% hint style="info" %}
OBSERVERA: Om du använder .NET Core så behöver du manuellt skriva till detta högst upp i dokumentet för att listor ska fungera:

```csharp
using System.Collections.Generic;
```
{% endhint %}

### Add\(\)

Metod som är inbyggd i listor. Används för att lägga till nya föremål i listan.

```csharp
listNamn.Add("Kim");
```

### Count

Variabel som är inbyggd i listor. Har alltid ett värde som är lika med listans storlek.

```csharp
// Skapa en integer-variabel och tilldela den värdet som motsvarar listans storlek
int length = listNamn.Count;
```

### Remove\(\)

Metod som är inbyggd i listor. Används för att ta bort föremål från listan.

```csharp
listNamn.Remove("Kim");
```

### RemoveAt\(\)

Metod som är inbyggd i listor. Används för att ta bort föremål på en specifik plats i listan.

```csharp
listNamn.RemoveAt(4);
```

### RemoveAll\(\)

Metod för att ta bort alla föremål som matchar ett visst kriterium. Kriteriet skrivs som en metod. Metoden tar emot ett värde av samma datatyp som listan innehåller, och returnerar true om kriteriet är uppfyllt och false om det inte är det. Här används med andra ord [delegates](delegates.md).

```csharp
// IsAboveScreen är kriteriet
static bool IsAboveScreen(Rectangle r)
{
  return r.y < 0;
}

static void Main(string[] args)
{
  List<Rectangle> rects = new List<Rectangle>();

  /* ... */

  // Tar bort alla rektanglar som, när de stoppas in 
  // i metoden, får den att returnera true
  rects.RemoveAll(IsAboveScreen);
```

Ett annat sätt är att använda ett [lambda-uttryck](delegates.md#lambdas):

```csharp
rects.removeAll(rect => rect.y < 0);
```

### Att göra om en lista till en array

```csharp
string[] aNamn = listNamn.ToArray();
```

