# Kollisioner

## CheckCollisionRecs\(\)

Tar emot två [Rectangles ](rectangle.md)som parametrar och returnerar true om de överlappar, false om de inte gör det.

```csharp
Rectangle playerRect = new Rectangle(5,5,10,10);
Rectangle enemyRect = new Rectangle(10,10,10,10);

bool areOverlapping = Raylib.CheckCollisionRecs(r1, r2); // true
```

## CheckCollisionCircles\(\)

Tar emot två [vektorer ](../../grundlaeggande/vektorer-numerics.md)som beskriver två cirklars mittpunkter, och två floats som beskriver cirklarnas radie, och returnerar true om de överlappar, false om de inte gör det.

```csharp
Vector2 playerPos = new Vector2(10,10);
Vector2 enemyPos = new Vector2(20,20);

// true
bool areOverlapping = Raylib.CheckCollisionCircles(playerPos, 10, enemyPos, 15);
```

{% hint style="warning" %}
Inte helt färdigt ännu!
{% endhint %}



