# Switch-case

Switch-case kan användas som ett alternativ till [if-satser](if-satser.md).

```csharp
int choice = 1;

switch(choice)
{
  case 1:
    Console.WriteLine("So you choose 1!");
    break;
  case 2:
    Console.WriteLine("So you choose 2!");
    break;
  case 3:
    Console.WriteLine("So you choose 3!");
    break;
  default:
    Console.WriteLine("That is not a valid choice!");
    break;
}
```

Man skriver alltså `switch` och sedan inom parenteser ett uttryck (t.ex. en variabel) som ska jämföras med flera olika _cases_.

Sedan skriver man ett antal `case`, där varje case är ett möjligt värde som uttrycket kan vara. I exemplet finns case 1, 2 och 3. Observera att man skriver : efter varje case och avslutar med en `break`.

Slutligen kan man ha en `default`, som är ett special-case som man hamnar i om uttrycket inte matchar något av de case man skrivit. Det är frivilligt att ha en default.

Har man ingen break så fortsätter koden att köras; på så vis kan man ha en kod som körs vid flera olika cases:

```cpp
int answer = 1;
int pts = 0;

switch(answer)
{
  case 1:
  case 2:
    Console.WriteLine("Not the right answer!");
    break;
  case 3:
    Console.WriteLine("Correct!");
    pts++;
    break;
  default:
    Console.WriteLine("That is not a valid answer!");
    break;
}
```
