# Databaser\*

(Kommer)

## Databas

En traditionell relationell databas består av ett antal tabeller. Varje tabell beskriver en kategori av saker. Det som gör databasen relationell är kopplingarna mellan tabellerna. Om man t.ex. har en tabell med användare, och en tabell med artiklar som användarna skrivit, så lagrar man inte användarnamnet etc för respektive användare i artikel-tabellen. Istället lagrar man användarens unika ID.

### Tabeller

En tabell innehåller data om en kategori av "saker" – man kan till exempel ha en tabell för användare, eller en tabell för highscores. En tabell består av ett antal kolumner och rader.

### Kolumner

Varje kolumn i en tabell beskriver någon egenskap hos de saker som tabellen beskriver. T.ex. kan en kolumn innehålla förnamn, efternamn, användarnamn, lösenord, etc. Varje kolumn ska helst bara innehålla EN kategori av värden, så att varje cell i tabellen i sin tur bara innehåller ETT värde.

### Rader

Varje rad i en tabell beskriver en "sak", till exempel en användare, en artikel, ett highscore eller ett datorspel. Rader kan också kallas **entries**.

### Primärnycklar

För att kunna identifiera en specifik entry i en tabell, behöver man vara säker på att det finns något unikt med varje rad. Den delen som är unik brukar kallas "primärnyckel". I teorin kan vilken kolumn eller kombination av kolumner som helst vara primärnyckel, men i de allra flesta fall ges bara varje entry ett unikt nummer, ett ID, som deklareras som primärnyckel.

### Normalisering

Normalisering kallas det när man följer ett antal regler designade att göra databasen så lätt att använda som möjligt. Till exempel försöker man att se till så att ingen data finns lagrad på flera ställen.
