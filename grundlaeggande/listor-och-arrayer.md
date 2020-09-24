# Listor och arrayer

## Array

Datatyp som innehåller flera värden av samma typ. Till exempel flera int-värden.

Arrayer har en **fast längd** som bestäms när arrayen skapas.

```csharp
// Skapa en int-array med tre tomma platser
int[] arrayHp = new int[3]

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

### Att göra om en array till en lista;

```csharp
// Skapa en string-lista baserat på arrayHp, med samma innehåll och storlek
List<string> lNamn = new List<string>(arrayHp);
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

```text
// Skapa en string-variabel och tilldela den värdet som är lagrat på den tredje platsen i listan.
```

```text
string name = listNamn[2];
```

```text

```

```text
// Skapa en int-variabel och tilldela den värdet som är lagrat på den andra platsen i arrayen.
```

```text
int num = arrayNamn[1];
```

