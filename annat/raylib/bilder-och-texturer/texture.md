# Texture

En Texture är en bild som är sparad i grafikkortets minne, och är redo att ritas ut på skärmen. Man kan skapa en Texture utifrån en [Image ](image.md)eller läsa in en bildfil från hårddisken direkt.

## Width och height

Varje texture har en width och en height.

```csharp
Console.WriteLine($"Width: {goombaTexture.width});
Console.WriteLine($"Height: {goombaTexture.height});

Rectangle hitBox = new Rectangle(0, 0, goombaTexture.width, goombaTexture.height);
```

## Läsa in

### LoadTexture()

Läser in en bildfil och skapar en texture direkt från den.

```csharp
Texture2D goombaTexture = Raylib.LoadTexture(@"goomba.png");
```

### LoadTextureFromImage()

Skapar en ny texture baserat på en [Image](texture.md#image).

```csharp
Texture2D heroTexture = Raylib.LoadTextureFromImage(originalImage);
```

Detta är alltså motsatsen till [LoadImageFromTexture()](image.md#loadimagefromtexture).

## Rita ut till skärmen

### DrawTexture()

Ritar ut en texture till fönstret.

```csharp
// Ritar texturen heroTexture till fönstret, på x-position 40 och 
// y-position 300, utan infärgning (WHITE färgar inte)
Raylib.DrawTexture(heroTexture, 40, 300, Color.WHITE)
```

### DrawTextureEx()

En lite mer avancerad version av DrawTexture, som dels använder en vektor för att ange x och y-värden, dels låter oss ange rotation och skalning av texturen.

```csharp
// Ritar texturen heroTexture till fönstret, på x-position 40 och 
// y-position 300, utan infärgning (WHITE färgar inte)
// Använd skalning 0.5 och rotation 0.
Vector2 position = new Vector2(40, 300);
Raylib.DrawTexture(heroTexture, position, 0, 0.5f, Color.WHITE)
```

{% hint style="info" %}
**OBSERVERA:** För att kunna använda [Vector2 ](../../../grundlaeggande/vektorer-numerics.md)så måste du lägga in detta bland dina using-statements:

```csharp
using System.Numerics;
```
{% endhint %}

### SetTextureFilter()

I vanliga fall när man ritar ut en texture i en annan storlek än den är från början så skalas den med interpolering – den hittar på mjuka övergångar mellan originalpixlarna. Det fungerar bra för foton och liknande, men sämre för pixelart.

```csharp
// Bestäm att texturen heroTexture ska skalas med "point"-filter, som ger skarp
// pixelart - ingen interpolering.
Raylib.SetTextureFilter(heroTexture, TextureFilter.TEXTURE_FILTER_POINT);
```

### DrawTexturePro()

En ännu mer avancerad version av DrawTexture. Här används två rektanglar, en vektor och en float för att ange vilken del av texturen som ska klippas ut, var den ska placeras och med vilka proportioner, kring vilken punkt den ska roteras och hur mycket den ska roteras.

Det här kan man bland annat använda sig av när man har en bild som är ett s.k. sprite sheet, där alla bildrutor i en karaktärs animation finns med. Man behöver då inte klippa upp animationen i en massa olika bildfiler utan kan istället använda DrawTexturePro för att kopiera en del av bilden till raylibfönstret i taget.

Bilden nedan visar principen:

![](../../../.gitbook/assets/DrawTexturePro.png)

DrawTexturePro kan också användas för vanliga texturer, som man vill rita ut roterade. Nedan är kod som ritar ut en textur som från början är 200×200 pixlar stor till Raylibfönstret.

{% tabs %}
{% tab title="C#" %}
```csharp
Raylib.DrawTexturePro(
  texture, 
  new Rectangle(0,0,200, 200), // Source
  new Rectangle(200,200,200,200), // Dest(ination)
  new Vector2(100,100), // Origin
  rotation,
  Color.WHITE );
```
{% endtab %}
{% endtabs %}
