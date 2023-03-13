# SQLite-kommandon\*

## CREATE TABLE

Skapar en tabell.&#x20;

```sql
CREATE TABLE users (
	id INTEGER PRIMARY KEY AUTOINCREMENT,
	name TEXT NOT NULL,
	password TEXT NOT NULL,
	email TEXT NOT NULL
);
```

Ovanstående skapar tabellen **users** med kolumnerna **id**, **name**, **password** och **email**.

* **INTEGER** betyder att kolumnen bara kan innehålla siffror, på samma sätt som en integer-variabel i C#..
* **TEXT** betyder att kolumnen bara kan innehålla text, lite som en string.
* **PRIMARY KEY** betyder att det är värdet i den kolumnen som är unikt och används för att identifiera varje rad.
* **AUTOINCREMENT** betyder att om man lägger till en rad i tabellen utan att ange ett värde för denna kolumn så ges den ett automatiskt nytt värde.
* **NOT NULL** betyder att man inte får lämna kolumnen tom.

| id🔑 | name | password | email |
| ---- | ---- | -------- | ----- |
|      |      |          |       |

## INSERT INTO

Lägger till en rad i en tabell.

```
INSERT INTO users (name,password,email)
VALUES('Mikael Bergström','12345','fake@bullshit.com');
```

Ovanstående stoppar in en rad i tabellen **users**.

* **(name,password,email)** betyder att det är de tre kolumnerna som värden ska stoppas in i.
* **VALUES('Mikael Bergström','12345','fake@bullshit.com')** betyder att texten "Mikael Bergström" läggs in i den första angivna kolumnen (name), "12345" läggs in i den andra kolumnen (password) och att "fake@bullshit.com" läggs in i den tredje (email).

En av tabellens fyra kolumner, "id", anges inte och får inget värde. Eftersom den är AUTOINCREMENT får den ändå ett värde, automatiskt.

| id🔑 | name             | password | email             |
| ---- | ---------------- | -------- | ----------------- |
| 0    | Mikael Bergström | 12345    | fake@bullshit.com |

## SELECT

Hämtar data från en tabell

```
SELECT * FROM users
```

Ovanstående hämtar alla rader och alla kolumner från tabellen.

```
SELECT name,email FROM users
```

Ovanstående hämtar alla rader, men bara kolumnerna **name** och **email**.

### WHERE

Gör att man kan vara mer specifik med vilken eller vilka rader man vill läsa av.

```
SELECT name,email FROM users WHERE id=0
```

Ovanstående hämtar bara kolumnerna name och email, och bara de rader där kolumnen id har värder 0.

## DELETE

## UPDATE

```csharp

  INSERT INTO
  WHERE
  FROM
  SELECT
  DELETE
  UPDATE

  Avancerat
    INNER JOIN
    ALTER TABLE
    DROP TABLE
```
