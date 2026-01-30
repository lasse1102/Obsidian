
--- 
Erstellt: 2026-01-21    09:24 
Tags: 
Link Up: 
Link Down:

--- 
# Präsentation Text

**Text(stichpunktartig)**
- Ja Herzlich Willkommen zu meiner Projekt Präsentation. Mein Name ist Lasse Pöhls ich mache meine Ausbildung bei OKLogistics und ich stelle Ihnen heute mein Abschluss Projekt vor, indem es darum ging eine webanwendung zu schreiben, welche Statistiken bereitstellt für Kommissionier Aufträge.

- Ja, Werfen wir zu aller erst ein kurzen Blick auf die Agenda: Wir starten am Anfang mit einer kurzen Vorstellung meines Ausbildungsbetriebs. Anschließend steigen wir direkt in die Analyse ein, wo ich so ein bisschen drauf eingehe, warum dieses Projekt überhaupt entstanden ist wie es davor gemacht wurden ist und was das Ziel des Projektes ist. Darauf Aufbauend zeige ich Ihnen den Entwurf und die anschließende Implementierung der Anwendung und zu guter letzt dann noch einmal ein kleines Fazit und ein Ausblick für bevorstehende Änderungen in dem Projekt.

- Genau kommen wir einmal zu mein Ausbilungsbetrieb. OKLogistics wurde 2006 gegründet und beschäftigt heute rund 100-150 Mitarbeiter auf 2 Standorten. Hier im Hintergrund sehen wir den Standort Hohenwestedt dort wo ich auch meine Ausbildung mache und der 2 Standort liegt in Boizenburg. Ja wie am Namen schon zu erkennen sind wir ein Logistikunternehmen und kümmern uns im wesentlichen um die Lagerung und den Versang von Waren für unsere Kunden. In meinen Projekt geht es speziell um die Kommissionierung, also das Zusammenstellen von Prodkten im Lager.

- Ja machen wir weiter mit der Analyse. 

- Beginnen wir mit dem Ist-Zustand und wie das vorher gemacht wurden ist?  Ja Vorher gab es 2 getrennte Systeme die solche Statistiken generieren können, diese hatten aber 1-2 enstscheidene Nachteile. Das eine System verfügte zwar über eine große Menge von Daten, ähm der Nachteil daran ist nur das die Perfomance extrem einstürtze ist und es zu verlängerten Ladezeiten geführt hat. Und das waren jetzt nicht nur ein paar sekunden sondern gerade bei abfragen über ein großen Zeitraum kann dies auch mal gerne mehr als 1min dauern. Und ja das würde jedes mal sehr sehr viel Zeit in anspruch nehmen immer so lange zu warten. Das andere System, welches auch genau deswegen mal erstellt wurden ist, kann die Statistiken zwar schnell laden, also hat eine höhere Performance, das Problem hierbei ist nur das die Datenhistorie mittlerweile nicht mehr aussreicht, also wir haben hier vielleicht Daten aus den letzten paar Monaten zur Verfügung aber mehr auch nicht.

- Ja da kommen wir auch dann direkt zu den Zielen des Projektes, das Hauptziel war es halt dann eine Lösung zu finden, welche genau diese Nachteile ausgleicht und eine Anwendung erstellt, welche sowohl eine hohe Performance hat als auch Daten über Jahre hinweg problemlos abrufen kann.  Ein andere Aspekt war auch noch das, dass alte System relativ altmodisch war und somit auch nicht mehr richtig benutzerfreundlich, somit war meine Aufgabe auch das ganze schick zu gestalten.

- Auch ein wichtiger Punkt ist die Wirtschaftlichkeit des Projektes. Hierzu habe ich einmal die Projektkosten berechnet. Da ich hier nicht mit den echten Stundenlöhnen arbeiten konnte, habe ich Referenz Werte genommen. Hier waren es jetzt einmal 10€ für mich als Auszubildender und 35€ die Stunde für ein normalen Mitarbeiter. Am Ende sind wir dann auf eine Endsumme von insgesamt 1115€ gekommen, welche sich zusammensetzte aus den Vorgängen Entwicklung, das Fachgespräch, welches ich mit dem Abteilungsleitern aus dem Lager gemacht habe die, die die Anwendung im wesentlichen Nutzen, dann noch einmal die Code Review und die Abnahme des Projektes.

- Darauf aufbauen habe ich dann einmal die Amortisationsdauer berechnet, um zu prüfen ob sich das Projekt auch wirklich finanziell lohnt. Die einmaligen Kosten, also die 1115€ sind in der Grafik blau dargestellt. Und die rote Linie zeigt die fortlaufende Kostenersparnis. Es ist gut zu erkennen, dass nach etwa **18 Wochen** der **Break-even-Point** erreicht wird, ab dem das Projekt einen finanziellen Vorteil erzielt.

- Machen wir weiter mit der Entwurfsphase, wie das Projekt unteranderem technisch umgesetzt wurde.

- Wir im Unternehmen arbeiten in einer klassischen 3 Schichten Architektur, um eine saubere Trennung zwischen der Benutzeroberfläche, der Logik und der Datenhaltung zu gewährleisten.
	Ja im Frontend setzten wir auf ein Kombination aus einer Template Engine von Twig, welche speziell für PHP entworfen wurden ist, dann nutzen wir für dynamische Inhalte JavaScript, welches ich in mein Projekt auch öfters verwendet habe als gedacht. Und für das Designen der Anwendung nutzen wir hier Bootstrap 5.
	Ja und im Backend nutzen wir wie gerade schon erwähnt PHP, welches wir einem Microframework von Slim nutze, dieses bietet den vorteil, das es deutlich flexibler ist und nicht so streng ist wie die typischen PHP Framework wie Laravel oder Symphony. Und da wir unsere Datenbankabfragen auch direkt in PHP schreiben nutzen wir hier noch ein Query Build von Doctrine, welcher uns ermöglicht direkt die sql abfragen in PHP zu schreiben.
  Genau und für die Datenhaltung nutzen wir PostgreSQL Datenbanken


- Hier sehen wir einmal ein MockUP, von der Anwenung, wie die Benutzeroberfläche später aussehen soll. Dieses wurde am Anfang im zusammenarbeit mit den Abteilungsleitern des Lagers erstellt.
  Hier auf der linken seite sehen wir einmal die Filterfunktion, wo wir unteranderm den Standort auswählen können, den Zeitraum von wann bis wann wir die Statistiken sehen wollen. Und die auswahl von Kunden welche wir sehen wollen.
  Ja basierend zu den Filter werden dann die Tabellen, wie wir hier rechts sehen generiert. Diese zeigen dann für jeden Tag und für jeden ausgewählten Kunden alle Werte an. Zum Beispiel haben wir hier am 12.09.25 für den Kunden BNE 396 Aufträge erledigt.
  Ja und die grünen Kästchen hier oben sollen die Durchschnittswerte pro Tag demonstrieren.

  - Ja kommen wir nun zu der Implementierung der Awendung

- Um einmal zu den Ablauf der Anwendung zu verdeutlichen habe ich hier einmal ein Aktivitätsdiagramm erstellt, welches passend zur Architektur der Anwenung in Frontend/Backen/Datenbank unterteillt ist.
  Die Anwendung beginnt wie üblich im Frontend, indem der Nutzer den Filter setzt und abschickt. 
  Anschließend werden dann im Backend die übermittelten Filterparameter abgerufen und validiert. Mit diesen Daten werden dann aus der Datenbank die erforderlichen Daten abgerufen und die Ergebnisse werden wieder zurückgeschickt.
  Anschließend beginnt dann die gesamte Geschäftslogik im Backend. Die Daten werden dort verarbeitet und auferarbeitet für die Darstellung im Frontend. Dazu gehören dann unter anderem die berechnung der Durchschnittswerte, die generierung der Tabellenstruktur und die Prozentsätze berechnet, dann werden die Datenstrukturen an das Frontend wieder zurückgegeben, wo dann mit dem Twig Template die Daten gerendert werden


- Um das anhand von Code Beispielen noch mal genauer zu zeigen, habe ich hier mal eine Route eingeblendet, welche immer dann aufgerufen wird, wenn die Seite geladen wird.
  Zu aller erst werden hier die Werte aus dem Filter abgerufen, in diesem Fall sind das alles Standart bzw. Default werte, da der Nutzer beim Aufrufen der Seite ja noch kein Filter eingegebne hat.
  Anschlieden werden diese Werte aus dem Filter an unsere Service Klassen übergeben, wo dann die Datenbank abfragen ausgeführt werden und die Logik erstellt wird. So die Ergebnisse bekommen wir hier dann zurück und diese geben wir dann schließlich wieder an das Frontend zurück, so wie wir hier sehen können.
  Ja und im großen und ganzen ist so eigentlich die Anwendung aufgebaut, wir haben verschiedene Routen, die für verschieden Funktionalität zuständig ist.

- Hier sehen wir dann nochmal wie die fertige Anwendung aussieht. Da können wir sehen das es sehr ähnlich zu den vorhin gezeigten MockUp aussieht. Hier oben linkts ist der Filter. Oben Rechts sind die Durschnittswerte und dadrunter haben wir die Tabellen.
  
  
- Genau kommen wir nun zum Fazit

- Im großen und ganzen kann man sagen, dass die Anforderungen erfolgreich erfüllt wurden. Auch die Abnahme verlief problemlos und es gab positives Feedback von den Nutzern der Anwendung.
  Rückblickend würde ich aber auch sagen, das ich ein wenig mehr Zeit in die Planung stecken können, um während der Entwicklung einige Probleme zu vermeiden
  Dennoch ist das Projekt insgesamt gut gelungen, wie ich mir das vorgestellt habe.

- Auch für die Zukunft sind bereits weitere Features geplant.
  Unteranderem sollen die Statistiken künftig nicht nur tabellarisch abgebildet werden, wie eben gezeigt. Sondern zusätzlich auch noch grafisch, in Form eines Liniendiagramms, welches den Vorteil hat, dass man direkt auf den ersten Blick erkennen kann an welchen Tagen mehr gemacht wurden ist und an welchen Tagen weniger, ohne in den Tabellen jetzt die ganzen Werte zu suchen.
  Außerdem haben wir seit neusten einen neuen Standort in Neumünster, und der muss ebenfalls noch integriert werden


- Das war meine Projekt Präsentation, vielen Dank fürs zuhören.



Wir werden hier in den kommenden wochen noch einmal die weiteren annehmn





**Falls Prüfer fragt, warum die Kostentabelle anders ist als die in der Doku**
- Dies liegt daran das ich die Aufteilung in der Präsentation genauer aufgeteilt habe. Zum Beispiel habe ich hier in der Code-Review mich als Auszubildenen auch noch mit rein genommen obwohl der meiste Anteil hier meine Ausbilderin gemacht habe













---
- OSI-Schicht Modell
- Testing (White Box, Black Box)
- SQL & Datenbank
	- Relationale Datenbanken
	- NO SQL
	- Normalisierung
	- ER-Modell
- UI/UX -> Passt zu meinen Projekt
- Objektorierntierung
	- Interfaces
	- Polymorphie
- Methoden von Darstellungsdiagrammen



# OSI Schicht Modell
![[Pasted image 20260123145607.png]]

---
# Testing 
TestEbene:
1. Unit Tests
	Es wird die kleinste Einheit im Code getestet (meistens eine einzelne Funktion oder Methode)
2. Integrations Test
	Prüfen ob Komponenten richtig miteinander kommunizieren (Beispiel z.B Datenbank, API)
	Prüft das Zusammenspiel mehrere Komponenten 
3. Systemtest
	Prüfen ob das ganze System funktioniert (Erfüllt es den fachlichen Anforderungen)
4. Abnahmetest


Testmetode
5. Backbox-Testing
	Der Tester Testet das Verhalten des Systems, ohne den Code zu kennen
6. Whitebox-Testing
	Hier wird der Code selbst getestet, der Tester kennt das Innenleben der Anwendung also den Code


Vorgehensweisen
1. Manuelles Testen
	Tests werden von Menschen durchgeführt, ohne Testtools
2. Automatisiertes Testen
	Tests werden per Code automatisch ausgeführt
3. Regressionstest

Qualitätsaspekte (Beschreibt wie gut eine Software ist, nicht was sie macht)
- Funktionalität 
	Die Software erfüllt die geforderten Funktionen korrekt und vollständig
- Zuverlässigkeit
	Die Software läuft stabil, fehlerarm
- Benutzerfreundlichkeit
	Die Software ist leicht verständlich, und angenehm zu bedienen
- Wartbarkeit
	Die Software lässt sich leicht ändern, erweitern und reparieren



## 6️⃣ Mögliche Prüfungsfragen (mündlich)
- „Was ist der Unterschied zwischen Unit-Tests und Integrationstests?“
- „Welche Testmethoden kennen Sie?“
	Man unterscheidet unter anderem **Blackbox- und Whitebox-Tests**, außerdem **manuelle und automatisierte Tests**.
- „Warum ist Testing wichtig?“
	Testing ist wichtig, um Fehler frühzeitig zu erkennen, die Qualität der Software sicherzustellen und spätere Kosten zu reduzieren.  
Außerdem erhöht es die Zuverlässigkeit und Wartbarkeit der Anwendung.
- „Wie dokumentieren Sie Ihre Tests?“
	Tests dokumentiere ich zum Beispiel über **Testfälle**, **automatisierte Testskripte**, **Testprotokolle** oder durch **Kommentare und Namen der Tests** im Code.
- „Wie würden Sie Regressionstests in Ihrem Projekt durchführen?“
	Regressionstests würde ich hauptsächlich **automatisiert** durchführen, indem bestehende Tests nach Änderungen erneut ausgeführt werden.
- „Erklären Sie den Unterschied zwischen Blackbox- und Whitebox-Testing.“
	Beim **Blackbox-Testing** wird das System ohne Kenntnis des Quellcodes getestet, nur anhand von Eingaben und erwarteten Ausgaben.  
Beim **Whitebox-Testing** kennt der Tester den Quellcode und prüft gezielt Logik, Bedingungen und Codepfade.


--- 

# UI/UX

#### UI (User Interface)
Alles, was der Benutzer sieht und mit dem er interagiert (Buttons, Menüs, Layouts).

### UX (User Experience)
Die Gesamterfahrung des Nutzers - wie einfach, angenehm und effizient er die Software nutzen kann.

Ziel: Software soll intuitiv, verständlich und effizient bedienbar sein

---

# Datenbanken 

**NoSQL**
NoSQL-Datenbanken sind **nicht relational**, speichern Daten oft **schemafrei** und sind für **große Datenmengen** und **hohe Skalierung** geeignet.
### Vergleichssatz (perfekt):

> Relationale Datenbanken sind stark bei **strukturierten Daten**, NoSQL bei **flexiblen und großen Datenmengen**.


**Normalisierung**
Normalisierung dient dazu, Redundanzen zu vermeiden und Daten konsistent zu halten.

Durch Normalisierung werden Daten sinnvoll auf mehrere Tabellen aufgeteilt, sodass Änderungen nur an einer Stelle erfolgen müssen.

**ER-Modell**
> Ein ER-Modell ist eine grafische Darstellung von Entitäten, Attributen und Beziehungen

Das ER-Modell hilft dabei, eine Datenbank vor der Umsetzung zu planen

---
# Objektorientierung

**Klasse vs Objekt**
- Eine Klasse ist der Bauplan oder eine Vorlage 
- Ein Objekt ist eine Instanz einer Klasse

**Vererbung**
Klassen können Eigenschaften von anderen Klassen erben

**Polymorphie**
Polymorhie erlaubt es Methoden unterschiedlich zu implementieren, obwohl sie gleich heißen

**Vorteil von Objektorientierung**
- Objektorientierung führt zu besserer Wartbarkeit, Wiederverwendbarkeit und Übersichtlichkeit von Code

---

# Design Patterns

**Was sind Design Pattern**
Design patterns sind wiederverwendbare Lösungsschablonen für häufig auftretende Probleme 

**Warum nutze man Design Patterns**
Sie vervessern die Wartbarkeit, Lesbarkeit und Erweiterbarkeit von Software


**Kategorien von Design Patterns**
Erzeugungsmuster:
	Objekte erzeugen
Strukturmuster:
	Klassen Struktorieren
Verhaltensmuster:
	Kommunikation zwischen Objekten

**3 Wichtigesten Patterns**
Singleton Pattern:
	Es gibt nur eine Instanz eine Klasse (Logger, Datenbankverbindung)
FactoryPattern:
	Es kapselt die Erzeugung von Objekten und erhöt die Flexibilität 
Observer:
	Objekte werden über Änderungen informiert, um gegebenfalls darauf zu reagieren


---
# Methoden und Darstellungsdiagramme

**Wasserfallmodell**
Lineares Vorgehensmodell mit festen Phasen wie Analyse, Design, Implementierung und Test

**Scrum**
Scrum ist eine agile Methode, bei der in kurzen Iterationen gearbeitet wird und regelmäßiges Feedback erfolgt.


## 2.1 Klassendiagramm (SEHR BELIEBT)

👉 **Was zeigt es?**
- Klassen
- Attribute
- Methoden
- Beziehungen

**Sequenzdiagramm**
Zeitlicher Ablauf von Objekt Interaktionen ( Benutzer-Controller-Service-Datenbank)

**Kanban** (Agile Methode)
Aufgaben werden auf einen Board dargestellt und durchlaufen verschieden Zustände (To-Do, In Bearbeitung, Done)












- 


## References
1. 
