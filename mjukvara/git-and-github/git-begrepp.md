# Git-begrepp

#### Repository / "Repo" <a id="h.p_IpODJFJYYoTr"></a>

En "projektmapp" som bevakas av Git och som innehåller dels projektets filer så som de ser ut just nu, och dels "commits" – avbildningar av hur filerna sett ut vid tidigare tillfällen.

Kan vara local \(på den egna datorn\) eller remote \(på en annan dator\).

Ofta kopplar man ihop ett lokalt repository med ett remote, och synkroniserar mellan dem medan man arbetar.

#### Commit <a id="h.p_3dvDFec7X3Rb"></a>

En ögonblicksbild av filerna i projektmappen. Kan beskrivas som en "version" av projektet.

Medan man arbetar gör man normalt commits löpande. Man kan alltid gå tillbaka till en tidigare commits, och se vad som ändrats mellan olika commits.

Man kan välja vilka filer som ska ingå i en commit.

#### Pull <a id="h.p_AqhNuTW1YdhD"></a>

Man laddar ner alla nya commits från ett remote repository.

#### Push <a id="h.p_kUW0AycwfkMA"></a>

Man laddar upp alla sina nya commits till ett remote repository.

#### Branch <a id="h.p_Ffj6SJ3xYugM"></a>

Används när man är flera som jobbar på olika delar av samma lite större projekt. När man skapar en egen branch så kan man fritt göra ändringar i denna bransch utan att det ställer till saker för andra. När man är klar med arbetet kan man "merge:a" sin branch med huvud-branchen och då bestämma vilka av ens ändringar som ska behållas.

