# Entity Framework Core\*

Entity Framework Core är ett ramverk som gör att man slipper skriva SQL-kommandon själv. EF fungerar som en mellanhand – vi kan säga åt EF hur datan som ska sparas ser ut och vad som ska göras med den, och EF förvandlar det till databaskommandon åt oss, och sköter interaktionen med databasen.

## Installation

Kör följande kommando för att installera EF-verktygen på din dator:

```powershell
dotnet tool install --global dotnet-ef
```

Lägg till NuGet-paketet Microsoft.EntityFrameworkCore till ditt projekt via [NuGet gallery](../../grundlaeggande/anvaenda-bibliotek-using.md#nuget-gallery) eller via [kommandot](../../grundlaeggande/anvaenda-bibliotek-using.md#nuget-via-terminalen):

```
dotnet add package Microsoft.EntityFrameworkCore
```

## DbContext

### OnConfiguring

### OptionsBuilder

### DbSet

## Migrations
