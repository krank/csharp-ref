# State pattern

När man använder ett objektorienterat state pattern så delar man in sin kod i lägen den kan vara i – ett AI-system skulle till exempel kunna ha lägena "Patrolling", "Attacking" och "Fleeing". Varje state blir en instans av en klass; antingen en generell State-klass eller en subklass till en sådan.

Varje state har också ansvaret för att se till så att vilket state som är det nuvarande byts ut när rätt kriterier uppfylls – så det är t.ex. Patrolling-state:t som avgör ifall och när man ska byta till Attacking.

Det enklaste sättet att implementera detta är att låta varje state ha en metod som anropar statets kod, och returnerar antingen sig självt eller ett nytt state till en generell "currentState"-variabel. Och så körs anropar-metoden på currentState i en loop, så att currentState hela tiden uppdateras.

{% code title="Program.cs" lineNumbers="true" %}
```csharp
State currentState = new MenuState();

while (true)
{
  currentState = currentState.Invoke();
}
```
{% endcode %}

{% code title="State.cs" lineNumbers="true" %}
```csharp
abstract class State
{
  public abstract State Invoke();
}
```
{% endcode %}

{% code title="MenuState.cs" lineNumbers="true" %}
```csharp
class MenuState : State
{
  public override State Invoke()
  {
    Console.WriteLine("MENYN");
    Console.WriteLine("Skriv 'a' och tryck enter");
    string answer = Console.ReadLine();
    if (answer == "a") return new GameState();
    else return this;
  }
}
```
{% endcode %}

{% code title="GameState.cs" lineNumbers="true" %}
```csharp
class GameState : State
{
  private int hp = 10;
  public override State Invoke()
  {
    Console.WriteLine("SPELET");
    Console.WriteLine($"Du tar 1 hp i skada ({hp} kvar)");
    Console.ReadLine();
    hp--;
    if (hp <= 0) return new MenuState();
    else return this;
  }
}
```
{% endcode %}
