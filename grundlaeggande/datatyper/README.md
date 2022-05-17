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

Length är en egenskap alla strings har. Det är en int som innehåller det antal tecken stringen har.

```csharp
Console.WriteLine($"Texten {s} har {s.Length} tecken");
```

### All()

All() är en del av **Linq-biblioteket** så man måste först ha med `using System.Linq`. All har en [delegate ](../delegates.md)som parameter, och förväntar sig då en metod (eller ett lambda-uttryck) som tar emot en `char` och returnerar `true` eller `false`. All stoppar sedan i var och ett av stringens tecken in i den angivna metoden. Om resultatet för alla blir `true` så returnerar All också `true`.

```csharp
using System.Linq;

string s1 = "12345";
string s2 = "123a45;

bool b1 = s1.All(char.IsDigit); // b1 = true
bool b2 = s2.All(char.IsDigit); // b2 = false
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

### Char.Is…

I klassen Char finns flera metoder för att undersöka char-tecken. Till exempel:

```csharp
Char.IsDigit(c) // true om c är en siffra
Char.IsLetter(c) // true om c är en bokstav
Char.IsLetterOrDigit(c) // true om c är en siffra eller en bokstav
Char.IsUpper(c) // true om c är en STOR BOKSTAV
Char.IsWhiteSpace(c) // true om c är ett mellanslag, en tabb eller en radbrytning
```

Observera att definitionen av "siffra" här inte bara inkluderar tecknen 0–9 utan också till exempel thailändska siffertecken.

## Andra heltal

Överkurs: det finns ett antal olika sätt att spara heltal, och de har olika min- och maxvärden.

* int, eller int32, är en 32-bitars integer. Den använder 32 ettor och nollor (bits/bitar) för att lagra ett heltal som kan vara positivt eller negativt. En av bitarna används för att avgöra ifall talet är positivt eller negativt.
* long, eller int64, är en 64-bitars integer.
* short, eller int16, är en 16-bitars integer.
* uint, ulong och ushort är versioner av int, long och short som inte kan bli negativa – men i gengäld kan mäta större positiva tal. Eftersom ingen bit används för att avgöra om talet är positivt/negativt.

Vilken som är lämplig vid vilket tillfälle beror på hur höga tal man behöver lagra samt hur viktigt det är att spara på minnesutrymmet.

```csharp
Console.WriteLine(int.MaxValue); //   2147483647
Console.WriteLine(int.MinValue); //  -2147483648
Console.WriteLine(uint.MaxValue); // 4294967295
Console.WriteLine(uint.MinValue); // 0

Console.WriteLine(long.MaxValue); //   9223372036854775807
Console.WriteLine(long.MinValue); //  -9223372036854775808
Console.WriteLine(ulong.MaxValue); // 18446744073709551615
Console.WriteLine(ulong.MinValue); // 0

Console.WriteLine(short.MaxValue); // 32767
Console.WriteLine(short.MinValue); // -32768
Console.WriteLine(ushort.MaxValue); // 65535
Console.WriteLine(ushort.MinValue); // 0
```
