# Filer och mappar



#### Exists <a id="h.p_et9sPwDmAsKJ"></a>

File.Exists är en metod som returnerar true om filen som anges som parameter existerar, false om den inte gör det.

```text
if (File.Exists(@"localfile.txt"))
```

```text
{
```

```text
  Console.WriteLine("The file exists!");
```

```text
}
```

#### Delete <a id="h.p_vG7QE75sA_i6"></a>

Tar bort den fil som anges som parameter.

```text
File.Delete(@"localfile.txt");
```

