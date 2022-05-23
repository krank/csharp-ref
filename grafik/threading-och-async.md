# Threading och async\*

Threading innebär att kod kan köras asynkront – det vill säga att två bitar kod exekveras samtidigt, i olika "trådar" i CPUn. Vanliga användningsområden inkluderar:

* Se till så att ett grafiskt gränssnitt inte låser sig medan det väntar på svar från något på internet, eller på att något laddas in från hårddisken.
* Dela upp något som kräver mycket datorkraft på flera processorer, och därmed utnyttja datorns kraft mer effektivt.

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

### Wait()

Pausar körningen av koden tills den inkapslade metoden körts färdigt.

```csharp
Console.WriteLine("Waiting...");
taskMaster.Wait();
Console.WriteLine("Finished!");
```

### Result

Innehåller det som returnerats från den inkapslade metoden, när den körts färdigt. Om Result läses av innan metoden körts färdigt så pausar koden precis som med Wait().

```csharp
Console.WriteLine("Waiting...");
int result = taskMaster.Result;
Console.WriteLine($"Finished with a result of {result}!");
```



## Async

* Asynkron metod
* Har en Task som returtyp, men returnerar Taskens typ-parameter
* Invänta att den avslutas genom await eller .Result

## Await

* Kan skrivas framför en asynkron metod
* Wait:ar på den asynkrona metoden och ger, som resultat, det den returnerar

