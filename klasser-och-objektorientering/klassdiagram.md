# Klassdiagram

Ett klassdiagram beskriver hur en klass är strukturerad, och ser likadant ut oavsett programmeringsspråk. Diagrammet här skulle t.ex. kunna omvandlas till kod i Java, C\#, PHP eller vilket annat språk som helst som har objektorientering.

I ett klassdiagram beskrivs klassen i tre sektioner:

* Klassnamnet — i det här fallet "Character".
* Variabler — i det här fallet hp och name.
* Metoder — i det här fallet Hurt och Attack.

**Variablerna:** Skrivs med namn och datatyp, men aldrig värde. Oftast skriver man namnet först, sedan kolon, och slutligen datatypen.

**Metoderna:** Skrivs med namn, parametrar och returtyp, men aldrig funktion. Oftast skriver man namnet först, sedan parametrarna inom parentes \(i samma form som man skrev variablerna\), och slutligen vilken datatyp metoden returnerar.

**Synlighet:** Man anger synlighet för variabler och metoder genom att skriva +, - eller \# innan namnet.

* + betyder "public"
* - betyder "private"
* \# betyder "protected"

![](../.gitbook/assets/image%20%2816%29.png) 

## Arv i klassdiagram

För att visa [arv ](arv.md)i klassdiagram används pilar.

Pilarna pekar alltid FRÅN subklassen TILL basklassen.

Man behöver generellt inte skriva in alla variabler och metoder som ärvs från basklassen i subklassens diagram. Undantaget är ifall man använder [override](polymorfism/virtual-override.md).

![](../.gitbook/assets/image%20%2819%29.png) 

## NClass

Nclass är ett enkelt program för att skapa klassdiagram. Det är gratis och [kan laddas ner här](http://www.google.com/url?q=http%3A%2F%2Fnclass.sourceforge.net%2F&sa=D&sntz=1&usg=AFQjCNH-E6IhpQ3vcfOLuWdAaRHZ_8__-Q).

