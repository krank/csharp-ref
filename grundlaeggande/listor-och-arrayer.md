# Listor och arrayer

## Array

Datatyp som innehåller flera värden av samma typ. Till exempel flera int-värden.

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

### Contains

Ett snabbt sätt att se ifall en sak finns i arrayen.

```csharp
string choice = Console.ReadLine();
bool validAnswer = choices.Contains(choice);
```

### Att göra om en array till en lista

```csharp
// Skapa en string-lista baserat på arrayHp, med samma innehåll och storlek
List<string> lNamn = new List<string>(arrayHp);
```

## Flerdimensionella arrayer

En vanlig array är endimensionell – en lista. Varje sak i arrayen identifieras av ett index.

En tvådimensionell array är som ett rutnät. Varje sak i arrayen identifieras av två index.

```csharp
// Skapa en tvådimensionell array med 100 platser; 10 rader med 15 kolumner
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

Datatyp som innehåller flera värden av samma typ. Till exempel flera int-värden.

När listor skapas har de normalt sett en längd på 0, och de **växer dynamiskt** när man lägger till saker i dem.

```csharp
// Skapa en tom string-lista
List<string> listNamn = new List<string>();

// Skapa en string-lista som redan från början innehåller tre värden
List<string> choices = new List<string>() {"Start", "Options", "Quit"};
```

Mer information om List finns under Generiska klasser \(Länk kommer\).

{% hint style="info" %}
**OBSERVERA:** Om du använder .NET Core så behöver du manuellt skriva till detta högst upp i dokumentet för att listor ska fungera:

```csharp
using System.Collections.Generic;
```
{% endhint %}

### Add

Metod som är inbyggd i listor. Används för att lägga till nya föremål i listan.

```csharp
listNamn.Add("Kim");
```

### Remove

Metod som är inbyggd i listor. Används för att ta bort föremål från listan.

```csharp
listNamn.Remove("Kim");
```

### RemoveAt

Metod som är inbyggd i listor. Används för att ta bort föremål på en specifik plats i listan.

```csharp
listNamn.RemoveAt(4);
```

### Count

Variabel som är inbyggd i listor. Har alltid ett värde som är lika med listans storlek.

```csharp
// Skapa en integer-variabel och tilldela den värdet som motsvarar listans storlek
int length = listNamn.Count;
```

### Att göra om en lista till en array

```csharp
string[] aNamn = listNamn.ToArray();
```

## Indexering

För att komma åt ett specifikt värde i en lista eller en array används ett index – en siffra som motsvarar positionen. Det första föremålet i listan har index 0, det andra har index 1, etc.

```csharp
// Skapa en string-variabel och tilldela den 
// värdet som är lagrat på den tredje platsen i listan.
string name = listNamn[2];

// Skapa en int-variabel och tilldela den 
// värdet som är lagrat på den andra platsen i arrayen.
int num = arrayNamn[1];
```

