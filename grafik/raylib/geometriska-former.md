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

### DrawCircleV()

Ritar en cirkel men använder en Vector2 som mittpunkt.

```csharp
Vector2 midPoint = new Vector2(100, 100);
Raylib.DrawCircleV(midPoint, 40, Color.PINK);
```

### DrawCircleSector()

Ritar en del av en cirkel.

```csharp
Vector2 midPoint = new Vector2(100, 100);
Raylib.DrawCircleSector(midPoint, 50, 0, -45, 100, Color.PINK);
```

Parametrarna är alltså mittpunkten, radien, startgraden, slutgraden, antalet segment som ska ritas ut samt färgen. Graderna utgår från att noll är rakt nedåt, och räknar motsols(!). Med andra ord är 0 nedåt, 90 är rakt åt höger och −90 är rakt åt vänster.

## Andra former

### DrawTriangle()

(kommer)

### DrawPoly()

(kommer)

### DrawLine()

(kommer)

### DrawLineBezier()

(kommer)

