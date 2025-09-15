# Namngivning

## Språk och "bra namn"

Namnen i ett projekt bör alla vara **på samma språk** och följa samma mönster.

Ett bra namn är tydligt och beskriver informationen variabeln innehåller, eller den handling metoden gör. "hitPoints" är ett bättre namn än "x".

| Kategori                                                                                        | Grundtanke                                          | Bra exempelnamn                                                                |
| ----------------------------------------------------------------------------------------------- | --------------------------------------------------- | ------------------------------------------------------------------------------ |
| <p><strong>Variabler</strong><br><strong>Parametrar</strong><br><strong>Properties</strong></p> | Den data som lagras                                 | <p>_hitPoints<br>movementX<br>hasBeenHit<br>weaponDamage<br>moneyOwed</p>      |
| **Metoder**                                                                                     | <p>Den handling som utförs<br>Ett <em>verb</em></p> | <p>CheckCollision<br>Draw<br>Update<br>LoadSavegame<br>ApplyMovementVector</p> |
| **Klasser**                                                                                     | Kategorinamn i singular                             | <p>Enemy<br>Level<br>Powerup<br>Button<br>Book</p>                             |

## PascalCase och camelCase

* **PascalCase:** Inga mellanslag mellan orden, stor bokstav (versal) i början av varje ord.
* **camelCase:** Inga mellanslag mellan orden, liten bokstav i början men i övrigt stor bokstav (versal) i början av varje ord.

### Exempel

<table><thead><tr><th width="242.2047984048375">Typ</th><th width="150">Modell</th><th width="352.26099094514075">Exempel</th></tr></thead><tbody><tr><td><strong>Projekt</strong></td><td>PascalCase</td><td><p>SpaceShooter</p><p>PacMan</p><p>BreakoutClone</p></td></tr><tr><td><a href="egna-metoder.md"><strong>Metoder</strong></a></td><td>PascalCase</td><td><p>TakeDamage()</p><p>RestoreOriginalPosition()</p><p>Rest()</p></td></tr><tr><td><a href="../klasser-och-objektorientering/klasser-och-instanser.md"><strong>Klasser</strong></a></td><td>PascalCase</td><td><p>Enemy</p><p>ProjectileTarget</p><p>PowerupBox</p></td></tr><tr><td><a href="../klasser-och-objektorientering/inkapsling-och-properties.md"><strong>Properties</strong></a></td><td>PascalCase</td><td>HitPoints</td></tr><tr><td><strong>Klassvariabler:</strong> <br><strong>public, protected</strong></td><td>PascalCase</td><td>IsAlive</td></tr><tr><td><strong>Klassvariabler: private</strong></td><td>camelCase</td><td>_hitPoints</td></tr><tr><td><strong>Lokala variabler</strong><br><strong>("vanliga variabler")</strong></td><td>camelCase</td><td><p>hitPoints</p><p>mana</p><p>isFloating</p></td></tr><tr><td><strong>Parametrar</strong></td><td>camelCase</td><td><p>name</p><p>movementVector</p></td></tr></tbody></table>

## Understreck

Understreck används i början av [privata/protected](../klasser-och-objektorientering/public-private-och-protected.md) variabler i [klasser](../klasser-och-objektorientering/klasser-och-instanser.md), och _ingen annanstans._

```csharp
public class Fighter
{
  private int _hp;
  protected int _mana;
  public int ShoeSize;
  public int Level { get; protected set; }
}
```
