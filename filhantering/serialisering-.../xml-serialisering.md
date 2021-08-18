# XML-serialisering

## Bibliotek

Lägg till dessa using-statements:

```csharp
using System.Xml.Serialization;
using System.IO;
```

## Klassdesign

Klassen vars instanser ska kunna serialiseras måste vara public.

```csharp
public class Spaceship
{
  // Lägg som vanligt in variabler, properties, metoder etc här
}
```

Det är också enbart publika variabler samt properties med publika getters och setters som serialiseras.

Om du ska deserialisera XML-kod som du får från något annat ställe och inte designat själv, så behöver du vara noga med att matcha namnet på dina publika variabler/[properties ](../../klasser-och-objektorientering/inkapsling-och-properties.md#properties)mot XML-filens. Serialiseringsprocessen är dock inte känslig vad gäller stora och små bokstäver.

{% tabs %}
{% tab title="Spaceship.cs" %}
```csharp
public class Spaceship
{
 public int Hp {get; set;} = 100;
 public int MaxHp {get; set;} = 100;
 public int Speed {get; set;} = 2;
}
```
{% endtab %}

{% tab title="Spaceship.xml" %}
```markup
<?xml version="1.0"?>
<Spaceship xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
           xmlns:xsd="http://www.w3.org/2001/XMLSchema">
 <hp>100</hp>
 <maxHp>100</maxHp>
 <speed>2</speed>
</Spaceship>
```
{% endtab %}
{% endtabs %}

## XmlSerializer

För att kunna serialisera instanser till XML behövs en XML-serialiserare, specialbyggd för att serialisera instanser av just den klassen.

```csharp
XmlSerializer shipSerializer = new XmlSerializer(typeof(Spaceship));
```

Tyvärr är XmlSerializern inte skriven som en generisk klass, så istället måste man använda typeof för att meddela vilken klass det är serialiseraren ska specialisera sig på.

## Serialize

När vi har en serialiserare så kan vi använda den för att serialisera en instans av en klass.

Beroende på om man vill ha ut XML-koden till en string eller till en fil behövs en StringWriter eller en FileStream.

{% tabs %}
{% tab title="StringWriter" %}
```csharp
Spaceship myShip = new Spaceship();

StringWriter textWriter = new StringWriter();

shipSerializer.Serialize(textWriter, myShip);

textWriter.Close();
```
{% endtab %}

{% tab title="FileStream" %}
```csharp
Spaceship myShip = new Spaceship();

FileStream file = File.Open(@"ship.xml", FileMode.OpenOrCreate);

shipSerializer.Serialize(file, myShip);

file.Close();
```
{% endtab %}
{% endtabs %}

Resultatet av denna kod blir att XML-koden längre upp på den här sidan sparas ner i ship.xml.

Samma kod kan skrivas så här, med hjälp av ett [using-statement](../open-close-using.md#using):

{% tabs %}
{% tab title="StringWriter" %}
```csharp
Spaceship myShip = new Spaceship();

using (StringWriter textWriter = new StringWriter())
{
  shipSerializer.Serialize(textWriter, myShip);
}
```
{% endtab %}

{% tab title="FileStream" %}
```csharp
Spaceship myShip = new Spaceship();

using (FileStream file = File.Open(@"ship.xml", FileMode.OpenOrCreate))
{
  shipSerializer.Serialize(file, myShip);
}
```
{% endtab %}
{% endtabs %}

## Deserialize

Serialiseraren kan också användas för att omvandla XML-text till en instans av klassen.

Beroende på om XML-koden finns i en string eller till en fil behövs en StringReader eller en FileStream.

{% tabs %}
{% tab title="StringReader" %}
```csharp
Spaceship myShip; // Variabeln resultatet lagras i

// xmlText är en variabel som innehåller XML-data
StringReader textReader = new StringReader(xmlText);

myShip = (Spaceship) shipSerializer.Deserialize(textReader);

textReader.Close();
```
{% endtab %}

{% tab title="FileStream" %}
```csharp
Spaceship myShip; // Variabeln resultatet lagras i

// ship.xml är en fil som innehåller XML-data
FileStream file = File.Open(@"ship.xml", FileMode.OpenOrCreate);

myShip = (Spaceship) shipSerializer.Deserialize(textReader);

file.Close();
```
{% endtab %}
{% endtabs %}

Eftersom serializern inte är skriven som en generisk klass så måste vi aktivt casta det Deserialize returnerar till den klass vi vill att det ska vara \(och vet att det borde vara\), i det här fallet Spaceship.

Samma kod kan skrivas så här, med hjälp av ett [using-statement](../open-close-using.md#using):

{% tabs %}
{% tab title="StringReader" %}
```csharp
Spaceship myShip;

using (StringReader textReader = new StringReader(xmlText))
{
  myShip = (Spaceship) shipSerializer.Deserialize(textReader);
}
```
{% endtab %}

{% tab title="FileStream" %}
```csharp
Spaceship myShip;

using (FileStream file = File.Open(@"ship.xml", FileMode.OpenOrCreate))
{
  myShip = (Spaceship) shipSerializer.Deserialize(textReader);
}
```
{% endtab %}
{% endtabs %}

## XML-serialisering av samlingar \(arrayer, listor\)

Det går utmärkt att serialisera även listor.

```csharp
List<Spaceship> fleet = new List<Spaceship>();

fleet.Add(new Spaceship());
fleet.Add(new Spaceship());
fleet.Add(new Spaceship());

XmlSerializer fleetSerializer = new XmlSerializer(typeof(List<Spaceship>));

using (FileStream file = File.Open(@"fleet.xml", FileMode.OpenOrCreate))
{
  shipSerializer.Serialize(file, fleet);
}
```

Precis som med andra variabler och properties så kommer publika samlingar av instanser som lagrats i en instans också serialiseras.

{% tabs %}
{% tab title="Fleet.cs" %}
```csharp
public class Fleet
{
  public List<Spaceship> ships = new List<Spaceship>();
}
```
{% endtab %}

{% tab title="Fleet.xml" %}
```markup
<?xml version="1.0"?>
<Fleet xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:xsd="http://www.w3.org/2001/XMLSchema">
 <ships>
   <Spaceship>
     <hp>100</hp>
     <maxHp>100</maxHp>
     <speed>2</speed>
   </Spaceship>
   <Spaceship>
     <hp>100</hp>
     <maxHp>100</maxHp>
     <speed>2</speed>
   </Spaceship>
 </ships>
</Fleet>
```
{% endtab %}
{% endtabs %}



