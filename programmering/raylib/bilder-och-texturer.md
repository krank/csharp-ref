# Bilder och texturer

## Bilder och texturer

I Raylib skiljer man på _Images_ och _Textures_.

Skillnaden är att Images kan _manipuleras mer_. Textures kan _ritas ut till skärmen_.

### Filformat som stöds

* png
* bmp
* tga
* gif \(dock ej animationer\)
* dds, hdr, ktx, astc

Observera att det saknas stöd för jpg – detta eftersom jpg är väldigt ovanligt i spel.

## Image

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

För att man ska kunna rita ut den till fönstret behöver man sedan konvertera den till en texture.

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

## Texture

En Texture är en bild som är sparad i grafikkortets minne, och är redo att ritas ut på skärmen. Man kan skapa en Texture utifrån en Image eller läsa in en bildfil från hårddisken direkt. Om man ska använda samma Image i flera olika Textures så kan det vara bra att skapa en Image först, så slipper man läsa in den från hårddisken flera gånger.

```csharp
// Skapar en ny texture baserat på en Image som redan lästs in.
Texture2D heroTexture = Raylib.LoadTextureFromImage(originalImage);

// Läser in en bildfil och skapar en texture direkt från den.
Texture2D goombaTexture = Raylib.LoadTexture(@"goomba.png");
```

### DrawTexture

```csharp
// Ritar texturen heroTexture till fönstret, på x-position 40 och 
// y-position 300, utan infärgning (WHITE färgar inte)
Raylib.DrawTexture(heroTexture, 40, 300, Color.WHITE)
```

### DrawTextureEx

En lite mer avancerad version av DrawTexture, som dels använder en vektor för att ange x och y-värden, dels låter oss ange rotation och skalning av texturen.

```csharp
// Ritar texturen heroTexture till fönstret, på x-position 40 och 
// y-position 300, utan infärgning (WHITE färgar inte)
// Använd skalning 0.5 och rotation 0.
Vector2 position = new Vector2(40, 300);
Raylib.DrawTexture(heroTexture, position, 0, 0.5f, Color.WHITE)
```

{% hint style="info" %}
**OBSERVERA:** För att kunna använda [Vector2 ](../grundlaeggande/vektorer-numerics.md)så måste du lägga in detta bland dina using-statements:

```csharp
using System.Numerics;
```
{% endhint %}



