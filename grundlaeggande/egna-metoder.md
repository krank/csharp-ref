# Egna metoder\*

## Enkel metod

En metod är ett namngivet kodblock, som kan anropas från andra delar av koden genom att man skriver dess namn. Det gör att koden kan återanvändas och man slipper skriva samma kod flera gånger.

```csharp
static void MetodensNamn()
{
  Console.WriteLine("Hej!");
}
```

För att anropa metoden skriver man sedan:

```csharp
MetodensNamn();
```

"static"-delen behövs _enbart_ om metoden ska kunna anropas från en annan metod som också är static, till exempel Main.

För mer information om vad "static" egentligen betyder – [läs här](../klasser-och-objektorientering/static.md).

## Parametrar

Genom parametrar kan man föra in information i metoden när den anropas.

```csharp
static void PrettyPrint(string text)
{
  Console.WriteLine($"--~~== {text} ==~~--");
}
```

För att deklarera värdet av parametern vars namn är text anropas metoden ovan såhär:

```csharp
PrettyPrint("Horsies!");
```

Resultatet blir att följande skrivs ut till konsollen:

```
--~~== Horsies! ==~~--
```

## Returnering

För att få ut information ur en metod så att informationen kan användas i resten av programmet används returnering. Det innebär att man istället för void skriver vilken datatyp informationen man vill få ut från metoden ska ha, och sedan någonstans i metoden skriver return följt av en information som har denna datatyp.

```csharp
static float OneThird()
{
  float result = 1f / 3f;
  return result;
} 
```

När man sedan anropar metoden så fångar man upp den returnerade informationen i en variabel.

```csharp
float f = OneThird();
```

Ofta kombinerar man parametrar och returneringar för att bygga metoder som bearbetar den information man stoppar in på något sätt.

```csharp
static int Multiply(int a, int b)
{
  int result = a * b;
  return result;
}
```

Och ovanstående metod anropas såhär:

```csharp
int area = Multiply(3, 4);
```

Resultatet blir att 3 multipliceras med 4 inuti metoden, och resultatet (12) returneras och lagras i variabeln `area`.

## Överlagring

Att överlagra metoder innebär att man döper flera metoder till samma namn, men låter dem ha olika parametrar.

Effekten blir att när man anropar metodnamnet så används de parametervärden man anger för att avgöra vilken av de olika metoderna som ska köras.

```csharp
static void Shout()
{
  Console.WriteLine("AAAAAAAAH!");
}
```

```csharp
static void Shout(string exclamation)
{
  Console.WriteLine(exclamation.ToUpper());
}
```

De två Shout-metoderna ovan har samma namn, men den ena tar emot en parameter. Om man nu anropar så här:

```csharp
Shout();
```

Så kommer den övre versionen att köras. Inget parametervärde angavs, och det finns en version av Shout som inte behöver några parametrar, alltså körs den.

Om man däremot anropar så här:

```csharp
Shout("abracadabra!");
```

Så kommer den nedre versionen att köras. Ett string-värde angavs som parametervärde, och det finns en version av Shout som behöver ett string-värde, alltså körs den.

## Generiska metoder

(Kommer…)
