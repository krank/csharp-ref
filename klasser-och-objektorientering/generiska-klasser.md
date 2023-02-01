# Generiska klasser

En generisk klass är en klass där någon datatyp inte är fördefinierad, utan deklareras i koden. En lista där värdena som lagras är `int` har till exempel datatypen List\<int> och en lista med strings är en List\<string>.

Det som skrivs mellan <> i en generisk klass kallas för en **typ-parameter**.

## Färdiga generiska klasser

OBS: För att dessa ska fungera om du kör äldre versioner av dotnet (t.ex. dotnet 5), så behöver du skriva in följande högst upp i din kod:

```csharp
using System.Collections.Generic;
```

### List

Fungerar som arrayer, utom att man inte bestämmer storlek från början utan kan använda bl.a Add och Insert och RemoveAt-metoder för att lägga till, stoppa in och ta bort grejer ur listan när som helst.

{% code lineNumbers="true" %}
```csharp
List<string> myList = new List<string>();

myList.Add("hej");

Console.WriteLine(myList[0])

List.RemoveAt(0);
```
{% endcode %}

### Queue

Fungerar som en lista, utom att man bara kan lägga till saker längst bak i kön, och ta bort dem längst fram.

{% code lineNumbers="true" %}
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
{% endcode %}

### Stack

Fungerar som en "hög" – man kan bara lägga till saker högst upp i högen och även bara plocka bort saker från högst upp i högen.

{% code lineNumbers="true" %}
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
{% endcode %}

### HashSet

Saknar indexering, men kan bara innehålla unika objekt – man riskerar inte att råka lägga till samma sak flera gånger.

{% code lineNumbers="true" %}
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
{% endcode %}

### Dictionary

Fungerar som en lista, utom att man kan använda andra datatyper än ints som index. I Dictionaries använder man ofta ordet "key" istället för "index".

{% code lineNumbers="true" %}
```csharp
Dictionary<string, int> myStats = new Dictionary<string, int>();

myStats.Add("Strength", 20);
myStats.Add("Intelligence", 12);

Console.WriteLine(myStats["Strength"]);
```
{% endcode %}

#### Keys

Man kan få fram en samling av alla keys i ett dictionary genom att läsa av egenskapen Keys som är inbyggd i alla Dictionaries.

{% code lineNumbers="true" %}
```csharp
foreach (string key in myStats.Keys)
{
  Console.WriteLine($"{key}: {myStats[key]});
}
```
{% endcode %}

## Skapa egna generiska klasser

Generiska klasser är oftast "container-klasser", alltså klasser vars uppgift det är att lagra ett annat värde.

{% code title="Node.cs" lineNumbers="true" %}
```csharp
class Node<T>
{
  public T value;
  public Node nextNode;
}
```
{% endcode %}

Ovanstående kod är en enkel nod i en s.k. länkad lista. I en länkad lista känner varje nod bara till "nästa nod".&#x20;

Nu bestäms vilken datatyp variabeln value ska ha genom att den anges mellan <> när instansen skapas:

{% code lineNumbers="true" %}
```csharp
Node<string> firstTextNode = new Node<string>(); // value blir en string
firstTextNode.value = "Bananas";

Node<int> firstNumberNode = new Node<int>(); // value blir en int
firstNumberNode.value = 23;
```
{% endcode %}
