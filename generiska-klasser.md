# Generiska klasser

## Färdiga generiska klasser

OBS: För att dessa ska fungera om du kör .NET Core, så behöver du skriva in följande högst upp i din kod:

```csharp
using System.Collections.Generic;
```

### List

Fungerar som arrayer, utom att man inte bestämmer storlek från början utan kan använda bl.a Add och Insert och RemoveAt-metoder för att lägga till, stoppa in och ta bort grejer ur listan när som helst.

```csharp
List<string> myList = new List<string>();

myList.Add("hej");

Console.WriteLine(myList[0])

List.RemoveAt(0);
```

### Queue

Fungerar som en lista, utom att man bara kan lägga till saker längst bak i kön, och ta bort dem längst fram.

```csharp
Queue<int> myQueue = new Queue<int>();

myQueue.Enqueue(5);
myQueue.Enqueue(42);
myQueue.Enqueue(665);

// Peek returnerar en kopia av värdet som ligger 
// längst fram i kön – 5 i det här fallet
Console.WriteLine(myQueue.Peek());

// Dequeue tar bort värdet som ligger längst fram ur kön 
// och returnerar det. Så nu är kön = 42, 665.
int n = myQueue.Dequeue();
```

### Stack

Fungerar som en "hög" – man kan bara lägga till saker högst upp i högen och även bara plocka bort saker från högst upp i högen.

```csharp
Stack<int> myStack = new Stack<int>();

myStack.Push(5);
myStack.Push(42);
myStack.Push(665);

// Precis som för queue, peekar "nästa värde". Det som ligger högst upp – 665.
Console.WriteLine(myQueue.Peek());

// Tar bort det som ligger högst upp i högen och returnerar det.
// Så nu är bara 5 och 42 kvar i högen.
int n = myStack.Pop();
```

### HashSet

Saknar indexering, men kan bara innehålla unika objekt – man riskerar inte att råka lägga till samma sak flera gånger.

```csharp
HashSet<int> mySet = new HashSet<int>();

mySet.Add(5);
mySet.Add(42);
mySet.Add(5);

// skriver ut true, eftersom 5 ingår i setet.
Console.WriteLine(mySet.Contains(5));

// Skriver ut 2, för det finns bara 2 unika objekt i setet
//  – den andra femman lades aldrig till.
Console.WriteLine(mySet.Count());
```

### Dictionary

Fungerar som en lista, utom att man kan använda andra datatyper än ints som index.

```csharp
Dictionary<string, int> myStats = new Dictionary<string, int>();

myStats.Add("Strength", 20);
myStats.Add("Intelligence", 12);

Console.WriteLine(myStats["Strength"]);

foreach (string key in myStats.Keys.ToArray())
{
  Console.WriteLine(key + ": " + myStats[key];
}
```

## Skapa egna generiska klasser

Generiska klasser är oftast "container-klasser", alltså klasser vars uppgift det är att lagra ett annat värde.

{% tabs %}
{% tab title="Node.cs" %}
```csharp
class Node
{
  public int value;
  public Node nextNode;
}
```
{% endtab %}
{% endtabs %}

Ovanstående kod är en enkel nod i en s.k. länkad lista. I en länkad lista känner varje nod bara till "nästa nod". Observera att den bara kan lagra ints i det här fallet. Om jag vill skapa en nod som kan lagra strings måste jag skapa en ny klass för det. Eller så gör jag den generisk:

{% tabs %}
{% tab title="Node.cs" %}
```csharp
class Node<T>
{
  public T value;
  public Node nextNode;
}
```
{% endtab %}
{% endtabs %}

Nu kan jag bestämma vilken datatyp variabeln value ska ha genom att ange det mellan &lt;&gt; när jag skapar instansen:

```csharp
Node<string> firstTextNode = new Node<string>();
firstTextNode.value = "Bananas";

Node<int> firstNumberNode = new Node<int>();
firstNumberNode.value = 23;
```

