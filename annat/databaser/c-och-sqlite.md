# C# och SQLite\*

Börja med att lägga till NuGet-paketet **Microsoft.Data.Sqlite**. Antingen genom att använda NuGet Gallery eller genom att köra i konsollen:

```powershell
dotnet add package Microsoft.Data.Sqlite
```

## SqliteConnection

En SqliteConnection är ett objekt som är kopplat till en SQLite-databasfil.

```csharp
SqliteConnection connection = new SqliteConnection("Data Source=users.sqlite")
connection.Open();
```

Det är ofta en bra idé att använda ett using-kodblock för att säkerställa att programmet inte håller kvar kopplingen längre än nödvändigt. Då stängs kopplingen ner säkert i samband med att using.kodblocket avslutas.

```csharp
using (SqliteConnection connection = new SqliteConnection("Data Source=users.sqlite"))
{
  connection.Open();
  // Kod som använder kopplings-objektet
}
```

### CreateCommand()

Skapar ett nytt SqliteCommand-objekt. Se nedan.

```csharp
SqliteCommand command = connection.CreateCommand();
```

## SqliteCommand

Ett SqliteCommand är ett objekt som motsvarar ett SQLite-kommando. Det har ett textinnehåll i form av själva kommandot, och kan köras på flera olika sätt. Ett SQLiteCommand är alltid kopplat till en SqliteConnection; kommandot skickas alltid till den SQLite-databasen.

### commandText

commandText är kommandotexten som ska köras mot databasen.

```csharp
command.CommandText =
  @"
    SELECT name
    FROM users
  ";
```

### ExecuteReader()

### ExecuteNonQuery()

### ExecuteScalar()

## SQLiteDataReader

### Read()

### Get

```csharp
 * SqliteConnection
 *   Open
 *   CreateCommand
 * SqliteCommand
 *   ExecuteReader
 *   ExecuteNonQuery
 *   ExecuteScalar
 * SQliteDataReader
 *   Read
 *   GetString / GetFloat / GetInt32 etc
```

