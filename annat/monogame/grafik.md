# Grafik\*

## Texture2D\*

Ett Texture2D-objekt är en tvådimensionell bild. Oftast skapas de genom att man laddar in resources som man tidigare förberett i [mcgb-editor.md](mcgb-editor.md "mention").

```csharp
Texture2D hero = Content.Load<Texture2D>("heroSprite");
```

Man kan också skapa nya Texture2Ds. När de skapas är de då helt tomma.

```csharp
// Skapa en Texture2D som är 1x1 i storlek
Texture2D pixel = new Texture2D(GraphicsDevice, 1, 1);
```

### SetData

För den som verkligen&#x20;

## SpriteBatch

2D-grafik i Monogame ritas ut med SpriteBatches. När man skapar ett nytt Monogame-projekt får man automatiskt en SpriteBatch-variabel i Game1-klassen:

```csharp
private SpriteBatch _spriteBatch;
```

Och den initieras och kopplas till sysyemets renderingssystem (GraphicsDevice) i LoadContent:

```csharp
protected override void LoadContent()
{
  _spriteBatch = new SpriteBatch(GraphicsDevice);
}
```

Därefter kan den användas i Draw() för att rita ut Texture2D-objekt till MonoGame-fönstret.

```csharp
protected override void Draw(GameTime gameTime)
{
  GraphicsDevice.Clear(Color.CornflowerBlue);

  _spriteBatch.Begin();
  _spriteBatch.Draw(pixel, rectangle, Color.Red);
  _spriteBatch.End();
    
  // ...
  base.Draw(gameTime);
}
```

### Begin()

Aktiverar en SpriteBatch och gör den redo för att börja rita ut sprites till skärmen.

```csharp
_spriteBatch.Begin();
```

### End()

Avslutar en SpriteBatch' ritande för den här bildrutan.

```csharp
_spriteBatch.End();
```

### Draw()

Ritar ut en Texture2D till skärmen. Första parametern är alltid den textur som ska ritas ut och den sista är den färg som texturen ska färgas med. Använd `Color.White` om du bara vill använda texturens normala färger.

```csharp
Rectangle rect = new (10,20,64,64);
Vector2 pos = new(100,20);

// Rita ut 'hero' och passa in den i rektangeln 'rect'
_spriteBatch.Draw(hero, rect, Color.White);

// Rita ut 'monster' på positionen som anges av vektorn 'pos'
_spriteBatch.Draw(monster, pos, Color.White);
```

Vill man bara rita ut en del av en Texture2D så kan man ange en extra rektangel som beskriver vilken del som ska klippas ut och visas.

```csharp
Rectangle rect = new (10,20,64,64);
Rectangle localRect = new(0,0,16,16);

// Rita ut den del av 'spritesheet' som finns inom 'localRect' och 
// passa in den i rektangeln 'rect'
_spriteBatch.Draw(spriteSheet, rect, localRect, Color.White);
```

Det finns även andra varianter av Draw() som inte dokumenteras här.
