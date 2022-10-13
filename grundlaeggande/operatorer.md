# Operatorer

## Matematiska

### + Addition och konkatenering

{% code lineNumbers="true" %}
```csharp
int x = 4 + 6; // Addition
string s = "hej " + "då" // Konkatenering
string s2 = "Värdet på x är " + x;
```
{% endcode %}

### - Subtraktion.

```csharp
int x = 6 - 4;
```

### / Division.

```csharp
int x = 6 / 3;
```

OBS: Om man delar ett heltal (int eller long) med ett annat heltal blir resultatet alltid ett heltal – decimaler trunkeras bort.

### \* Multiplikation.

```csharp
int x = 2 * 3;
```

### % Modulus

Räknar ut resten.

```csharp
int x = 5 % 2;
```

x blir lika med 1, eftersom det är vad man får kvar när man delat 5 med 2.

## Snabba

### += Addera något till variabelns värde.

```csharp
i += 5;
```

### ++ Lägg till 1 till variabelns värde.

```csharp
i++;
```

### -= Subtrahera något från variabelns värde.

```csharp
i -= 5; 
```

### -- Dra ifrån 1 från variabelns värde.

```csharp
i--;
```

## Boolska

### > < Större än, mindre än.

```csharp
bool x = 4 > 3;
```

### == Lika med

Är operanderna **likadana**?

```csharp
bool x = 4 == 4; // true eftersom 4 är samma som 4
```

### != Inte lika med

Är operanderna **olika**?

```csharp
bool x = 4 != 5; // true eftersom det stämmer att 4 och 5 är olika
```

## Logiska

### && And (Och)

True om **båda** operanderna är true, dvs det är true på båda sidorna om &&.

```csharp
bool x = true && true; // resultatet är true
```

```
bool y = true && false; // resultatet är false
```

### || Or (Eller)

True om **minst en** av operanderna är true.

{% code lineNumbers="true" %}
```csharp
bool x = true || false; // true; det räcker om den ena är true.
```
{% endcode %}

```
bool y = false || false; // false
```

```
bool z = (3 == 2) || x; // true; x är true även om 3 inte är samma som 2.
```
