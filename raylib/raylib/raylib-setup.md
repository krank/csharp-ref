# Raylib setup

## I Visual Studio Code

Skapa ett nytt konsollprojekt som vanligt, med eller utan solution.

### Alternativ 1: Installera via NuGet Gallery

* Ta fram kommandopaletten \(F1\) och sök efter NuGet Gallery.
* I galleriet, sök efter Raylib.
* Kryssa i ditt projekt, klicka Install.

![](https://lh3.googleusercontent.com/g0GRXLLHduG1kDk0wLtjec4ruyvZWnxkqlWSeMjlyu5DEw1RMIRaKRMwqykZFU083GT2krx2Xao24T_YK6VUifM4w6eY444q52HBUsBkz8Ha5Wenhu0=w1280)

### Alternativ 2: Installera via terminalen <a id="h.p_eZYhfdj2mpDH"></a>

Öppna terminalen och skriv in följande.

```text
dotnet add package Raylib-cs
```

Tryck Enter. SFML.Net laddas ner till ditt projekt, och du kan nu återgå till din Program.cs-fil.

### Inkludera Raylib <a id="h.p_jUwPvKT-mpLN"></a>

{% hint style="warning" %}
**OBSERVERA:** För att du ska kunna använda Raylib så måste du skriva in följande bland dina using-rader högst upp i programfilen:

```csharp
using Raylib_cs;
```
{% endhint %}

## I Visual Studio <a id="h.p_UWqYyuHkiwIc"></a>

Börja med att skapa ett projekt av typen Console App \( .NET Core\). Observera alltså att det ska vara .NET Core och inte .NET Framework!  
 ![](../../.gitbook/assets/image%20%2815%29.png) 

Högerklicka på projektet i Solution Explorer och välj Manage NuGet Packages.

I fönstret som dyker upp, klicka på Browse.  
 ![](../../.gitbook/assets/image%20%2812%29.png) 

Sök efter "raylib" och klicka på Raylib-cs.  
 ![](../../.gitbook/assets/image%20%2813%29.png) 

I högerspalten, klicka på Install.

![](../../.gitbook/assets/image%20%2814%29.png) 

Det dyker nu upp en dialogruta med titeln "Preview changes", och där du får svara på om du vill lägga till Raylib till ditt projekt. Tryck OK.

### Inkludera Raylib <a id="h.p_jUwPvKT-mpLN"></a>

{% hint style="warning" %}
**OBSERVERA:** För att du ska kunna använda Raylib så måste du skriva in följande bland dina using-rader högst upp i programfilen:

```csharp
using Raylib_cs;
```
{% endhint %}

