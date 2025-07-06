<!--
author:   Sebastian Zug, André Dietrich

email:    Sebastian.Zug@informatik.tu-freiberg.de

version:  0.0.3

language: de

narrator: Deutsch Male

mode:     Presentation

comment:  Dieser Kurs für in das Projekt LiaScript ein und diskutiert die
          Vorteile im Kontext der OER Idee.

logo:     ./images/logo.png

import:   https://raw.githubusercontent.com/liaTemplates/ABCjs/main/README.md
          https://raw.githubusercontent.com/LiaTemplates/BeforeAndAfter/0.0.1/README.md
          https://raw.githubusercontent.com/LiaScript/CodeRunner/master/README.md

link:     ./style.css

translation: Deutsch  translations/German.md

@style
.flex-container {
    display: flex;
    flex-wrap: wrap; /* Allows the items to wrap as needed */
    align-items: stretch;
    gap: 20px; /* Adds both horizontal and vertical spacing between items */
}

.flex-child { 
    flex: 1;
    margin-right: 20px; /* Adds space between the columns */
}

.flex-child-liacode {
     flex: 1;
     background-color:rgb(255, 255, 255); 
     flex-wrap: wrap;
     margin-right: 20px;
}

@media (max-width: 600px) {
    .flex-child {
        flex: 100%; /* Makes the child divs take up the full width on slim devices */
        margin-right: 0; /* Removes the right margin */
    }
}
@end

-->

[![LiaScript](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/LiaScript_Meets_OPAL/refs/heads/main/README.md)

# LiaScript Meets OPAL


<section class="flex-container">

<!-- class="flex-child" style="min-width: 250px;" -->
><h3>Anleitung für die Einbettung von LiaScript-Kursen in OPAL</h3>
> 
><h4>Die Integration des LiaScript Interpreters in OPAL, wurde durch die Technische Universität Chemnitz und die Technische Universität Bergakademie Freiberg ermöglicht und durch die BPS GmbH umgesetzt wurde.</h4>
>
> André Dietrich, Sebastian Zug
> 
> Freiberg, Juli 2025

<!-- class="flex-child" style="min-width: 250px;" -->
![partner_map](pic/LiaScript_Meets_OER.png "OER-Logo - Quelle: Jonathasmello - Eigenes Werk, CC BY 3.0, [https://commons.wikimedia.org/w/index.php?curid=18460156](https://commons.wikimedia.org/w/index.php?curid=18460156) erweitert um LiaScript Logo")

</section>

--------------------------------------------

<!-- class="reference" -->
> Dieser Kurs gibt einen kurzen Überblick über die Konzepte von LiaScript, illustriert an Beispielen einige der Features und beschreibt die zwei Optionen für die Integration in OPAL. Sie können anhand der Buttons am unteren Bildrand oder mit den Pfeiltasten durch die Folien navigieren.
> 
> _Der Quellcode dieses Open Source Dokuments ist unter [Link](https://github.com/SebastianZug/LiaScript_Workshop_Lehrende_an_Schulen/blob/main/Motivation.md) zu finden._


## LiaScript Kernkonzepte

LiaScript wird als __Beschreibungssprache__ für __interaktive Lehr-Lern-Inhalte__ seid 2017 an der TU Bergakademie Freiberg entwickelt. Die Idee ist es, Lehrinhalte in einem Format zu beschreiben, das einfach durch den Browser interpretiert werden kann, in LMS integrierbar ist und gleichzeitig die Vorteile von __OER (Open Educational Resources)__ adressiert. 

Daraus resulieren vier Kernkonzepte:



{{1-5}}
> __1. Wir trennen Darstellung und Inhalt! Alle Elemente werden soweit wie möglich durch eine rein textuelle Repräsentation ausgedrückt.__

                        {{1-2}}
*******************************************************

Die Inhalte eines Textdokuments, das Elemente der Beschreibungssprache Markdown aufgereift, wandelt der Browser für den Lernenden in eine entsprechende Darstellung um.

<section class="flex-container">

<!-- class="flex-child-liacode" style="min-width: 250px;" -->
> ```markdown
> Das ist ein Text mit unterschiedlichen Formatierungen. __Fett__, _kursiv_ oder ~durchgestrichen~.
> 
> Hier folgt nun etwas Mathematik $f(x) = x^2$ und eine Aufzählung 
> 
> + Punkt 1
> + Punkt 2
> 
>    + Punkt 2a
> ```

<!-- class="flex-child" style="min-width: 250px;" -->
> Das ist ein Text mit unterschiedlichen Formatierungen. __Fett__, _kursiv_ oder ~durchgestrichen~.
> 
> Hier folgt nun etwas Mathematik $f(x) = x^2$ und eine Aufzählung 
> 
> + Punkt 1
> + Punkt 2
> 
>    + Unterpunkt 2a

</section>

<!-- class="reference" -->
> Das machen Markdown, Latex und HTML auch ... wo ist der Vorteil von LiaScript?


*******************************************************

{{2-5}}
> __2. Lehre lebt von Interaktion!__

                        {{2-23}}
*******************************************************

Ändern Sie die Sortierreihenfolge innerhalb der Tabelle, illustrieren Sie die Aussage anhand des intelligenten Diagrammgenerator und lösen Sie das Quiz.

<section class="flex-container">

<!-- class="flex-child-liacode" style="min-width: 250px;" -->
> ```markdown
> __Tabellen als Grafiken__
> 
> | X | B(y) | C(y) |
> |---|:----:|:----:|
> | 1 |   2  |   3  |
> | 4 |   5  |   6  |
> 
> __Quizze__
> 
> Wann wurde die TU Bergakademie gegründet?
> 
> - [(X)] 1765
> - [( )] 1896
> ```

<!-- class="flex-child" style="min-width: 250px;" -->
> __Tabellen als Grafiken__
> 
> | X | B(y) | C(y) |
> |---|:----:|:----:|
> | 1 |   2  |   3  |
> | 4 |   5  |   6  |
> 
> __Quizze__
> 
> Wann wurde die TU Bergakademie gegründet?
> 
> - [(X)] 1765
> - [( )] 1896

</section>

*******************************************************

{{3-5}}
> __3. Der Browser kann viel mehr als Webseiten anzuzeigen.__

                        {{3-4}}
*******************************************************

In den vergangen Jahren entstanden aus der LiaScript-Community heraus verschiedene JavaScript-Plugins aus unterschiedlichen Wissensbereichen, die spezifische Inhalte interaktiv aufbereiten. Führen Sie die ABC Noten Notation aus - der Browser wird interpretiert und die Noten werden als Musikstück abgespielt.


<section class="flex-container">

<!-- class="flex-child-liacode" style="min-width: 250px;" -->
> ````markdown
> ``` abc
> X:353
> T: GLUECK AUF DER STEIGER KOEMMT
> N: E1512
> O: Europa, Mitteleuropa, Deutschland
> R: Staende -, Bergmanns - Lied
> M: 4/4
> L: 1/16
> K: G
> | G8F4A4 | G8z8 | B8A4c4 | B8z4G2A2 | B4B4B4A2B2 | c4A3AA4
> A2B2 | c4c4c4B2c2 | d4B3BB4A4 | G8F8 | G4e4d4c2A2 | B8A8 | G8z8
> ```
> @ABCJS.eval
> ````

<!-- class="flex-child" style="min-width: 250px;" -->
> ``` abc
> X:353
> T: GLUECK AUF DER STEIGER KOEMMT
> N: E1512
> O: Europa, Mitteleuropa, Deutschland
> R: Staende -, Bergmanns - Lied
> M: 4/4
> L: 1/16
> K: G
> | G8F4A4 | G8z8 | B8A4c4 | B8z4G2A2 | B4B4B4A2B2 | c4A3AA4
> A2B2 | c4c4c4B2c2 | d4B3BB4A4 | G8F8 | G4e4d4c2A2 | B8A8 | G8z8
> ```
> @ABCJS.eval

</section>


*******************************************************

{{4-5}}
> __4. Vorlesungen als OER kollaborativ entwickeln.__

                        {{3-4}}
*******************************************************

Durch die Trennung von Inhalt und Darstellung können Lernende in die Entwicklung von Lehrinhalten eingebunden werden. Dies motiviert Studierende zusätzlich und förder die Identifikation mit der Lehrveranstaltung.

Das Video zeigt die Zusammenarbeit verschiedener Lehrender und Lernender im Kontext der Infomatiklehre in Freiberg über mehrere Jahre. 

!?[](./pic/Student_as_Coauthors.mp4)

*******************************************************

## Beispielfeatures

<!-- class="reference" -->
> Aktivieren Sie die automatische Übersetzung der Inhalte, um Lernende aus anderen Ländern zu unterstützen. Die Implementierung nutzt die Google Übersetzungs-API und evaluiert sorgfältig, welche Inhalte zu überführen sind - Webseiten, Eigennamen, Formeln bleiben unverändert.

![](./pic/translation.jpg "Aktivierung des Übersetzungsfeatures in LiaScript")

### Quizze

<!-- class="reference" -->
> LiaScript unterstützt eine Vielzahl von Quizformaten (Lückentext, Multiple-Choise, Drag&Drop, Rechenaufgaben). Diese können neben der eigentlichen Fragestellung mit zusätzlichen Informationen versehen werden, die den Lernenden helfen, die Frage zu beantworten.

Das kleine Beispiel reagiert noch nicht intelligent - die Hinweise sind statisch konfiguriert. In der Praxis können diese Hinweise aber dynamisch generiert werden, um den Lernenden zu helfen, die Frage gezielt zu beantworten.

__Beispiel für mathematische Aufgabe__

 Was ist das Ergebnis von $37 + 15$?

[[52]]
[[?]] Die Lösung ist größer als 50.
[[?]] Die Lösung ist kleiner als 55.
[[?]] Es solte eine gerade Zahl sein.
***********************************************************************

52 is the correct solution, you get this by adding:

``` ascii
                        .------.
                        |      |
                        |      v
                        |
                        |     (1)
  37           3(7)     |     (3)x          37
+ 15         + 1(5)     |   + (1)x        + 15
---- -->     ------ --> |   ------ -->    ----
  ??           (12)     |     (5)2          52
                |       |                 ====
                '-------'
                  carry
```

***********************************************************************
falstrad
__Beispiel für einen Lückentext__

I (learn) [[  have been learning  ]] English for seven years now.
But last year I (not / work) [[ was not working ]] hard enough for English,
that's why my marks (not / be) _[[ were not ]]_ really that good then.
As I (pass / want) [[ want to pass ]] my English exam successfully next year,
I (study) ~[[ am going to study ]]~ harder this term.


Die Beschreibung der Aufgabenformate findet sich in der Dokumentation im Abschnitte [Quiz Types](https://liascript.github.io/course/?https://raw.githubusercontent.com/liaScript/docs/master/README.md#68). 

### 2D Visualisierungen 

<!-- class="reference" -->
> 2D Grafiken können entweder anhand von Bildern oder generierten Diagrammen erzeugt werden. Ausgehend davon eröffnen sich dann vielfältige Interaktionsmuster.

<!-- style="max-width: 78vh;" -->
@beforeAndAfter(https://mediathek.tu-freiberg.de/eas/partitions-inline/2/0/80000/80790/feeb4ee9cc5e44f2731e2a764eae56a9cf599e8f/image/png,https://mediathek.tu-freiberg.de/eas/partitions-inline/2/0/81000/81387/2b9379093c840e6a716411ea85ac5d6ee5459188/image/png)



### 3D Visualisierungen / Simulationen 

<!-- class="reference" -->
> LiaScript unterstützt die Einbettung von 3D-Modelle oder Simulationen zu integrieren, die aus unterschiedlichen Quellen stammen können. Die Modelle können interaktiv im Browser betrachtet werden und bieten eine Vielzahl von Möglichkeiten, komplexe Konzepte zu veranschaulichen.

??[Familienschacht](https://sketchfab.com/3d-models/familienschacht-freiberg-germany-7c7d30506c554385a4a4321366e2e601 "sketchfab.com https://sketchfab.com/3d-models/familienschacht-freiberg-germany - https://sketchfab.com/3d-models/familienschacht-freiberg-germany")

??[](https://tinyurl.com/yrt9xz6n "Paul Falstad, 8 Bit Flash ADC Wandler - https://www.falstad.com/circuit/ ")

### Programmierumgebungen 

<!-- class="reference" -->
> Ihr Browser unterstützt nativ die Ausführung von JavaScript Code. LiaScript erweitert mit einem Coderunner-Server diese Möglichkeit auf aktuell 38 Programmiersprachen. Die Ausführung erfolgt serverseitig und die Ergebnisse werden im Browser angezeigt.

Führen Sie den Code mit dem kleinen Symbol unter dem Beispiel aus ... oha, es gibt einen Fehler. Korrigeren Sie den Code.

```python
print("Geben Sie die Anzahl der Iterationen an:")
iterations = input()
for i in range(iterations):
    print("Hallo Welt", i)
```
@LIA.python3

## Integration in OPAL



## Fazit


LiaScript löst den Inhalt vom LMS und erlaubt die Anwendung von Methoden der verteilten Softwareentwicklung.

- Beschreibungssprache
- Verteilte Entwicklung
- Serverlose Infrastruktur
- Dynamische Inhalte


Weitere Informationen finden Sie unter der Projektwebseite [https://liascript.github.io/](https://liascript.github.io/) in der [Dokumentation](https://liascript.github.io/course/?https://raw.githubusercontent.com/liaScript/docs/master/README.md#1) oder dem [Youtube-Channel](https://www.youtube.com/channel/UCyiTe2GkW_u05HSdvUblGYg)

