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

## Modellen

Skapa en klass för varje typ av objekt som ska lagras i databasen. Det enda som lagras i databasen är klassernas [properties](../../klasser-och-objektorientering/inkapsling-och-properties.md#properties). Tillsammans bildar alla dessa klasser "modellen" för databasen.

```csharp
public class User
{
  public int UserId { get; set; }
  public string Username { get; set; } = "";
  public string Password { get; set; } = "";
}
```

Tabellen som skapas för att lagra användare kommer att döpas till samma sak som klassen plus en plural-ändelse (Users). Som primärnyckel används första bästa property som antingen heter Id eller klassens namn plus Id.&#x20;

## DbContext

En klass som representerar kopplingen till en databas, och som kommunikationen med database sker genom. Detta kallas en databas-kontext.

Man skapar en egen databaskontext, med egna inställningar, genom att skapa en klass som ärver från DbContext.

```csharp
public class DatabaseContext : DbContext
{
  public DbSet<User> Users { get; set; }

  protected override void OnConfiguring (DbContextOptionsBuilder optionsBuilder)
  {
    optionsBuilder.UseSqlite("Data Source=ef_users.sqlite");
  }
}
```

### DbSet

Varje klass som ingår i modellen läggs in som en DbSet-property i klassen som ärver från DbContext.

```csharp
public class DatabaseContext : DbContext
{
  public DbSet<User> Users { get; set; }
  public DbSet<Group> Users { get; set; }
  public DbSet<Post> Users { get; set; }
}
```

### OnConfiguring

För att göra egna inställningar i databas-kontexten, gör en [override ](../../klasser-och-objektorientering/polymorfism/virtual-override.md)av basklassens OnConfiguring-metod.

```csharp
protected override void OnConfiguring (DbContextOptionsBuilder optionsBuilder)
{
  optionsBuilder.UseSqlite("Data Source=ef_users.sqlite");
}
```

Objektet optionsbuilder används sedan för att göra diverse inställningar. Den viktigaste här är UseSqlite, som gör att databaskontexten kommer att kopplas till en SqLite-databas. Där anges också databasens filnamn.

## Migrations

Migrations används för att antingen generera en databasfil från klasser eller tvärtom. När man genererar en databas utifrån klasser kallas det att man arbetar "code first".

För att skapa och köra migrations behöver man använda **terminalen**, och man behöver vara i samma mapp som csproj-filen. I Visual Studio Code kan man med andra ord behöva byta till den mappen, t.ex:

```powershell
PS C:\Programming\EFDemo> cd EFDemo
PS C:\Programming\EFDemo\EFDemo>
```

### Skapa en migration

En migration är, lite förenklat, en _databasförändring_. Det betyder att man gör en stor migration i början när man först skapat sin modell, och sedan kan göra förändringar i form av fler migrationer i efterhand.

```powershell
dotnet ef migrations add CreateDB
```

I exemplet ovan skapas en migration med namnet CreateDB. Alla migrationer behöver ha ett unikt namn. Namnet bestämmer man själv, men undvik mellanslag.

### Uppdatera databasen

När en ny migration skapats behöver databasen uppdateras.

<pre class="language-powershell"><code class="lang-powershell"><strong>dotnet ef database update
</strong></code></pre>

Om modellen uppdateras behöver alltså en ny migration skapas och därefter behöver databasen uppdateras.

## Hämta data

### Where() och Linq

### FromSql()

### Include()

## Modifiera data

### Stoppa in data

### Modifiera data

### Ta bort data

