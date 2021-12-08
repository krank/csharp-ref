# Namngivning

## Språk och "bra namn"

Ett bra namn är tydligt och beskriver informationen variabeln innehåller, eller den handling metoden gör. "hitPoints" är ett bättre namn än "x".

\[Fler exempel kommer]

Namnen i ett projekt bör alla vara **på samma språk** och följa samma mönster.

## PascalCase och camelCase

* **PascalCase:** Inga mellanslag mellan orden, stor bokstav (versal) i början av varje ord.
* **camelCase:** Inga mellanslag mellan orden, liten bokstav i början men i övrigt stor bokstav (versal) i början av varje ord.

### Exempel

| Typ                         | Modell     | Exempel                                                          |
| --------------------------- | ---------- | ---------------------------------------------------------------- |
| **Projekt**                 | PascalCase | <p>SpaceShooter</p><p>PacMan</p><p>BreakoutClone</p>             |
| **Metoder**                 | PascalCase | <p>TakeDamage()</p><p>RestoreOriginalPosition()</p><p>Rest()</p> |
| **Variabler**               | camelCase  | <p>hitPoints</p><p>mana</p><p>isFloating</p>                     |
| **Parametrar**              | camelCase  | <p>name</p><p>movementVector</p>                                 |
| **Klasser**                 | PascalCase | <p>Enemy</p><p>ProjectileTarget</p><p>PowerupBox</p>             |
| **Klassvariabler: publika** | PascalCase | IsAlive                                                          |
| **Klassvariabler: privata** | camelCase  | hitPoints                                                        |
| **Properties**              | camelCase  | HitPoints                                                        |

