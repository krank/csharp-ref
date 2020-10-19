# Typkonvertering

## Implicit konvertering

En del datatyper kan lätt konverteras till andra utan att man behöver göra någon manuell konvertering. Det gäller framför allt när konverteringen inte innebär att man blir av med information eller precision.

```csharp
int i = 9;
long l = i;
```

### Exempel:

* int → long
* int → string
* int → float
* float → double

## Explicit konvertering / Casting

När konverteringen innebär att man blir av med precision, t.ex. går från en float till en int och blir av med decimaler, så behöver man använda **casting**. Det betyder att man helt enkelt skriver vilken datatyp man vill konvertera till inom parenteser innan värdet som ska konverteras.

```csharp
float xPos = 3.4f;
int x = (int) xPos;
```

## Konvertera till int

### int.Parse

Många datatyper kan inte konverteras direkt till t.ex. en int. Metodern int.Parse tar emot nästan vad som helst – t.ex. en string – och försöker konvertera den till en int.

```csharp
string tal = "42";
int i = int.Parse(tal);
```

### int.TryParse

För en enkel, säker konvertering kan man använda TryParse.

```csharp
string tal = "42";
int resultat;
bool lyckad = int.TryParse(tal, out resultat);
```

TryParse returnerar true om konverteringen lyckades, false om den inte lyckades. Resultatet lagras i variabeln som anges som "out"-variabel i den andra parametern \(i exemplet, variabeln "resultat"\). Om konverteringen misslyckas så blir resultatet 0.

### .All\(char.IsDigit\)

Om man försöker använda Parse på en string som innehåller bokstäver så kan man få felmeddelande. Därför kan man använda följande kod för att undersöka ifall en string enbart innehåller siffror.

```csharp
string testNum = "456";
bool onlyContainsNumbers = testNum.All(char.IsDigit); // Blir true

string testLetters = "abrakadabra9";
bool onlyContainsNumbers = testLetters.All(char.IsDigit); // Blir false
```

## Konvertera till float

### float.Parse

Fungerar motsvarande int.Parse, men omvandlar till floats istället.

```csharp
string tal = "42.5"
float f = float.Parse(tal);
```

### float.TryParse

```csharp
string tal = "42.5";
float f;
bool lyckad = int.TryParse(tal, out f);
```

