# Serialisera subklasser

Om man har en lista som innehåller instanser av olika klasser (via [polymorfi](../../../klasser-och-objektorientering/polymorfism/)), så serialiseras den listan normalt sett som om alla objekt var instanser av basklassen.

```csharp
List<Enemy> enemies = [
  new Fireflower(), // Fireflower, Goomba och HammerBrother är subklasser till Enemy
  new Goomba(),
  new HammerBrother()
];
```

För att meddela JSON-deserializern vilka subklasser den ska vara medveten om, används \[JsonSerivedType]

```csharp
[JsonDerivedType(typeof(Goomba), typeDiscriminator:"goomba")]
[JsonDerivedType(typeof(FireFlower), typeDiscriminator:"fireflower")]
[JsonDerivedType(typeof(HammerBrother), typeDiscriminator:"hammerbrother")]
public class Enemy 
{
  public int Hitpoints { get; set; }
  public string Name { get; set; }
}
```

I den JSON-kod som genereras, finns nu en extra egenskap vars jobb är att berätta hur varje objekt ska deserialiseras.

```json
[
  {
    "$type": "goomba",
    "CoolnessFactor": 0,
    "Hitpoints": 0,
    "Name": "Goomba"
  },
  // ...
]
```

## \[JsonPolymorphic]

Används för att deklarera information om hur ovanstående ska fungera.

```csharp
[JsonPolymorphic(TypeDiscriminatorPropertyName ="class")]
[JsonDerivedType(typeof(Goomba), typeDiscriminator:"Goomba")]
public class Enemy 
{
  public int Hitpoints { get; set; }
  public string Name { get; set; }
}
```

### InferClosedTypePolymorphism (C# 15)

Med C# 15 och senare så kan man förenkla allt detta genom att använda InferClosedTypePolymorphism. Detta kräver att basklassen är [closed](../../../klasser-och-objektorientering/closed.md). Då läggs ingen extra egenskap till i JSON-koden, och när koden ska deserialiseras så gör serializern sitt bästa för att _gissa_ vilken subklass som objektet ska räknas som utifrån vilka egenskaper den innehåller.

```csharp
[JsonPolymorphic(InferClosedTypePolymorphism = true)]
public class Enemy 
{
  public int Hitpoints { get; set; }
  public string Name { get; set; }
}
```
