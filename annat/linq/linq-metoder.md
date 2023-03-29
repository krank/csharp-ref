# Linq-metoder\*

Ofta tar metoderna emot [delegater ](../../grundlaeggande/delegates.md)som parametrar, och ofta används då istället [Lambda-uttryck](../../grundlaeggande/delegates.md#lambdas).

## Metoder

### Hämta flera

#### Where()

#### OfType<>()

### Hämta enstaka

#### First() / Last()

Returnerar det första/sista värdet i samlingen. Om samlingen är tom så skapas ett [runtime-fel](../../grundlaeggande/fel.md#runtime-fel-exceptions).

```csharp
List<int> myList = new List<int>() {4,3,2,1};

int i = myList.First(); // i blir 4
```

#### FirstOrDefault() / LastOrDefault()

Fungerar som First/Last, utom att metoden returnerar null, eller ett default-värde (t.ex. 0 för ints) ifall samlingen är tom.

```csharp
List<int> myList = new List<int>();
int i = myList.FirstOrDefault(); // i blir 0
```

### OrderBy()

### Select

### Boolska

#### All()

#### Any()

### Matematiska

#### Max()

#### Min()

#### Average()
