# JSON

JSON är Javascript Object Notation, så för den som är van vid Javascript kanske det ser bekant ut.

## Datatyper

Det finns fem datatyper i JSON:

* **string** – "test"
* **number** – 42
* **bool** – true
* **array** – \[]
* **object** – {}

## Objekt och egenskaper

Objekt kan innehålla **egenskaper**. Varje egenskap har ett **namn** och ett **värde**. Värdet är en av de fem datatyperna. Egenskapsnamnen är **strings**. Man separerar egenskaperna från varandra med **kommatecken**, och separerar egenskapsnamn från egenskapsvärde med **kolon**.

```json
{
  "name": "Albert",
  "age": 3000
}
```

En egenskap kan ha ett objekt som värde:

```json
{
  "name": "Albert",
  "age": 3000,
  "weapon": {
    "name": "Sword",
    "damage": 300
  }
}
```

## Arrayer

(Kommer…)
