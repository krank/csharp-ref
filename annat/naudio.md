# NAudio

NAudio är ett bibliotek för att spela upp ljud, och som funkar i konsolen.

## Setup

Lägg till [**NAudio**](https://www.nuget.org/packages/NAudio/) via [NuGet Gallery](../grundlaggande/anvaenda-bibliotek-using.md#nuget-gallery). Lägg också till **NAudio.Wasapi** om du gör det här i ett konsolprojekt.

Lägg till de ljudfiler du vill använda i din csproj som [resursfiler](../filhantering/resursfiler.md).

```xml
<ItemGroup>
  <Content Include="music\*.mp3" CopyToOutputDirectory="Always" />
</ItemGroup>
```

Skriv högst upp i programmet:

```csharp
using NAudio.Wave
```

## Komplett exempel

```csharp
using NAudio.Wave;

AudioFileReader reader = new AudioFileReader("music/BitBitLoop.mp3");
WasapiPlayr player = new WasapiPlayrBuilder().Build();

player.Init(reader);
player.Play();

while (player.PlaybackState == PlaybackState.Playing)
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

## WasapiPlayer

En klass som används för att spela upp ljudfiler.

Finns bara om man lagt till NAudio.wasapi-paketet manuellt, eller ändrat i sin csproj så att ens `targetFramework` är `netXX-windows`, t.ex. så här:

```xml
<TargetFramework>net11.0-windows</TargetFramework>
```

Man skapar en WasapiPlayer-instans genom att först skapa en WasapiPlayerBuilder, och låta den skapa playern:

```csharp
WasapiPlayerBuilder builder = new WasapiPlayerBuilder();
WasapiPlayer player = builder.Build();
```

Eller kortare:

```csharp
WasapiPlayer player = new WasapiPlayerBuilder().Build();
```

### Init()

Initierar objektet med en källa till ljuddata (ofta en AudioFileReader).

```csharp
AudioFileReader reader = new AudioFileReader("music/BitBitLoop.mp3");
WasapiPlayer player = new WasapiPlayerBuilder().Build();
player.Init(reader);
```

### Play()

Påbörjar uppspelningen.

```csharp
player.Play();
```

### Pause()

Pausar uppspelningen

```csharp
player.Pause();
```

### Stop()

Stoppar uppspelningen

```csharp
player.Stop();
```

### PlaybackState()

Läser av WaveOutEventets nuvarande läge. Resultatet kommer att vara någon av `PlaybackState.Playing`, `PlaybackState.Stopped` och `PlaybackState.Paused`.

```csharp
while (player.PlaybackState == PlaybackState.Playing)
{
  Thread.Sleep(100);
  Console.WriteLine(reader.CurrentTime);
}
```

