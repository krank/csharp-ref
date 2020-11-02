# Vektorer \(Numerics\)

Numerics är ett bibliotek som innehåller mer avancerade numeriska typer, som komplement till de vanliga, t.ex. int.

```csharp
using System.Numerics;
```

## Vector2

En Vector2 är en tvådimensionell vektor som består av två komposanter, en i x-led och en i y-led. Komposanterna har datatypen float.

```csharp
// Skapa en vektor med X-värde 20 och Y-värde 30.5
Vector2 position = new Vector2(20f 30.5f);
```

Man kan använda räknesätt med vektorer.

```csharp
Vector2 position = new Vector2(20, 20);
Vector2 movement = new Vector2(0.1f, 0.1f);

// Adderar movement-vektorn till position-vektorn
position += movement;
```

Man kan till och med kombinera vektorer med vanliga siffror och räknesätt.

```csharp
Vector2 position = new Vector2(20, 20);

// Skapar en vektor med X-värde 1 och Y-värde 0; 
// multiplicerar sedan både X och Y med 0.1.
Vector2 movement = new Vector2(1f, 0f) * 0.1f;

position += movement;
```

### Distance

Ger avståndet mellan två vektorer

```csharp
Vector2 position = new Vector2(20, 20);
Vector2 enemyPosition = new Vector2(30, 30);

float d = Vector2.Distance(position, enemyPosition); // 14.142136
```

### Length

### Normalize

