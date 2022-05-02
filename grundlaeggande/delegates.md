# Delegates och lambdas

Delegates är ett sätt att kunna göra så att variabler pekar mot metoder istället för mot värden eller objekt i minnet. De är lite överkurs, men ganska användbara.

```csharp
// Skapar en delegate som passar in på metoder som 
// inte tar emot några parametrar eller returnerar något.
delegate void Task(); 

// En metod som passar in på delegaten
static void SayHello() {
  System.WriteLine("Hello!");
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

När man skapat sin delegat används den alltså som om den vore en datatyp. När man lagrar metoderna i den så ser man till att inte använda () efter metodnamnet, för då körs ju metoden istället, innan tilldelningen.

```csharp
DelegateOne test = MethodOne;
```

### Dictionary med Actions <a href="#h.p_qt3arehin8yt" id="h.p_qt3arehin8yt"></a>

Ett exempel på hur man kan använda delegater – **Action** är en delegat som ingår i C# och som helt enkelt stämmer in på metoder som varken tar emot parametrar eller returnerar något.

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

### Anonyma metoder i delegatvariabler

Anonyma metoder saknar eget namn.

```csharp
delegate void Task(); 

static void Main(string[] args)
{
  Task t = delegate()
    {
      System.WriteLine("Hello!");
    }
    
  t();
}
```

De är praktiska när man aldrig faktiskt kommer att anropa metoden med dess eget namn, utan bara vill kunna lägga in den i en variabel eller en lista.

```csharp
Dictionary<string, Action> actions = new Dictionary<string, Action>();

actions.Add("greet", 
  delegate ()
  {
    Console.WriteLine("Hello");
  }
);

actions["greet"]();
```

### Multicasting: delegat-variabler med flera metoder

Om man vill att flera metoder ska köras när en delegat-variabel anropas så kan man kombinera delegater för att skapa s.k. [multicast-delegater](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates).

```csharp
Action multiCaster = delegate() { Console.WriteLine("Hello"); };

multiCaster += delegate() { Console.WriteLine("World"); };

multiCaster(); // Skriver först ut Hello, sedan World
```

```csharp
Action good = delegate() { Console.WriteLine("Good"); };

Action bye = delegate() { Console.WriteLine("Bye"); };

Action morning = delegate() { Console.WriteLine("Morning"); };

Action goodMorning = good + morning;
Action goodBye = good + bye;

goodMorning();
goodBye();
```

### Lambdas

Lambda-uttryck är, enkelt uttryckt, ett sätt att skriva väldigt enkla anonyma metoder (anonyma delegater) vars returvärden är direkta resultat av deras parametrar.

```csharp
// Delegat som passar alla metoder som tar emot två int-parametrar och
// som returnerar en int som resultat
delegate int Calculation(int x, int y);

static void Main(string[] args)
{
  // Lambda-uttrycket => har två inputs på vänster sida, 
  // och uträkningen på höger sida resulterar i en int.
  // Därför passar lambda-uttrycket in på delegaten Calculation.
  Calculation c = (xInput, xOutput) => xInput * xOutput;

  int result = c(10, 5);
}
```

Lambdas används väldigt ofta när man till exempel vill filtrera en lista på något sätt.

```csharp
List<int> numbers = new List<int>() {2,3,4,5,6};

// FindAll returnerar en lista med alla föremål i listan som matchar ett visst
// kriterium. Kriteriet ska vara utformat som en metod, som tar emot ett
// föremål av rätt datatyp som parameter och returnerar en bool.
// lambda-uttrycket nedan tar emot en input på vänster sida (n) och uttrycket
// på höger sida är en boolsk jämförelse.
// Därför kommer lowNumbers att innehålla en lista med alla integers från
// numbers, som är < 4.
List<int> lowNumbers = numbers.FindAll(n => n < 4);
```
