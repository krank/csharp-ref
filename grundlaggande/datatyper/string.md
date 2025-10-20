# String

En string är en text – en serie tecken efter varandra.

```csharp
string s = "Hello";
```

## $ – interpolation

Om man skriver $ framför en string, så kan man sedan stoppa in variabler och metodanrop och annat inuti måsvingar i stringen. Det som står innanför måsvingarna _utvärderas_ och blir en del av stringen.

```csharp
int hp = 100;
string s = $"Du har {hp} hit points kvar";
```

Om man har ett decimaltal ([float](./#float) eller [double](./#double)) så kan man skriva : och sedan ett format med t.ex. antal decimaler.

```csharp
float c = 23;
float f = 32 + (c * 1.8f);
Console.WriteLine($"Fahrenheit: {f:00.00}");
```

## ToLower()

En metod som är inbyggd i alla strings, och ger en kopia av stringen där alla stora bokstäver bytts ut mot små.

```csharp
string name = "Micke";
string nameSmall = name.ToLower(); // värdet i nameSmall blir "micke".
```

Detta är praktiskt när man t.ex. vill göra jämförelser och det inte ska spela någon roll ifall användaren skriver med stor bokstav.

## Length

Length är en egenskap alla strings har. Det är en int som innehåller det antal tecken stringen har.

```csharp
Console.WriteLine($"Texten {s} har {s.Length} tecken");
```

## `\` – specialtecken

Om man skriver `\` i en string så kommer tecknet efter att tolkas som ett specialtecken. Det vanligaste är `\n`, som är en newline (ny rad).

```csharp
Console.WriteLine("Detta är första raden.\nDetta är andra raden.");
```

## `"""` – raw strings

Väldigt praktiskt för ASCII-art och andra strings som har flera rader.

Om man använder tre citattecken före och efter en string:

* Alla tecken inklusive `"` och `\` tolkas som vanliga tecken snarare än kommandon.
* Framför allt den avslutande `"""` måste vara på en egen ny rad
* Ingen rad i stringen får börja längre åt vänster än den avslutande `"""`.
* Indraget för sista """ anger var alla raderna anses "börja", så även om hela stringen har ett indrag på 8 mellanslag så kommer den skrivas ut med 2 mellanslags indrag om den avslutande """ är indragen 6 mellanslag.
* Man kan fortfarande använda `$` och `{}` för att infoga variabler.

```csharp
Console.WriteLine("""
          _  .   .   .
        .' '; '-' '-'|-.
      (     '------.'  )
        ;            \ /
        :     '   ' |/
        '._._       \    .;
        .-'   ;--.    '--' /
      /      \-'---.___.'
      |     / 7 \(>o<) /\
      |     | \ |  . \   \
      |=====|   |  .  \ |-)
      |-'-'   ./_.-._.\|"
      '-.----'        |
        |       |     |
        |     | |   | |
        |_____|_|___|_|
        (-------',----'.
          '-'-----'-----'         
    """);
```

## `@` – verbatim strings

Om man skriver @ framför en string, så kommer varje tecken i denna string sedan att tolkas väldigt bokstavligt. Framför allt används detta när man inte vill att \ ska tolkas, utan bara skrivas ut som just \\. Det är praktiskt när man ska göra sökvägar i Windows.

```csharp
Console.WriteLine(@"Detta är första raden.\nDetta är också första rader.");
```

## String-metoder

### Replace()

Byter ut ett tecken eller en del-string.

{% code lineNumbers="true" %}
```csharp
string oldString = "Mikael är min programmeringslärare";

string newString = oldString.Replace("Mikael", "Micke");
```
{% endcode %}

### Substring()

Returnerar en del av stringen. Tar emot startposition och längd som parametrar. Anges bara en parameter så antas längden vara resten av stringen.

{% code lineNumbers="true" %}
```csharp
string oldstring = "Detta är en string";

string sub1 = oldString.Substring(2,5); // sub1 blir "tta ä"

string sub2 = oldString.Substring(2); // sub2 blir "tta är en string"
```
{% endcode %}

### Trim()

Returnerar en kopia av stringen där mellanslag och andra "tomma" tecken tagits bort från början och slutet.

```csharp
string clean = oldString.Trim();
```

Det finns också `TrimEnd` och `TrimStart` ifall man bara vill trimma slutet eller början av stringen.

### Insert()

Returnerar en kopia av stringen där en annan string stoppats in på en angiven plats. Tar emot en position och en string som parametrar.

{% code lineNumbers="true" %}
```csharp
string folk = "micke och kim och mimmi";

string nyFolk = folk.insert(5, " och herbert"); 
// nyFolk blir "micke och herbert och kim och mimmi"
```
{% endcode %}

### Contains()

Kollar om en string innehåller en annan string, t.ex. ifall "haj" finns i texten "en haj hoppar över en björn". Returnerar true om den finns, false om den inte gör det.

{% code lineNumbers="true" %}
```csharp
string answer = Console.ReadLine();
bool hasAShark = answer.Contains("haj");

if (hasAShark == true)
{
  Console.WriteLine("Du skrev något med ordet haj!");
}
```
{% endcode %}

### IndexOf()

Returnerar positionen för den första plats i stringen där en annan string finns. Tar emot något att söka efter som parameter.

{% code lineNumbers="true" %}
```csharp
string folk = "micke och kim och mimmi";
int kimPlats = folk.IndexOf("kim");
int mellanslagPlats = folk.IndexOf(" ");
```
{% endcode %}

Resultatet av ovanstående blir att variabeln kimPlats får värdet 10 och att mellanslagPlats får värdet 5. Positionssiffrorna börjar på 0.

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

### Sätta ihop och ta isär

#### String.Join()

Sätter ihop alla element i en array till en string. Tar emot två parametrar; en separator som placeras mellan elementen och en array med de element som ska sättas ihop.

{% code lineNumbers="true" %}
```csharp
string[] names = {"micke", "kim", "mimmi"};
string folk = String.Join(" och ", names);

// Variabeln "folk" får namnet "micke och kim och mimmi"
```
{% endcode %}

#### Split()

Returnerar en array som består av en uppdelad string. Tar emot en separator som parameter. Separatorn kan bara vara ett ensamt tecken, en **char**.

{% code lineNumbers="true" %}
```csharp
string folk = "micke och kim och mimmi";
string[] names = folk.Split(' ');

// Variabeln "names" får innehållet {"micke", "och", "kim", "och", "mimmi"}
```
{% endcode %}

## En string är en array

I grunden är en string helt enkelt en [array ](../listor-och-arrayer.md#array)av [chars](./#char). Det betyder att man kan använda alla tekniker man normalt kan med arrayer – Length, indexering och ranges till exempel – även med strings

{% code lineNumbers="true" %}
```csharp
string name = "Mikael Bergström";

char firstChar = name[0]; // firstChar blir M

string firstPart = name[..6]; // firstPart blir "Mikael"
```
{% endcode %}

## All()

All() är en del av **Linq-biblioteket** så man måste först ha med `using System.Linq`. All har en [delegate ](../delegates.md)som parameter, och förväntar sig då en metod (eller ett lambda-uttryck) som tar emot en `char` och returnerar `true` eller `false`. All stoppar sedan i var och ett av stringens tecken in i den angivna metoden. Om resultatet för alla blir `true` så returnerar All också `true`.

```csharp
using System.Linq;

string s1 = "12345";
string s2 = "123a45;

bool b1 = s1.All(char.IsDigit); // b1 = true
bool b2 = s2.All(char.IsDigit); // b2 = false
```

