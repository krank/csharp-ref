# Grundläggande

## Swap

```csharp
int a = 5;
int b = 3;

int tmp=a; // lagra värdet tillfälligt i en tmp-variabel
a=b;
b=tmp;
```

## Begränsa input

<pre class="language-c#"><code class="lang-c#">string answer = ""; // Skapa en tom svarsvariabel
/<a data-footnote-ref href="#user-content-fn-1">/ Loopa så länge svar varken är a eller b</a>
while (answer != "a" &#x26;&#x26; answer != "b")
{
  Console.Write("Välj a eller b:");
  answer = Console.ReadLine();
}
</code></pre>

### Med break istället

```csharp
string answer = ""; // Skapa en tom svarsvariabel

while (true)
{
  Console.Write("Välj a eller b:");
  answer = Console.ReadLine();
  // Avbryt loopen om svaret är a eller b
  if (answer == "a" || answer == "b")
  {
    break;
  }
}
```

### Läsa in en siffra

```csharp
int answer = 0; // Skapa en tom svarsvariabel

while (true)
{
  Console.Write("Skriv en siffra:");
  string tmp = Console.ReadLine();
  bool success = int.TryParse(tmp, out answer)
  
  if (success)
  {
    break;
  }
}
```

## Early return

Hoppa ur en metod tidigt, så slipper man onödig nästling.

```csharp
static false IsPalindrome(string text)
{
  // Om textens längd är 0, så är det en tom string och ingen palindrom
  if (text.Length == 0) return false;
  
  // --- Kod för att kolla om det är en palindrom
}
```

## Listor

Dessa funkar även med arrayer och en del andra samlingar.

Flera av dem bygger på samma idé: index i en lista går från 0 till ett maxvärde. Detta index är en vanlig integer, och man kan använda olika sätt för att få fram giltiga index.

### Slumpa ur en lista

Alla tal mellan 0 och listans Count är giltiga index. Alltså kan man slumpa ett tal mellan 0 och Count och få ett framslumpat giltigt index.

```csharp
List<string> names = ["Micke", "Martin", "Liv"];
int rn = Random.Shared.Next(names.Count);
string name = names[rn];
Console.WriteLine("Hello " + name);
```

### Gå igenom en lista med for

En for-loop räknar normalt upp från 0 till ett maxvärde. Använder man listans Count eller arrayens Length som maxvärde så ger for-loopen exakt de index som är giltiga.

```csharp
List<string> choices = ["Start", "Options", "Quit"];

for (int i = 0; i < choices.Count; i++)
{
  Console.WriteLine(i + ": " + choices[i]);
}
```

### Filtrera från en lista

Om man _går igenom_ en lista så kan man utsätta varje grej i listan för en if-sats och undersöka om den uppfyller vissa krav. Därmed kan man göra något med _bara vissa_ av grejerna i listan.

```csharp
List<int> numbers = [56, 128, 12, 4, 665];

for (int i = 0; i < numbers.Count; i++)
{
  if (numbers[i] > 50)
  {
    Console.WriteLine(numbers[i] + " är högre än 50!);
  }
}
```

### Ackumulera från en lista

Om man går igenom en lista kan man också använda en variabel för att komma ihåg något mellan loopens iterationer. Denna ackumulator kan då användas för att samla på sig information – den kan t.ex. komma ihåg vilket som är det lägsta talet hittills, eller räkna ihop en summa.

```csharp
List<int> numbers = [56, 128, 12, 4, 665];
int sumAcc = 0;
for (int i = 0; i < numbers.Count; i++)
{
  sumAcc += numbers[i];
}
Console.WriteLine("Summan är " + sumAcc);
```

### Synkade listor

Har man två listor med _samma längd_ så kan man tänka sig att de _hör ihop_, och att sakerna på varje index i respektive lista beskriver _olika_ egenskaper hos _samma sak_.

```csharp
List<string> planets = ["Mercury", "Venus", "Earth"];
List<float> gravity = [3.7f, 8.87f, 9.807f];

// Planet 1 (Venus) har gravitationen 1 (8.87)
Console.WriteLine(planets[1] + " har gravitationen " + gravity[1] + " m/s");
```



[^1]: 
