# Closed

Från C# 15 så kan man deklarera en klass som closed. Då blir den automatiskt också abstract.

En klass som är closed kan man bara skapa subklasser av i det nuvarande programmet (assemblyn).

```csharp
public closed class Enemy
{

}
```

