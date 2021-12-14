# Namngivning

## Språk och "bra namn"

Namnen i ett projekt bör alla vara **på samma språk** och följa samma mönster.

Ett bra namn är tydligt och beskriver informationen variabeln innehåller, eller den handling metoden gör. "hitPoints" är ett bättre namn än "x".

| Kategori                                                                                        | Grundtanke                                          | Bra exempelnamn                                                                |
| ----------------------------------------------------------------------------------------------- | --------------------------------------------------- | ------------------------------------------------------------------------------ |
| <p><strong>Variabler</strong><br><strong>Parametrar</strong><br><strong>Properties</strong></p> | Den data som lagras                                 | <p>hitPoints<br>movementX<br>hasBeenHit<br>weaponDamage<br>moneyOwed</p>       |
| **Metoder**                                                                                     | <p>Den handling som utförs<br>Ett <em>verb</em></p> | <p>CheckCollision<br>Draw<br>Update<br>LoadSavegame<br>ApplyMovementVector</p> |
| **Klasser**                                                                                     | Kategorinamn i singular                             | <p>Enemy<br>Level<br>Powerup<br>Button<br>Book</p>                             |

## PascalCase och camelCase

* **PascalCase:** Inga mellanslag mellan orden, stor bokstav (versal) i början av varje ord.
* **camelCase:** Inga mellanslag mellan orden, liten bokstav i början men i övrigt stor bokstav (versal) i början av varje ord.

### Exempel

| Typ                                                                            | Modell     | Exempel                                                          |
| ------------------------------------------------------------------------------ | ---------- | ---------------------------------------------------------------- |
| **Projekt**                                                                    | PascalCase | <p>SpaceShooter</p><p>PacMan</p><p>BreakoutClone</p>             |
| **Metoder**                                                                    | PascalCase | <p>TakeDamage()</p><p>RestoreOriginalPosition()</p><p>Rest()</p> |
| **Klasser**                                                                    | PascalCase | <p>Enemy</p><p>ProjectileTarget</p><p>PowerupBox</p>             |
| **Properties**                                                                 | PascalCase | HitPoints                                                        |
| <p><strong>Klassvariabler:</strong> <br><strong>public, protected</strong></p> | PascalCase | IsAlive                                                          |
| **Klassvariabler: private**                                                    | camelCase  | hitPoints                                                        |
| **Lokala variabler**                                                           | camelCase  | <p>hitPoints</p><p>mana</p><p>isFloating</p>                     |
| **Parametrar**                                                                 | camelCase  | <p>name</p><p>movementVector</p>                                 |

