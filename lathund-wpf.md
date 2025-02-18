# Lathund – koda WPF-applikationer

## Appens fönster

Vanliga attribut för fönstret i XAML:
- **Title:** Sätter fönstrets titel.
- **MaxWidth** och **MaxHeight:** Anger maximal storlek för fönstret.
- **SizeToContent:** Bestämmer hur fönstret anpassar sig efter innehållet. Exempel: `SizeToContent="WidthAndHeight"` innebär att fönstret anpassar både bredd och höjd.

```xml
<Window ...
        Title="MinApp"
        MaxWidth="800" MaxHeight="450"
        SizeToContent="WidthAndHeight">
    <!-- Innehållet i fönstret -->
</Window>
```

## Vanliga kontroller och attribut i XAML

### Layoutkontroller – StackPanel

StackPanel är en layoutkontroll som ordnar sina barnkontroller i en vertikal eller horisontell stapel.  
Vanliga attribut:
- **Background:** Anger bakgrundsfärg.
- **Orientation:** Bestämmer stapelns riktning, t.ex. `Orientation="Vertical"` eller `Orientation="Horizontal"`.

```xml
<Window ...>
    <StackPanel Background="#000" Orientation="Vertical">
        <!-- Barnkontroller -->
    </StackPanel>
</Window>
```

### Label

Används för att visa text. Vanliga attribut:
- **Margin:** Anger yttre marginal.
- **FontSize:** Bestämmer teckenstorlek.
- **Foreground:** Sätter textfärg.

```xml
<Label Margin="10" FontSize="24" Foreground="#FFF">Ange ditt namn</Label>
```

### Button

En klickbar knapp. Vanliga attribut:
- **Margin** och **Padding:** Anger yttre och inre marginal.
- **Background:** Anger knappens bakgrundsfärg.
- **FontWeight:** T.ex. `FontWeight="Bold"` för fet stil.
- **Foreground:** Sätter textfärg.

```xml
<Button Margin="10" Padding="10" Background="Red" FontWeight="Bold">Spara</Button>
```

### TextBox

Används för att visa eller låta användaren skriva in text. Vanliga attribut:
- **Margin** och **Padding:** Styr layouten.
- **IsReadOnly:** Anger om textfältet är skrivskyddat.

```xml
<TextBox Margin="10" Padding="10"></TextBox>
```

### Image

Visar en bild. Vanliga attribut:
- **Width:** Sätter bildens bredd.
- **Source:** Anger sökvägen till bildfilen.

```xml
<Image Width="200" Source="bilder/melodifestivalen.png" />
```

Bildfilen skall ligga i rätt mapp i projektet, och i **.cproj**-filen skall mappen inkluderas som en resurs:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    ...
  </PropertyGroup>
  <ItemGroup>
    <Resource Include="./bilder/*.png" />
  </ItemGroup>
</Project>
```

## Vanliga attribut för kontroller

Alla kontroller i XAML kan ha följande attribut:

- **Margin:** Anger yttre marginal.
- **Padding:** Anger inre marginal.
- **Background:** Bakgrundsfärg.
- **Foreground:** Textfärg.
- **Width** och **Height:** Storlek.
- **FontFamily:** Typsnitt.
- **FontSize:** Teckenstorlek.
- **FontWeight:** Fet stil.

## Koppla kontroller till C#-kod

### click-event och event-metoder

När en användare klickar på en knapp utlöses ett ```click```-event. I XAML kopplar du eventet till en metod genom att använda attributet **Click**. Exempel:

```xml
<Button Click="KlickSpara" Margin="10" Padding="10">Spara</Button>
```

I logiken definierar du event-metoden som hanterar klickhändelsen:

```csharp
void KlickSpara(object sender, RoutedEventArgs e)
{
    MessageBox.Show("Du sparade dina ändringar!");
}
```

### Referens till kontroller: Name-attributet

Name-attributet i XAML ger varje kontroll ett unikt namn, vilket gör att du kan referera till den direkt i din C#-logik. När du exempelvis anger:

```xml
<TextBox Name="txbResultat" Margin="10" Padding="10"></TextBox>
```

Nu kan du i C#-koden referera till textfältet med namnet `txbResultat`. Exempel:

```csharp
// Läs innehållet i textfältet
string innehall = txbResultat.Text;

// Sätt nytt innehåll i textfältet
txbResultat.Text = "Nytt innehåll visas här!";
```
