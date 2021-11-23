# Fönster i Raylib

## Skapa fönster

Att skapa ett nytt fönster för Raylib görs med en enkel kodrad:

```csharp
Raylib.InitWindow(800, 600, "Hello World");
```

800 är fönstrets bredd, 600 dess höjd, och "Hello World" är vad som kommer att stå i titeln.

## WindowShouldClose()

Returnerar False så länge användaren inte skickat signalen att fönstret borde stängas – till exempel genom att trycka på krysset.

Ett vanligt sätt att bygga spelets grund-loop är att använda denna ihop med en while-loop:

```csharp
while (!Raylib.WindowShouldClose())
{
  // Spelets logik
}
```

## Ett enkelt komplett exempel

I exemplet nedan initieras Raylib-fönstret. Sedan körs en loop så länge fönstret är öppet, och varje bildruta ritas först en vit bakgrund och sedan en magentafärgad cirkel.

```csharp
using Raylib_cs;

Raylib.InitWindow(800, 600, "The title of my window");
RayLib.SetTargetFPS(60);

while (!Raylib.WindowShouldClose())
{
  Raylib.BeginDrawing();
  
  Raylib.ClearBackground(Color.WHITE);
  
  Raylib.DrawCircle(100,100,100,Color.MAGENTA);
  
  Raylib.EndDrawing();
}
```
