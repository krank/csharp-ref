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

```text
if (i > 4)
```

```text
{
```

```text
  Console.WriteLine("Högre än fyra!");
```

```text
}
```

```text
else
```

```text
{
```

```text
  Console.WriteLine("Inte högre än fyra!");
```

```text
}
```

#### else if <a id="h.p_V-P-XRp3Uq2f"></a>

Används för att skapa en kedja av if-satser, där varje if-sats bara kollas om den föregående inte satsens kriterium inte uppnåddes.

```text
if (i > 4)
```

```text
{
```

```text
  Console.WriteLine("Högre än fyra!");
```

```text
}
```

```text
else if (i < 0)
```

```text
{
```

```text
  Console.WriteLine("Lägre än noll!");
```

```text
}
```

```text
else
```

```text
{
```

```text
  Console.WriteLine("Högre än noll, lägre än fem!");
```

```text
}
```

