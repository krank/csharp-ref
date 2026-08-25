# Loopar

## while-loop

Fungerar och ser ut som en [if-sats](if-satser.md) utom att körningen inte fortsätter när kodblocket körts, utan "hoppar upp" till kriteriet och testar det igen.

Precis som med if-satserna ska det som är mellan paranteserna vara kod som ger [boolskt](datatyper/#bool) resultat t.ex. en [jämförelse ](operatorer.md#boolska)eller en metod som [returnerar ](metoder.md#returnering)ett boolskt värde.

While-loopar används när man **inte vet** hur många gånger loopen ska köras. Till exempel:

{% code lineNumbers="true" %}
```csharp
string name = "";

// Körs så många gånger som behövs för att 
// användaren ska förstå att hen ska skriva "Micke"
while (name != "Micke")
{
  Console.WriteLine("Skriv ditt namn:")
  name = Console.ReadLine();
}
```
{% endcode %}

## for-loop

Fungerar som en while-loop men har alltid en räknare – bra när man vill göra något ett visst antal gånger. Samlar deklaration av räknare, kriterie för att fortsätta loopa och förändring av räknarens värde på samma ställe.

{% code lineNumbers="true" %}
```csharp
// i är räknarvariabeln, vars värder börjar på 0
// i < 10 är villkoret; så länge det utvärderas som sant fortsätter loopen köras
// i++ körs i slutet av varje iteration, och betyder att i ökar med 1 varje gång

for (int i = 0; i < 10; i++)
{
  Console.WriteLine(i);
}
```
{% endcode %}

For-loopar används när man **vet** hur många gånger loopen ska köras – åtminstone när man når den. Så länge en räknare ska användas fungerar en for-loop bra.

## Nästlad for-loop

En teknik som ofta används för att göra till exempel rutnät eller andra 2d-grejer.

```csharp
for (int y = 0; y < 5; y++)
{
  for (int x = 0; x < 5; x++)
  {
    Console.Write ("o ");
  }
  Console.WriteLine();
}
```

Resultatet av koden blir:

```
o o o o o
o o o o o
o o o o o
o o o o o
o o o o o
```

## foreach-loop

Foreach-loopar är i princip likadana som for-loopar men är specialdesignade för att gå igenom listor och arrayer. En foreach-loop körs lika många gånger som det finns saker i en lista/array, och varje gång loopen körs så lagras en av sakerna i variabeln som anges.

Nackdelen jämfört med en for-loop är att man inte får ut vilket index (plats i listan/arrayen) respektive sak har. Behöver man skriva ut index eller använda det på något vis är därför for-loop ett bättre val.

{% code lineNumbers="true" %}
```csharp
string[] choices = {"Start", "Options", "Quit"};

foreach (string choice in choices)
{
  Console.WriteLine(choice);
}
```
{% endcode %}

## Break

Används för att hoppa ur en loop.

```csharp
while (true)
{
  string name = Console.ReadLine();
  if (name == "Kalle")
  {
    break; // Hoppar ur loopen helt om name är "kalle" 
  }
}
```

## Continue

Används för att hoppa till nästa iteration av loopen.

```csharp
for (int i = 0; i < 10; i++)
{
  if (i == 5)
  {
    continue; // Skippar resten av iterationen; skriver alltså inte ut 5
  }
  Console.WriteLine(i)
}
```
