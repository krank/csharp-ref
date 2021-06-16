# Konsollen \(Console\)

### Console.WriteLine\(\)

Skriver ut något till konsollen.

```csharp
Console.WriteLine("Hello!");
```

### Console.ReadLine\(\)

Läser in en string från användaren och väntar på Enter-tryckning. Returnerar stringen så att den kan lagras i en variabel eller användas i koden.

```csharp
string answer = Console.ReadLine();
```

### Console.Title

Ändrar konsollfönstrets namn.

```csharp
Console.Title = "Mitt fina fönster";
```

### Console.Clear\(\)

Rensar skärmen.

```csharp
Console.Clear();
```

### Console.ForegroundColor

Variabel vars värde avgör färgen på texten i konsollfönstret.

```csharp
Console.ForegroundColor = ConsoleColor.Cyan;
```

{% hint style="info" %}
OBSERVERA: detta gäller enbart text som skrivs efter det att färgen ändrats. Text som redan skrivits ut förändras inte.
{% endhint %}

### Console.BackgroundColor

Variabel vars värde avgör färgen på texten i konsollfönstret.

```csharp
Console.BackgroundColor = ConsoleColor.Magenta;
```

{% hint style="info" %}
OBSERVERA: detta gäller enbart text som skrivs efter det att färgen ändrats. Text som redan skrivits ut förändras inte.
{% endhint %}

### Console.Beep\(\)

Gör ett ljud!

```csharp
Console.Beep(294,1000) // 1 sekunds (1000 millisekunders) beep i D.
```

### Console.CursorLeft

Pekarens position i x-led, räknat från fönstrets vänstra kant \(den första "kolumnen" är 0\)

```csharp
Console.CursorLeft = 20; // Placera pekaren i kolumn 20
```

```csharp
Console.CursorLeft -= 5; // Flytta pekaren fem steg åt vänster
```

### Console.CursorTop

Pekarens position i y-led, räknat från fönstrets överdel.

```csharp
Console.CursorTop = 10; // Placera pekaren på rad 10
```

```csharp
Console.CursorTop-- // Flytta pekaren 1 rad uppåt
```

{% hint style="info" %}
OBSERVERA: y-axeln är **omvänd**! Med andra ord, den första raden är 0, den andra är 1, den tredje är 2…
{% endhint %}

