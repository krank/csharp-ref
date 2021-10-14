# Geometriska former

## Rektanglar

### DrawRectangle()

```csharp
Raylib.DrawRectangle(10, 10, 30, 40, Color.ORANGE);
```

Parametrarna är, i tur och ordning: X- och Y-position för rektangelns övre vänstra hörn, rektangelns bredd och höjd, och dess färg.

### DrawRectangleLines(), DrawCircleLines()

Fungerar precis som DrawCircle respektive DrawRectangle, men använder färgen för att rita ut respektive forms kanter istället för att fylla dem.

```csharp
Raylib.DrawCircleLines(150, 200, 40, Color.MAGENTA);
```

### DrawRectangleRec()

Fungerar precis som DrawRectangle, men tar emot ett [Rectangle](rectangle.md)-objekt istället för koordinater och bredd/höjd.

```csharp
Rectangle r1 = new Rectangle(10,5,30,15);
Raylib.DrawRectangleRec(r1, Color.PINK);
```

## Cirklar och elipser

### DrawCircle()

```csharp
Raylib.DrawCircle(150, 200, 40, Color.MAGENTA);
```

Parametrarna är, i tur och ordning: X- och Y-position för cirkelns mitt, cirkelns radie, och cirkelns färg.

### DrawCircleSector()

(kommer)

## Andra former

### DrawTriangle()

(kommer)

### DrawPoly()

(kommer)

### DrawLine()

(kommer)

### DrawLineBezier()

(kommer)

