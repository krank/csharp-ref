# Threading och async\*

## Task<>

Den generiska Task-klassen abstraherar och förenklar användningen av threading i C#.&#x20;

Genom att kapsla in en metod i en **Task** så körs metoden parallellt med övrig kod i programmet.

```csharp
static int HelloWorld()
{
  Console.WriteLine("Hello World!");
  Thread.Sleep(1000);
  Console.WriteLine("Goodbye World!");
  return 23;
}

Task<int> taskMaster = Task.Run(HelloWorld);
```

Taskens typ-parameter ska vara densamma som returtypen för metoden som kapslas in.

### Wait

### Result



* Asynkron körning
  * Task<>
    * Run
    * Result
  * async
    * Asynkron metod
    * Returnerar en Task
    * Invänta att den avslutas genom await eller .Result
  * await
    *
* Threading
