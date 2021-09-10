# If-satser

## if-sats

Ett villkorat kodblock. Koden i blocket körs bara om det som är mellan parenteserna är _sant_.

Man kan bara lägga in kod som ger [boolskt](datatyper/#bool) resultat mellan parenteserna, t.ex. en [jämförelse ](operatorer.md#boolska)eller en metod som [returnerar ](egna-metoder.md#returnering)ett boolskt värde.

```csharp
if (i > 4)
{
  Console.WriteLine("Högre än fyra!");
}

if (name == "Micke")
{
  Console.WriteLine("Innehållet i variabeln name är samma som 'Micke'");
}
```

## else

Kompletterar en if-sats. Skrivs innan ett kodblock som ska köras om if-satsens kriterium inte stämmer.

```csharp
if (i > 4)
{
  Console.WriteLine("Högre än fyra!");
}
else
{
  Console.WriteLine("Inte högre än fyra!");
}
```

## else if

Används för att skapa en kedja av if-satser, där varje if-sats bara kollas om den föregående inte satsens kriterium inte uppnåddes.

```csharp
if (i > 4)
{
  Console.WriteLine("Högre än fyra!");
}
else if (i < 0)
{
  Console.WriteLine("Lägre än noll!");
}
else
{
  Console.WriteLine("Högre än noll, lägre än fem!");
}
```

