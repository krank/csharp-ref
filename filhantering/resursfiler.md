# Resursfiler

Ofta jobbar vi med filer som ska finnas i samma mapp som vårt program, eller i en filsökväg relativt programmet.

När vi använder F5 för att köra programmen i Visual Studio Code antas det att den mappen är samma som Program.cs ligger i.

Om vi däremot skickar vår färdiga exe-fil till någon, så kommer den mappen att vara den som exe-filen ligger i.

För att automatiskt se till att alla filer kopieras till samma mapp som exe-filen, vilket underlättar distribution, används det här knepet:

1. Skapa en mapp vid namn "assets" i din projektmapp.
2. Redigera din csproj-fil och stoppa in detta innan &lt;/project&gt;:

```text
<ItemGroup>
  <Content Include="assets\**\*.*">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
</ItemGroup>
```

Det gör att det automatiskt skapas en "assets"-mapp där exe-filen läggs \(t.ex. i bin\debug\net5.0 eller liknande\), och alla filer etc från din assets-mapp kopieras dit.

