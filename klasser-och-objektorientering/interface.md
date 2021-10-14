# Interface

Ett interface är ett slags kravspecifikation som beskriver ett antal metoder som en klass behöver implementera. De fungerar som ett slags tvingande abstrakta klasser. När en klass "ärver" från ett interface så kallas det att klassen implementerar interfacet.

Interfaces namnges med PascalCase och med ett I (stora i) i början.

{% tabs %}
{% tab title="IDamagable.cs" %}
```csharp
interface IDamagable
{
  void Hurt(int amount);
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Character.cs" %}
```csharp
class Character : IDamagable
{
  public string name;
  public int hp = 100;

  public void Hurt(int amount)
  {
    hp -= amount;
  }
}
```
{% endtab %}
{% endtabs %}

Interfacet Damagable specificerar att klasser som implementerar det måste ha en Hurt-metod.

Sedan kan man designa t.ex. metoder som kan ta emot vilken klass sim helst som implemeterar interfacet som parameter:

{% tabs %}
{% tab title="Character.cs" %}
```csharp
class Character : IDamagable
{
  public string name;
  public int hp = 100;

  public void Hurt(int amount)
  {
     hp -= amount;
  }

  public void Attack(Damagable target)
  {
    target.Hurt(5);
  }
}
```
{% endtab %}
{% endtabs %}

I exemplet ovan kan man alltså stoppa in Characters - eller vad som helst som implementerar Damagable - i metoden Attack. Eftersom man vet att alla klasser som implementerar Damagable har en Hurt-metod.

Sedan behöver den som designar andra saker i spelet som kan skadas - väggar, växter, utrustning, känslor - bara se till att hens klasser implementerar Damagable, så vet man att klasserna kommer att fungera tillsammans med karaktärernas Attack-metod.

## Implementera flera interfaces

En och samma klass kan implementera flera interfaces.

{% tabs %}
{% tab title="IDamagable.cs" %}
```csharp
interface IDamagable
{
  void Hurt(int amount);
}  
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="IAttacking.cs" %}
```csharp
interface IAttacking
{
  void Attack(Damagable target);
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Character.cs" %}
```csharp
class Character : IDamagable, IAttacking
{
  public string name;
  public int hp = 100;

  public void Hurt(int amount)
  {
     hp -= amount;
  }

  public void Attack(Damagable target)
  {
    target.Hurt(5);
  }
}
```
{% endtab %}
{% endtabs %}

Eftersom interfaces mer fungerar som kravspecifikationer än traditionella arv så innebär detta med andra ord helt enkelt att klassen uppfyller de krav som ställs upp av både IDamagable och IAttacking.
