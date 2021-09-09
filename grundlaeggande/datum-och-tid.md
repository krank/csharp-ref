---
description: (Under uppbyggnad)
---

# Datum och tid

## DateTime

Datatyp som lagrar tidpunkter.

```csharp
// Datumet 10:e december 1815
DateTime lovelaceBirthday = new DateTime(1815, 12, 10);
```

### Egenskaper

```csharp
Console.WriteLine(lovelaceBirthday.DayOfWeek); // vilken dag i veckan det är
Console.WriteLine(lovelaceBirthday.Year);
Console.WriteLine(lovelaceBirthday.Month);
Console.WriteLine(lovelaceBirthday.Day); // Dag i månaden
Console.WriteLine(lovelaceBirthday.Hour);
Console.WriteLine(lovelaceBirthday.Minute);
Console.WriteLine(lovelaceBirthday.Second);
Console.WriteLine(lovelaceBirthday.Millisecond);
```

### Metoder

## DateTime.Now

Tidpunkten _just nu_.

\(Är egentligen en [static ](../klasser-och-objektorientering/static.md#statiska-variabler)[property](../klasser-och-objektorientering/inkapsling-och-properties.md#properties)\)

```csharp
DateTime startTime = DateTime.Now;
```

## TimeSpan

Datatyp som beskriver ett tidsspann, till exempel "tiden mellan 26:e mars 1926 och 27:e februari 2015".

Om man subtraherar en DateTime från en annan DateTime så blir resultatet en TimeSpan.

```csharp
DateTime leonardBirth = new DateTime(1926, 3, 26);
DateTime leonardDeath = new DateTime(2015, 2, 27);

TimeSpan life = leonardDeath - leonardBirth;
```

### Tidsenheter i en TimeSpan

```csharp
// Dagar
Console.WriteLine(life.Days); // en int: 32480 hela dagar i spannet
Console.WriteLine(life.TotalDays); // en double, som inkluderar delar av dagar

// Timmar
Console.WriteLine(life.Hours); // Timme-komponenten för spannet. Går mellan -23 och 23.
Console.WriteLine(life.TotalHours); // En double: 779520 hela timmar i spannet

// Minuter
Console.WriteLine(life.Minutes); // Minut-komponenten för spannet. Går mellan -59 och 59.
Console.WriteLine(life.TotalMinutes); // En double: 46771200 minuter i spannet

// Sekunder
Console.WriteLine(life.Seconds); // Timme-komponenten för spannet. Går mellan -59 och 59.
Console.WriteLine(life.TotalSeconds); // En double: 2806272000 sekunder i spannet

// Millisekunder
Console.WriteLine(life.Milliseconds); // Timme-komponenten för spannet. Går mellan -59 och 59.
Console.WriteLine(life.TotalMilliseconds); // En double: 2806272000000 millisekunder i spannet
```

## Att mäta tid

Ett vanligt användningsområde för DateTime och TimeSpan är att mäta hur lång tid något tar.

```csharp
DateTime start = DateTime.Now

// Någon tung och jobbig kod körs här

DateTime end = DateTime.Now

TimeSpan span = end - start;

Console.WriteLine("Det tog:");
Console.WriteLine($"{span.Hours} timmar");
Console.WriteLine($"{span.Minutes} minuter");
Console.WriteLine($"{span.Seconds} sekunder");
Console.WriteLine($"{span.Milliseconds} millisekunder");
```



