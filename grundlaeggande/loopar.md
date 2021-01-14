# Loopar

## while-loop

Fungerar och ser ut som en if-sats utom att körningen inte fortsätter när kodblocket körts, utan "hoppar upp" till kriteriet och testar det igen.

```csharp
int i = 10;
while (i > 0)
{
  Console.WriteLine(i);
  i--;
}
```

Används när man inte vet hur många gånger loopen ska köras. Till exempel:

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

## for-loop

Fungerar som en while-loop men har alltid en räknare – bra när man vill göra något ett visst antal gånger. Samlar deklaration av räknare, kriterie för att fortsätta loopa och förändring av räknarens värde på samma ställe.

```csharp
// i är räknarvariabeln, vars värder börjar på 0
// i < 10 är villkoret; så länge det utvärderas som sant fortsätter loopen köras
// i++ körs i slutet av varje iteration, och betyder att i ökar med 1 varje gång

for (int i = 0; i < 10; i++)
{
  Console.WriteLine(i);
}
```

## foreach-loop

Foreach-loopar är i princip likadana som for-loopar men är specialdesignade för att gå igenom listor och arrayer. En foreach-loop körs lika många gånger som det finns saker i en lista/array, och varje gång loopen körs så lagras en av sakerna i variabeln som anges.

```csharp
string[] choices = {"Start", "Options", "Quit"};

foreach (string choice in choices)
{
  Console.WriteLine(choice);
}
```

