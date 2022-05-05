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

## Casting

När konverteringen innebär att man blir av med precision, t.ex. går från en float till en int och blir av med decimaler, så använder man ibland **casting**. Det betyder att man helt enkelt skriver vilken datatyp man vill konvertera till inom parenteser innan värdet som ska konverteras.

```csharp
float xPos = 3.4f;
int x = (int) xPos;
```

## As

As fyller en liknande funktion som casting, men fungerar bara på datatyper som är av referenstyp (t.ex. klasser) och datatyper som kan bli null (t.ex. string). Detta är mest användbart när man använt [polymorfi](../klasser-och-objektorientering/polymorfism/).

As går också lite snabbare än casting.

```csharp
// Säger att instansen som enemy-variabeln pekar mot är en instans av Goomba,
//  och att Goomba-variabeln "g" också ska peka mot samma instans.
Goomba g = enemy as Goomba;
```

## Is

Is kan användas för att se vilken datatyp ett värde är. Detta är mest användbart när man använt [polymorfi](../klasser-och-objektorientering/polymorfism/).

```csharp
// Om instansen som enemy-variabeln pekar mot är en instans av Goomba-klassen,
//  så kör koden inuti if-blocket.

if (enemy is Goomba)
{
  // ---
}
```

Is kan också göra en samtidig As-operation.

```csharp
// Om instansen som enemy-variabeln pekar mot är en instans av Goomba-klassen
//  så skapa en ny variabel "g" som är an datatypen Goomba och pekar mot
//  samma instans.

if (enemy is Goomba g)
{
  g.SetColor("Brown");
}
```

## Konvertera till int

### int.Parse()

Många datatyper kan inte konverteras direkt till t.ex. en int. Metodern int.Parse tar emot nästan vad som helst – t.ex. en string – och försöker konvertera den till en int.

```csharp
string tal = "42";
int i = int.Parse(tal);
```

### int.TryParse()

För en enkel, säker konvertering kan man använda TryParse.

```csharp
string tal = "42";
int resultat;
bool lyckad = int.TryParse(tal, out resultat);
```

TryParse returnerar true om konverteringen lyckades, false om den inte lyckades. Resultatet lagras i variabeln som anges som "out"-variabel i den andra parametern (i exemplet, variabeln "resultat"). Om konverteringen misslyckas så blir resultatet 0.

### .All(char.IsDigit)

Om man försöker använda Parse på en string som innehåller bokstäver så kan man få felmeddelande. Därför kan man använda följande kod för att undersöka ifall en string enbart innehåller siffror.

{% hint style="warning" %}
**OBS:** Du måste skriva in denna kod högst upp i filen för att All ska funka:\
`using System.Linq`
{% endhint %}

```csharp
string testNum = "456";
bool onlyContainsNumbers = testNum.All(char.IsDigit); // Blir true

string testLetters = "abrakadabra9";
bool onlyContainsNumbers = testLetters.All(char.IsDigit); // Blir false
```

## Konvertera till float

### float.Parse()

Tar emot ett värde, och konverterar det till en float – om det går. Resultatet av konverteringen returneras.

```csharp
string tal = "42.5"
float f = float.Parse(tal);
```

Om det inte går att konvertera värdet till en float, kommer Parse att ge ifrån sig ett runtime-felmeddelande.

### float.TryParse()

Tar emot två parametrar – ett värde som ska försöka konverteras till en float, och en "out"-variabel.

Den float som är resultatet av konverteringen lagras i out-variabeln.

Om konverteringen lyckades returnerar TryParse true, om den inte lyckas returneras istället false. Då blir också out-variabeln 0.

Metoden ger alltså två resultat ifrån sig – dels en bool som säger ifall konverteringen lyckades, och dels en float som innehåller resultatet av konverteringen.

```csharp
string tal = "42.5";
float f;
bool lyckad = int.TryParse(tal, out f);
```
