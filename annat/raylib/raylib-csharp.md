# Raylib-CSharp\*

Raylib är från början ett bibliotek till C++, och Raylib-cs är inte det enda sättet att koppla Raylib till C#. **Raylib-CSharp** är ett annat paket, som funkar delvis annorlunda.

## Separata bibliotek

Raylib-CSharp är mer uppdelat än Raylib-cs. Varje kategori av funktioner har sitt eget bibliotek, som man måste inkludera via [using](../../grundlaeggande/anvaenda-bibliotek-using.md).

```csharp
using System.Numerics;
using Raylib_CSharp.Colors;
using Raylib_CSharp.Rendering;
using Raylib_CSharp.Windowing;

Window.Init(800, 600, "Hello");

Vector2 position = new (400, 300);

while (!Window.ShouldClose())
{
  Graphics.BeginDrawing();
  Graphics.ClearBackground(Color.Green);

  Graphics.DrawCircleV(position, 40, Color.Black);

  Graphics.EndDrawing();
}
```

## Funktioner



| Raylib-cs                | Raylib-CSharp            | Bibliotek      |
| ------------------------ | ------------------------ | -------------- |
| Raylib.InitWindow        | Window.Init              | Windowing      |
| Raylib.SetTargetFPS      | Time.SetTargetFPS        | Raylib\_CSharp |
| Raylib.WindowShouldClose | Window.ShouldClose       | Windowing      |
| Raylib.BeginDrawing      | Graphics.BeginDrawing    | Rendering      |
| Raylib.EndDrawing        | Graphics.EndDrawing      | Rendering      |
| Raylib.ClearBackground   | Graphics.ClearBackground | Rendering      |
| Raylib.DrawRectangle     | Graphics.DrawRectangle   | Rendering      |
| Raylib.DrawCircle        | Graphics.DrawCircle      | Rendering      |
| Raylib.DrawLine          | Graphics.DrawLine        | Rendering      |
|                          |                          |                |

Varianter av funktionerna – DrawRectangleRec, DrawRectangleLines osv finns såklart också.

## Datatyper

| Struct    | Bibliotek       |
| --------- | --------------- |
| Rectangle | Transformations |
| Color     | Colors          |
| Texture   | Textures        |
| Image     | Images          |

