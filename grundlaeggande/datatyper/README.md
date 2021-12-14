# Datatyper \[…]

## int

Integer, heltal.

```csharp
int x = 3;
```

## string

En string är en text – en serie tecken efter varandra.

```csharp
string s = "Hello";
```

### Length

Alla strings har en inbyggd egenskap som heter Length. Det är en int som innehåller det antal tecken stringen har.

```csharp
Console.WriteLine($"Texten {s} har {s.Length} tecken");
```

### \ – specialtecken

Om man skriver \ i en string så kommer tecknet efter att tolkas som ett specialtecken. Det vanligaste är \n, som är en newline (ny rad).

```csharp
Console.WriteLine("Detta är första raden.\nDetta är andra raden.");
```

### $ – interpolated strings

Om man skriver $ framför en string, så kan man sedan stoppa in variabler och metodanrop och annat inuti måsvingar i stringen. Det som står innanför måsvingarna utvärderas och blir en del av stringen.

OBS: utvärderingen sker bara en gång. Så i exemplet nedan spelar det ingen roll att hp-variabeln minskar med 50 på rad 3, stringen s innehåller fortfarande bara "Du har 100 hit points kvar".

```csharp
int hp = 100;
string s = $"Du har {hp} hit points kvar";
hp -= 50;
```

### @ – literal strings

Om man skriver @ framför en string, så kommer varje tecken i denna string sedan att tolkas väldigt bokstavligt. Framför allt används detta när man inte vill att \ ska tolkas, utan bara skrivas ut som just \\. Det är praktiskt när man ska göra ASCII-art eller sökvägar i Windows.

```
Console.WriteLine(@"Detta är första raden.\nDetta är också första rader.");
```

## float

Flyttal, decimaltal.

```csharp
float y = 3.4f;
```

## bool

Boolskt värde, är antingen true eller false.

```csharp
bool z = true;
```

## char

Ett tecken.

```csharp
char c = 'ä';
```

## long

Heltal, kan ha mycket större (och mindre) värden än int.

```csharp
long i = 9223372036854775804; 
```

##
