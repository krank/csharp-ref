# String-manipulering

En string är i C# alltid oföränderlig; man kan inte ändra direkt i en string. Men man kan använda olika metoder för att skapa **nya versioner** av existerande strings.

## Replace()

Byter ut ett tecken eller en del-string.

```csharp
string oldString = "Mikael är min programmeringslärare";

string newString = oldString.Replace("Mikael", "Micke");
```

## Substring()

Returnerar en del av stringen. Tar emot startposition och längd som parametrar. Anges bara en parameter så antas längden vara resten av stringen.

```csharp
string oldstring = "Detta är en string";

string sub1 = oldString.Substring(2,5); // sub1 blir "tta ä"

string sub2 = oldString.Substring(2); // sub2 blir "tta är en string"
```

## Trim()

Returnerar en kopia av stringen där mellanslag och andra "tomma" tecken tagits bort från början och slutet.

```csharp
string clean = oldString.Trim();
```

Det finns också `TrimEnd` och `TrimStart` ifall man bara vill trimma slutet eller början av stringen.

## Insert()

Returnerar en kopia av stringen där en annan string stoppats in på en angiven plats. Tar emot en position och en string som parametrar.

```csharp
string folk = "micke och kim och mimmi";

string nyFolk = folk.insert(5, " och herbert"); 
// nyFolk blir "micke och herbert och kim och mimmi"
```

## Contains()

Kollar om en string innehåller en annan string, t.ex. ifall "haj" finns i texten "en haj hoppar över en björn". Returnerar true om den finns, false om den inte gör det.

```csharp
string answer = Console.ReadLine();
bool hasAShark = answer.Contains("haj");

if (hasAShark == true)
{
  Console.WriteLine("Du skrev något med ordet haj!");
}
```

## IndexOf()

Returnerar positionen för den första plats i stringen där en annan string finns. Tar emot något att söka efter som parameter.

```csharp
string folk = "micke och kim och mimmi";
int kimPlats = folk.IndexOf("kim");
int mellanslagPlats = folk.IndexOf(" ");
```

Resultatet av ovanstående blir att variabeln kimPlats får värdet 10 och att mellanslagPlats får värdet 5. Positionssiffrorna börjar på 0.

## Stora och små bokstäver

### ToUpper()

Returnerar en kopia av stringen där alla gemener (små bokstäver) bytts ut mot versaler (stora bokstäver).

```csharp
string caps = oldString.ToUpper();
```

### ToLower()

Returnerar en kopia av stringen där alla versaler (stora bokstäver) bytts ut mot gemener (små bokstäver).

```csharp
string small = oldString.ToLower();
```

Denna används ofta för att till exempel förvandla strings man fått in från en användare så att det inte spelar någon roll ifall hen svarat t.ex. JA, Ja, jA eller ja.

## Sätta ihop och ta isär

### String.Join()

Sätter ihop alla element i en array till en string. Tar emot två parametrar; en separator som placeras mellan elementen och en array med de element som ska sättas ihop.

```csharp
string[] names = {"micke", "kim", "mimmi"};
string folk = String.Join(" och ", names);
```

Resultatet av ovanstående blir en string som heter folk och som innehåller följande:

```csharp
"micke och kim och mimmi"
```

### Split()

Returnerar en array som består av en uppdelad string. Tar emot en separator som parameter. Separatorn kan bara vara ett ensamt tecken, en **char**.

```csharp
string folk = "micke och kim och mimmi";
string[] names = folk.Split(' ');
```

Resultatet av ovanstående blir en string-array med följande innehåll:

```csharp
{"micke", "och", "kim", "och", "mimmi"}
```
