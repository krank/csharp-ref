# Task, async, await\*

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

## Await
