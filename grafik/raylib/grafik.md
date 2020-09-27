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

## Bilder och texturer

I Raylib skiljer man på _bilder_ och _texturer_.

### Image

En Image är en bild som är sparad i datorns arbetsminne, och kan manipuleras på olika sätt.

```csharp
// Skapar en svart bild som är 200x200 pixlar.
Image emptyImage = Raylib.GenImageColor(200, 200, Color.BLACK);

// Skapar en röd bild som är 200x200 pixlar.
Image emptyImage = Raylib.GenImageColor(200, 200, Color.RED);

// Läser in bilden hero.png och bygger en ny Image baserat på den.
// OBS! bilden måste ligga i samma mapp som exe-filen (eller projektet)!
Image filebasedImage = Raylib.LoadImage(@"hero.png");
```

### ImageDrawPixel

Ändrar färg på en pixel i en Image.

```csharp
// Ändrar pixeln som är 20 pixlar från vänsterkanten och 15 från 
// toppen av bilden till att bli blå
Raylib.ImageDrawPixel(ref targetImage, 20, 15, Color.BLUE);
```

### ImageFlipHorizontal

Flippar en Image horisontellt \(spegelvänder\).

```csharp
Raylib.ImageFlipHorizontal(ref targetImage);
```

### ImageFlipVertical

Flippar en Image vertikalt.

```csharp
Raylib.ImageFlipVertical(ref targetImage);
```

### ImageResize/ImageResizeNN

Ändrar storlek på en bild. NN-versionen ger ett skarpt resultat vilket fungerar bra för pixelart som skalas med jämna multiplikationer.

```csharp
//Ändrar storleken på bilden "someImage" till 400x400 pixlar
Raylib.ImageResize(ref someImage, 400, 400);

//Ändrar storleken på bilden "pixelartImage" till dubbla dess nuvarande storlek
RayLib.ImageResizeNN(ref pixelartImage, pixelartImage * 2, pixelartImage * 2);
```

### Texture

En Texture är en bild som är sparad i grafikkortets minne, och är redo att ritas ut på skärmen. Man kan skapa en Texture utifrån en Image eller läsa in en bildfil från hårddisken direkt. Om man ska använda samma Image i flera olika Textures så kan det vara bra att skapa en Image först, så slipper man läsa in den från hårddisken flera gånger.

```csharp
// Skapar en ny texture baserat på en Image som redan lästs in.
Texture heroTexture = Raylib.LoadTextureFromImage(originalImage);

// Läser in en bildfil och skapar en texture direkt från den.
Texture goombaTexture = Raylib.LoadTexture(@"goomba.png");
```

Images kan manipuleras mer. Textures kan ritas ut till skärmen.

### DrawTexture

```csharp
// Ritar texturen heroTexture till fönstret, på x-position 40 och 
// y-position 300, utan infärgning (WHITE färgar inte)
Raylib.DrawTexture(heroTexture, 40, 300, Color.WHITE)
```

