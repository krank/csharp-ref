# If-satser

## if-sats

Ett villkorat kodblock, som bara körs ifall ett kriterium \(booleskt uttryck\)

```csharp
if (i > 4)
{
  Console.WriteLine("Högre än fyra!");
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

