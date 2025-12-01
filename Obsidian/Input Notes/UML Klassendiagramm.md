
--- 
Erstellt: 2025-10-08    14:06 
Tags: 
Link Up: 
Link Down:

--- 
#### Klassendiagramm
Das Klassendiagramm bildet das Herzstück des UML. Es basiert auf den Prinzipien der Objektorientierung  ([[Abstraktion]], Kapselung, Vererbung,...) und ist durch seine Vielseitigkeit in allen Phasen eines Projektes einsetzbar.
In Klassendiagrammen werden **Klassen und Beziehungen von Klassen** untereinander modelliert. Bei den Beziehungen kann man grob drei Arten unterscheiden. Die einfachste und allgemeinste Variante ist die Assoziation. Eine zweite modellierbare Beziehung ist die Aufnahme einer Klasse in eine zweite Klasse, die sogenannte Containerklasse. Solche Beziehungen werden Aggregation oder Komposition genannt. Eine dritte Möglichkeit ist die Spezialisierung bzw. Generalisierung.

### Beziehungen

#### Assoziation
Die Assoziation ist die allgemeinste Form einer Beziehung zwischen 2 oder mehreren Klassen. Sie gibt an, dass die Klassen in irgendeiner Weise miteinander verbunden sind oder miteinander kommunizieren können.
- **Bedeutung:**
	Eine Strukturelle Beziehung, die besagt das Objekte einer Klasse mit Objekten einer anderen Klasse verbunden sind. Es gibt keine starke oder schwache Abhängigkeit der Lebenszyklen
- **Beispiel:**
	Ein Schüler belegt ein Kurs. Der Schüler existiert auch ohne den Kurs und der Kurs existier auch ohne den Schüler.
- **Darstellung im Klassendiagramm:**
	Eine durchgezogene Linie zwischen den Klassen. Die Multiplizitäten sind oft (z.B. "1.." für ein oder mehrere).

---

# Aggregation / Komposition
Dies sind beides Teil-Ganzes Beziehungen. Bedeutet, das es eine Klasse welches das Ganze beschreibt. Und eine Klasse welches ein Teil des Ganzen beschreibt. Der einzige unterschied zwischen Aggregation und Komposition ist, in welchen Zusammenhang das Teil zum Ganzen steht, wenn sie das Ganze verändert.
- Wenn das Teil nicht weiter existieren kann ohne das Ganze, dann handelt es sich um eine Komposition.
- Wenn das Teil weiter existieren kann, ohne das Ganze, dann handelt es sich um eine Aggregation
<mark style="background: #FFB86CA6;">WICHTIG: Kompositionen, kommen in der Realität oder auch im Code kaum vor, meistens sind es immer Aggregationen</mark>

Im folgenden sind die beiden Beziehungen detaillierter erklärt.
#### Aggregation
Die **Aggregation** ist eine **spezialisierte Form der Assoziation**, die eine **Teil-Ganzes-Beziehung** (Part-Whole-Relationship) darstellt. Sie impliziert, dass ein Objekt (das "Ganze") aus anderen Objekten (den "Teilen") zusammengesetzt ist.
- **Bedeutung:** Eine schwächere Form der Teil-Ganzes-Beziehung. Der **Teil** kann **unabhängig vom Ganzen existieren**. Wenn das "Ganze" zerstört wird, existieren die "Teile" weiter. Man spricht auch von einer "Hat-ein/e"-Beziehung (A hat B).
- **Beispiel:** Eine Bibliothek **aggregiert** Bücher. Wenn die Bibliothek schließt, existieren die einzelnen Bücher weiterhin und können woandershin gebracht werden.
- **Darstellung im Klassendiagramm:** Eine **durchgezogene Linie** mit einer **leeren Raute** (◊) an der Seite der **Ganzt-Klasse** (dem Aggregat).

![[Pasted image 20251010073636.png]]
#### Komposition
Die **Komposition** ist die **stärkste Form der Teil-Ganzes-Beziehung** und eine **spezialisierte Form der Aggregation**.
- **Bedeutung:** Eine starke Abhängigkeit. Der **Teil** kann **nicht unabhängig vom Ganzen existieren**. Der Teil wird **erzeugt und zerstört** zusammen mit dem Ganzen. Der Teil kann immer nur zu **einem** Ganzen gehören.
- **Beispiel:** Ein Haus **besteht aus** Räumen. Ein Raum **kann nicht existieren**, wenn das Haus zerstört wird. Ein Raum gehört _immer_ zu genau einem Haus.
- **Darstellung im Klassendiagramm:** Eine **durchgezogene Linie** mit einer **gefüllten Raute** (■) an der Seite der **Ganzes-Klasse** (dem Kompositum).
![[Pasted image 20251010073753.png]]

#### Multiplizität
![[Pasted image 20251013082903.png]]

In der UML wird auch der Begriff **Kardinalität** verwendet, um die Anzahl konkreter Ausprägungen zu beschreiben
#### Zugriffsmodifikatoren
- Öffentlich (+)
- Privat (-)
- Geschützt (#)
- Paket (~)
- Abgeleitet (/)
- Statisch (unterstrichen)
### Aufbau
1. Name
2. Attribute
	1. Attributname : Datentyp = (Initialisierung)
3. Methoden
	1. Methodenname(Parameter: Datentyp): Rückgabewert
4. Getter und Setter
	- + setVehicle(string): void
	- - getVehicle (): string
Getter und Setter dienen nur als Beispiel, da das in einer Prüfung so dran kam
###### Vererbung
Die Unterklasse erhält alle Eigenschaften und Methoden der Oberklasse (Dargestellt durch eine geschlossenen Pfeilspitze)
![[Pasted image 20250227125559.png]]
In diesem Beispiel würde das Objekt „Auto“ (Car) alle Attribute 
(Geschwindigkeit, Mitfahrerzahl, Treibstoff) und Methoden (Los(), Stop(), Richtungswechsel()) der Parent-Klasse „Fahrzeug“ (Vehicle) annehmen.  
Hinzu kämen spezifische Attribute (Modelltyp, Türenzahl, Autohersteller) und Methoden (Radio(), Scheibenwischer(), Klimaanlage/Heizung()) der eigenen Klasse.



# Vererbung / Interfaces
- Vererbung: Klassen können von anderen (abstrakten) Klassen erben.
	- Vererbungen werden mit einer geschlossenen nicht ausgefüllten Pfeilspitze gemalt (Von der Sub Klasse zur Basis Klasse)
- Interfaces: Klassen können Interfaces implementieren
- Wird mit einer geschlossenen nicht ausgefüllten Pfeilspitze aber mit gestrichelten Strich(Von der Sub Klasse zur Basis Klasse)

#### Abstrakte Klassen / Methoden
Eine abstrakte Klasse ist eine Klasse, die nicht direkt erzeugt werden kann (Instanziiert). Sie dient als Vorlage oder Bauplan für Unterklassen.

<mark style="background: #FFB86CA6;">MEKRE: Aus einer abstrakten Klasse werden niemals Objekte erzeugt. Sie dient lediglich dazu Gemeinsamkeiten verwandter Klassen in einer gemeinsamen Oberklasse zu bündeln</mark>

Beispiel:
Es sollen die Klassen Konto, Aktien und Festgeld von einer gemeinsamen Elternklasse Geldanlage erben, in der festgelegt ist, dass wir über die Methode getAnlagewert() immer den aktuellen Zeitwert der Geldanalage erhalten.

![[Pasted image 20251104072127.png]]

Da das Guthaben zum Zeitwert beim `Konto` schlicht über den Kontostand, beim `Festgeld` über die Verzinsung der Einlage und bei einer `Aktie` über den aktuellen Börsenwert ermittelt werden muss, kann die Methode `getAnlagenwert()` nicht sinnvoll zentral in `Geldanlage` implementiert werden.
Wir können verdeutlichen, dass jede Unterklasse eine eigene Implementierung benötigt, in dem wir den Methodenrumpf leer lassen und lediglich die Signatur (also Name + Parameter) und der Rückgabewert festlegen: derlei Methoden nennt man _abstrakt_.

Gekennzeichnet werden sie in der Regel kursiv. 


# Polymorphie
Wenn man ein Objekt unterschiedlicher Unterklassen über den selben Basistypen (z.B. Tier) anspricht und sie sich unterschiedlich verhalten, dann ist es Polymorphie.

Der unterschied zu Abstraktion ist: Bei Abstraktion definieren wir eine gemeinsame Schnittstelle (eine abstrakte Klasse z.B.), die beschreibt was alle Unterklassen können sollen, aber nicht wie sie es macht. Mit Polymorphie implementieren wir dies in Unterklassen.













# Übungsaufgaben
![[Pasted image 20251017084612.png]]







![[Pasted image 20251017084629.png]]







![[Pasted image 20251017090525.png]]



![[Pasted image 20251017090544.png]]







## References
1. 
