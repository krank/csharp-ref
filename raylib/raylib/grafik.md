# Grafik

## Mått och koordinatsystem

Observera att koordinatsystemet i Raylib har **origo i övre vänstra hörnet**, och att **Y-axeln är omvänd** så att positiva värden går nedåt.

Måtten är i pixlar.

## BeginDrawing\(\), EndDrawing\(\)

Används för att påbörja, respektive avsluta, den delen av spelloopen som ritar ut saker till fönstret.

```csharp
while (!Raylib.WindowShouldClose())
{
  // Spelets logik
  
  Raylib.BeginDrawing();
  
  // Kod för att rita ut saker till fönstret
  
  Raylib.EndDrawing();
}
```

## ClearBackground\(\)

Rensar fönstret. Görs normalt kort efter BeginDrawing.

```csharp
while (!Raylib.WindowShouldClose())
{
  Raylib.BeginDrawing();

  Raylib.ClearBackground(Color.WHITE);
  
  Raylib.EndDrawing();
}
```

## Färger

Det finns en hel del färdiga färger i Raylib, till exempel Color.MAGENTA eller Color.ORANGE.

Om man vill skapa en egen ny färg så kan man göra det:

```csharp
Color hotPink = new Color(255, 105, 180, 255);
```

Parametrarna är helt enkelt siffror från 0–255 för rött, grönt, blått och alpha \(genomskinlighet\). 0 alpha är helt genomskinlig, 255 är helt ogenomskinlig.

## Enkla geometriska former

### DrawCircle

```csharp
Raylib.DrawCircle(150, 200, 40, Color.MAGENTA);
```

Parametrarna är, i tur och ordning: X- och Y-position för cirkelns mitt, cirkelns radie, och cirkelns färg.

### DrawRectangle

```csharp
Raylib.DrawRectangle(10, 10, 30, 40, Color.ORANGE);
```

Parametrarna är, i tur och ordning: X- och Y-position för rektangelns övre vänstra hörn, rektangelns bredd och höjd, och dess färg.

### DrawRectangleLines, DrawCircleLines

Fungerar precis som DrawCircle respektive DrawRectangle, men använder färgen för att rita ut respektive forms kanter istället för att fylla dem.

```csharp
Raylib.DrawCircleLines(150, 200, 40, Color.MAGENTA);
```

### DrawRectangleRec

Fungerar precis som DrawRectangle, men tar emot ett [Rectangle](rectangle.md)-objekt istället för koordinater och bredd/höjd.

```csharp
Rectangle r1 = new Rectangle(10,5,30,15);
Raylib.DrawRectangleRec(r1, Color.PINK);
```

