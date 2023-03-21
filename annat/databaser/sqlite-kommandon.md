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

```sql
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

```sql
SELECT * FROM users;
```

Ovanstående hämtar alla rader och alla kolumner från tabellen.

| id🔑 | name             | password | email                      |
| ---- | ---------------- | -------- | -------------------------- |
| 0    | Mikael Bergström | 12345    | fake@bullshit.com          |
| 1    | Jacob Marley     | money$   | moneyman@scroogemarley.com |

```sql
SELECT name,email FROM users;
```

Ovanstående hämtar alla rader, men bara kolumnerna **name** och **email**.

| name             | email                      |
| ---------------- | -------------------------- |
| Mikael Bergström | fake@bullshit.com          |
| Jacob Marley     | moneyman@scroogemarley.com |

### WHERE

Gör att man kan vara mer specifik med vilken eller vilka rader man vill läsa av.

```sql
SELECT name,email FROM users WHERE id=0;
```

Ovanstående hämtar bara kolumnerna name och email, och bara de rader där kolumnen id har värdet 0.

| name             | email             |
| ---------------- | ----------------- |
| Mikael Bergström | fake@bullshit.com |

### COUNT

Räknar antalet rader som innehåller ett värde.

```sql
SELECT COUNT(*) FROM users WHERE id=0;
```

## DELETE

Tar bort en eller flera rader från en tabell, baserat på ett eller flera kriterier.

```sql
DELETE FROM users WHERE id=0;
```

Kriterierna anges via WHERE, precis som för SELECT.

## UPDATE

Ändrar information i en eller flera celler, baserat på ett eller flera kriterier.

```sql
UPDATE users
SET email = 'deep@fake.com'
WHERE id=0;
```

Ovanstående kod ändrar email-kolumnens data till "deep@fake.com" för alla rader där id-kolumnen innehåller en nolla.

| id🔑 | name             | password | email                      |
| ---- | ---------------- | -------- | -------------------------- |
| 0    | Mikael Bergström | 12345    | deep@fake.com              |
| 1    | Jacob Marley     | money$   | moneyman@scroogemarley.com |

## Avancerat: Relationer

```csharp
    Avancerat
    INNER JOIN
    ALTER TABLE
    DROP TABLE
```
