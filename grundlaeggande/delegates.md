# Delegates

Delegates är ett sätt att kunna göra så att variabler pekar mot metoder istället för mot värden eller objekt i minnet.

```csharp
// Skapar en delegate som passar in på metoder som 
// inte tar emot några parametrar eller returnerar något.
delegate void Task(); 

// En metod som passar in på delegaten
static void SayHello() {
  System.Console.WriteLine("Hello!");
}

static void Main(string[] args)
{
  Task t = SayHello; // Lagra en referens till SayHello-metoden i "t"
  t(); // Att köra t som en metod är nu samma sak som att köra SayHello.
}
```

När man skapar en delegat så beskriver den en metodprofil. Man kan säga att varje delegat beskriver en **kategori** av metoder.

```csharp
// Stämmer in på metoder som tar emot en int-parameter och inte returnerar något.
delegate void DelegateOne(int y);

// Stämmer in på metoder som returnerar en int utan att ta emot några parametrar.
delegate int DelegateTwo();

// Stämmer in på metoder som returnerar en float efter att ha tagit emot
// en string och en int.
delegate float DelegateThree(string x, int y);
```

När man skapat sin delegat används den alltså som om den vore en datatyp. När man lagrar metoderna i den så ser man till att inte använda \(\) efter metodnamnet, för då körs ju metoden istället, innan tilldelningen.

```csharp
DelegateOne test = MethodOne;
```

### Dictionary med actions <a id="h.p_qt3ARehin8YT"></a>

Ett exempel på hur man kan använda delegater – Action är en delegat som ingår i C\# och som helt enkelt stämmer in på metoder som varken tar emot parametrar eller returnerar något.

```csharp
static void Main(string[] args)
{
  Dictionary<string, Action> actions = new Dictionary<string, Action>();

  actions.Add("first", DoFirst);
  actions.Add("second", DoSecond);
  
  actions["first"](); // Kör DoFirst-metoden
}

static void DoFirst()
{
  /* .. */
}

static void DoSecond()
{
  /* .. */
}
```

