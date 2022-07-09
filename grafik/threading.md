# Threading\*

{% hint style="info" %}
**OBSERVERA:** Threading är definitivt överkurs och ingår varken i Programmering 1 eller 2.
{% endhint %}

{% hint style="info" %}
**OBSERVERA:** Oftast gör man inte threading manuellt på det här viset i C#, men det är bra att förstå grundkonceptet. Istället används oftast [Tasks ](task-async-await.md)för asynkron programmering.
{% endhint %}

Threading innebär att kod kan köras asynkront – det vill säga att två bitar kod exekveras samtidigt, i olika "trådar" i CPUn. Vanliga användningsområden inkluderar:

* Se till så att ett grafiskt gränssnitt inte låser sig medan det väntar på svar från något på internet, eller på att något laddas in från hårddisken.
* Dela upp något som kräver mycket datorkraft på flera processorkärnor, och därmed utnyttja datorns kraft mer effektivt.

Normalt körs ett C#-program bara i en enda tråd. Det betyder att den bara körs på en enda processorkärna – en kärna kan köra flera trådar, men en tråd kan inte delas upp på flera kärnor.

Om det arbete en tråd utför är väldigt tungt så begränsas tråden av sin processor – det syns till exempel i att en processorkärna arbetar till 100% medan övriga knappt gör något alls. Vill man då öka hastigheten på körningen behöver man dela upp arbetet på flera processorer.

**Den stora nackdelen** med threading är att det blir svårt att dela data på ett säkert sätt mellan olika delar av programmet. Om två trådar till exempel försöker komma åt samma resurs finns risk att något går fel.

## Debugging

## Thread

Thread-klassen används när man manuellt vill skapa nya trådar. Som parameter anges en metod vars kod ska köras i den separata tråden. Observera att det är metodens namn – dess identifier – som anges, och att man inte skriver () efter namnet.

```csharp
Thread workerThread = new Thread(DoSomeHeavyLifting);

static void DoSomeHeavyLifting()
{
  // Kod som ska köras i en separat tråd
}
```

Man kan också använda metoder som tar emot en parameter. Parametern måste då vara av datatypen object, som sedan kan castas till sin egentliga datatyp.

```csharp
Thread workerThread = new Thread(DoSomeHeavyLifting);

static void DoSomeHeavyLifting(object n)
{
  string name = (string) n;
  
  // Kod som ska köras i en separat tråd
}
```

### Start

Startar körningen av tråden.

```csharp
Thread workerThread = new Thread(DoSomeHeavyLifting);
workerThread.Start();
```

När man startar körningen av en metod som tar emot parametrar, så anges parametervärdet som parameter i Start-metoden.

```csharp
Thread workerThread = new Thread(DoSomeHeavyLifting);
workerThread.Start("Saruman");

static void DoSomeHeavyLifting(object n)
{
  string name = (string) n;
  
  // Kod som ska köras i en separat tråd
}
```

### Join

Pausar körningen av den nuvarande tråden, tills den tråd som "joinas" är klar med sin körning.

```csharp
Thread workerThread = new Thread(DoSomeHeavyLifting);
workerThread.Start();

// Gör nånting

workerThread.Join();
```

### Name

Trådens namn. Användbart bl.a när man debuggar.

```csharp
Thread workerThread = new Thread(DoSomeHeavyLifting);

workerThread.Name = "Arbetaren";
```

### IsAlive

### CurrentThread

### IsBackground

### Sleep

##
