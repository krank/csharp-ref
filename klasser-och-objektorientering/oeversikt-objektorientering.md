# Översikt objektorientering

## Objekt

Ett objekt är en samling variabler, metoder och algoritmer som "hör ihop" och motsvarar en "sak" i programmet.

_Exempel på objekt: Ett svärd, en fiende, en bok, en bana, ett päron, en kund._

## Klass

En klass är en ritning, eller en mall, för en kategori av objekt. En klass är inte i sig ett objekt, utan bara en instruktion för hur ett objekt ska se ut och fungera.

_Exempel på klasser: Svärd, fiende, bok, bana, päron, kund._

En klass fungerar också som en datatyp, så varje gång kod förväntar sig en datatyp (t.ex. string eller int) kan man istället skriva dit en klass.

[Mer om klasser.](klasser-och-instanser.md#skapa-klasser-i-visual-studio-code)

## Instans

En instans är ett _objekt _man skapat utifrån en _klass_.

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

En klass kan ärva från en annan klass. Det betyder att subklassen får basklassens alla metoder och variabler, men den kan också lägga till egna.

Man brukar också beskriva det som att subklassen är en mer specialiserad version av basklassen – ett exempel på basklass kan vara `Weapon` och en subklass till Weapon kan då vara `Sword`. Sedan kan Sword agera basklass till `LongSword `och `ShortSword`.

Alla svärd är då vapen, och har alla metoder etc som ingår i vapen – fast de kan ha egna tillägg, och de kan också delvis fungera annorlunda (se Polymorfism).

## Inkapsling

## Interaktion mellan objekt

## Polymorfism

## Generiska klasser
