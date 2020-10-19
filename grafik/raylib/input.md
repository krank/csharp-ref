# Input

## Tangentbordet

### IsKeyDown

Tar emot en tangent som parameter; returnerar true om den angivna tangenten är nedtryckt – false om den inte är det.

Under KeyboardKey finns variabler för i princip alla tangenter på tangentbordet.

```csharp
if (Raylib.IsKeyDown(KeyboardKey.KEY_LEFT))
{
  // Kodlogik
}
```

### IsKeyUp

Fungerar som IsKeyDown fast… tvärtom

```csharp
if (Raylib.IsKeyUp(KeyboardKey.KEY_LEFT))
{
  // Kodlogik
}
```

## Musen

### GetMouseX, GetMouseY

Hämtar musens nuvarande position i form av integervärden i x- respektive y-led.

```csharp
int mouseX = Raylib.GetMouseX();
int mouseY = Raylib.GetMouseY();
```

### IsMouseButtonDown

Anropas med en musknapp som parameter; returnerar true om den musknappen just nu är nedtryckt.

```csharp
bool leftDown = Raylib.IsMouseButtonDown(MouseButton.MOUSE_LEFT_BUTTON);
bool rightDown = Raylib.IsMouseButtonDown(MouseButton.MOUSE_RIGHT_BUTTON);
```

### IsMouseButtonPressed

Anropas med en musknapp som parameter; returnerar true om den musknappen tryckts ned någon gång sedan förra gången metoden anropades.

```csharp
bool leftWasPressed = Raylib.UsMouseButtonPressed(MouseButton.MOUSE_LEFT_BUTTON);
```

