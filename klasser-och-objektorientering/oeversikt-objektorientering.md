# Översikt objektorientering

## Objekt

Ett objekt är en samling variabler, metoder och algoritmer som "hör ihop" och motsvarar en "sak" i programmet.

_Exempel på objekt: Ett svärd, en fiende, en bok, en bana, ett päron, en kund._

## Klass

En klass är en ritning, eller en mall, för en kategori av objekt. En klass är inte i sig ett objekt, utan bara en instruktion för hur ett objekt ska se ut och fungera.

_Exempel på klasser: Svärd, fiende, bok, bana, päron, kund._

En klass fungerar också som en datatyp, så varje gång kod förväntar sig en datatyp \(t.ex. string eller int\) kan man istället skriva dit en klass.

[Mer om klasser.](klasser-och-instanser.md#skapa-klasser-i-visual-studio-code)

## Instans

En instans är ett _objekt_ man skapat utifrån en _klass_.

[Mer om instanser.](klasser-och-instanser.md#skapa-klasser-i-visual-studio-code)

## Klassvariabler och klassmetoder

En klassvariabel är en variabel som ingår i en klass, och en klassmetod är en metod som ingår i en klass.

Alla instanser av en klass får tillgång till alla klassens metoder och egen kopia av alla klassens variabler.

_Exempel:_

```csharp
class Pear
{
  public int cost = 100; // <-- klassvariabel
  public bool eaten = false; // <-- klassvariabel
  public void Eat() // <- klassmetod
  {
    eaten = true;
  }
}
```

## Arv

## Inkapsling

## Interaktion mellan objekt

## Polymorfism

## Generiska klasser

