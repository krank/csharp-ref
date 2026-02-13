# State pattern

State pattern är…

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
