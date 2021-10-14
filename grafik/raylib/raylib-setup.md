# Raylib setup

## I Visual Studio Code

Skapa ett nytt konsollprojekt som vanligt, med eller utan solution.

* Ta fram kommandopaletten (F1) och sök efter NuGet Gallery (som du såklart [behöver ha installerat](https://marketplace.visualstudio.com/items?itemName=patcx.vscode-nuget-gallery)).
* I galleriet, sök efter Raylib.
* Kryssa i ditt projekt, klicka Install.

### Inkludera Raylib <a href="h.p_juwpvkt-mpln" id="h.p_juwpvkt-mpln"></a>

{% hint style="warning" %}
**OBSERVERA:** För att du ska kunna använda Raylib så måste du skriva in följande bland dina using-rader högst upp i programfilen:

```csharp
using Raylib_cs;
```
{% endhint %}

## Via terminalen

Öppna terminalen och skriv in följande.

```
dotnet add package Raylib-cs
```

Tryck Enter. SFML.Net laddas ner till ditt projekt, och du kan nu återgå till din Program.cs-fil.

## I Visual Studio <a href="h.p_uwqyyuhkiwic" id="h.p_uwqyyuhkiwic"></a>

Börja med att skapa ett projekt av typen Console App ( .NET Core).

Högerklicka på projektet i Solution Explorer och välj Manage NuGet Packages.

I fönstret som dyker upp, klicka på Browse.\
 ![](<../../.gitbook/assets/image (13).png>) 

Sök efter "raylib" och klicka på Raylib-cs.\
 ![](<../../.gitbook/assets/image (14).png>) 

I högerspalten, klicka på Install.

![](<../../.gitbook/assets/image (15).png>) 

Det dyker nu upp en dialogruta med titeln "Preview changes", och där du får svara på om du vill lägga till Raylib till ditt projekt. Tryck OK.

### Inkludera Raylib <a href="h.p_juwpvkt-mpln" id="h.p_juwpvkt-mpln"></a>

{% hint style="warning" %}
**OBSERVERA:** För att du ska kunna använda Raylib så måste du skriva in följande bland dina using-rader högst upp i programfilen:

```csharp
using Raylib_cs;
```
{% endhint %}
