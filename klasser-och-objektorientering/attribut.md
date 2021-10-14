# Attribut

Attribut används för att säga saker _om_ klassvariabler, properties och metoder. Med andra ord är de ett slags _metadata _– information om information.

De används en hel del när man konstruerar controllers till REST-servrar, och när man jobbar med JSON-serialisering.

Man skriver attribut mellan hakparenteser `[]` innan det attributet ska gälla.

```csharp
using System.Text.Json.Serialization;

public class Pokemon
{
  public string Name {get; set;}
  public bool IsDefault {get; set;}
  
  [JsonIgnore]
  public int CurrentHp {get; set;}
}
```



