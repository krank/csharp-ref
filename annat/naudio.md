# NAudio

NAudio är ett bibliotek för att spela upp ljud, och som funkar i konsolen.

## Setup

Lägg till [NAudio](https://www.nuget.org/packages/NAudio/) via [NuGet Gallery](../grundlaggande/anvaenda-bibliotek-using.md#nuget-gallery).

Lägg till de ljudfiler du vill använda i din csproj som [resursfiler](../filhantering/resursfiler.md).

```xml
<ItemGroup>
  <Content Include="music\*.mp3" CopyToOutputDirectory="Always" />
</ItemGroup>
```

Skriv `using NAudio.Wave` högst upp i ditt program.

## Komplett exempel

```csharp
using NAudio.Wave;

AudioFileReader reader = new AudioFileReader("music/BitBitLoop.mp3");
WaveOutEvent output = new();

output.Init(reader);
output.Play();

while (output.PlaybackState == PlaybackState.Playing)
{
  Thread.Sleep(100);
}
```

## AudioFileReader

En klass som används för att läsa in ljudfiler. Varje instans av AudioFileReader är kopplad till en specifik ljudfil, som bestäms när instansen skapas.

### currentTime

En [TimeSpan](../grundlaggande/datum-och-tid.md#timespan) som beskriver var i ljudfilen uppspelningen är just nu.

```csharp
while (output.PlaybackState == PlaybackState.Playing)
{
  Thread.Sleep(100);
  Console.WriteLine(reader.CurrentTime);
}
```

## WaveOutEvent

En klass som används för att spela upp ljudfiler.

### Init()

Initierar objektet med en källa till ljuddata (ofta en AudioFileReader).

```csharp
AudioFileReader reader = new AudioFileReader("music/BitBitLoop.mp3");
WaveOutEvent output = new();
output.Init(reader);
```

### Play()

Påbörjar uppspelningen.

```csharp
output.Play();
```

### Pause()

Pausar uppspelningen

```csharp
output.Pause();
```

### Stop()

Stoppar uppspelningen

```csharp
output.Stop();
```

### PlaybackState()

Läser av WaveOutEventets nuvarande läge. Resultatet kommer att vara någon av `PlaybackState.Playing`, `PlaybackState.Stopped` och `PlaybackState.Paused`.

```csharp
while (output.PlaybackState == PlaybackState.Playing)
{
  Thread.Sleep(100);
  Console.WriteLine(reader.CurrentTime);
}
```

