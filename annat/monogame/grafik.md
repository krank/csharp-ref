# Grafik\*

## Texture2D\*

## SpriteBatch\*

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

Därefter kan den användas i Draw() för att rita ut Texture2D-objekt till MonoGame-fönstret. Begin() aktiverar Sprite

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
