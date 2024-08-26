# XAML\*

## Element

Elementen är UIts byggstenar; de är saker som knappar och textrutor. En del av dem är rena layoutelement, som t.ex. StackPanel som man lägger andra element inuti. Varje element kan olika _attribut_. Ibland kallas elementen också _kontroller_. De kan skrivas med start- och sluttagg eller som självavslutande taggar.

```xml
<TextBlock>Kolla här!</TextBlock>
<Button>Klicka på mig!</Button>
```

```xml
<TextBlock Text="Kolla här!" />
<Button Content="Klicka på mig!" />
```

## Attribut

Det finns många olika attribut tillgängliga för olika element. De kan skrivas antingen inuti starttaggen för elementet eller som child-taggar.

```xml
<TextBlock FontSize="28" Text="Kolla här" />
```

```xml
<TextBlock>
  <TextBlock.FontSize>28</TextBlock.FontSize>
  <TextBlock.Text>Kolla här!</TextBlock.Text>
</TextBlock>
```

### x:Name

Ger elementet ett unikt namn

```xml
<TextBlock x:Name="NameText">Hello</TextBlock>
```

### Text/Content

Get elementet ett innehåll, eller en text. Vissa typer av element har text, men de flesta har Content istället.

```xml
<TextBlock Text="Hello"/>
```

### FontSize

Anger textens storlek.

```xml
<TextBlock FontSize="56" Text="Hello"/>
```

### Margin

Lägger till utrymme kring elementet.

```xml
<TextBlock Margin="10">Hello</TextBlock>
```

## Events

Varje element har ett antal events som kod kan reagera på – t.ex. att en knapp klickas på eller att en kryssruta kryssas i eller ur.

Ett sätt att göra detta är genom att ange event i XAML och sedan ha en matchande metod i fönstrets cs-fil.

{% code title="MainWindow.xaml" %}
```xml
<Button x:Name="mainButton" Click="OnMainClick" Margin="10">What</Button>
```
{% endcode %}

<pre class="language-csharp" data-title="MainWindow.xaml.cs"><code class="lang-csharp"><strong>private void OnMainClick(object sender, RoutedEventArgs e)
</strong>{
  MessageBox.Show("Yes");
}
</code></pre>

Genom att analysera **sender** kan man få veta mer – om t.ex. en och samma metod anropas från flera olika objekt kan det vara bra att veta vilket.

```csharp
if (sender is FrameworkElement obj)
{
  MessageBox.Show(obj.Name);
}
```

### Eventbindning i kod

För att helt separera kod från XAML kan man sköta bindningen i C# istället. Det gör också att man kan få flera olika metoder att anropas när en event sker.

Man behöver en referens till objektet; den kan man t.ex. skaffa genom att använda FindName för att hitta objektet man vill lägga till en bindning till, och casta objektet till rätt datatyp.

Sedan utnyttjar man att alla events ligger inlagda i datatypen som [delegates](../../grundlaeggande/delegates.md).

```csharp
if (FindName("mainButton") is Button button)
{
  button.Click += (object sender, RoutedEventArgs e) => {
    MessageBox.Show("Yes");
  };
}
```

## FindName

En metod som letar igenom alla sub-objekt efter något med angivet `x:Name`. Det man får som resultat är alltid bara ett generellt object, så resultatet behöver castas.

```csharp
if (FindName("mainButton") is Button button)
{
  button.Content = "New text for button";
}
```

## \<Button>

```
<Button>Click Me</Button>
```

## \<TextBlock>

```
<TextBlock Text="Hello" FontSize="56" />
<TextBlock>Goodbye</TextBlock>
```

## \<StackPanel>

```
<StackPanel Margin="10">

</StackPanel>
```

## \<CheckBox>

```
<CheckBox Checked="HandleCheck">Option 1</CheckBox>
<CheckBox>Option 2</CheckBox>
<CheckBox>Option 3</CheckBox>
```

## \<RadioButton>

```xaml
<RadioButton>Radio 1</RadioButton>
<RadioButton>Radio 2</RadioButton>
<RadioButton>Radio 3</RadioButton>
```

## \<Image>

## \<ListBox>

##
