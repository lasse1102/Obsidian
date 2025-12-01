
--- 
Erstellt: 2025-02-13    12:36 
Tags: #IT/Hardware
Link Up: [[Komponenten]]
Link Down: 

--- 
#### **1. Kommunikation in Binärcode**
- Computer verstehen nur [[Binär|**Binärzahlen (1 und 0)**]].
- Menschen nutzen natürliche Sprachen (z. B. Englisch, Spanisch), während Computer in **Maschinensprache** arbeiten.
- Um mit Computern zu kommunizieren, benötigt man eine **Übersetzung** – Programme und Betriebssysteme übernehmen diese Aufgabe.

#### **2. Programme und Speicherung**
- **Programme** sind Sammlungen von Anweisungen, die dem Computer sagen, was er tun soll.
- Diese Programme werden auf **Speichermedien** wie Festplatten gespeichert.
- Vergleich: Programme sind wie **Rezepte in einem Kochbuch** – die Anweisungen müssen vom Computer ausgeführt werden.

#### **3. Der Prozessor (CPU) als zentrale Recheneinheit**
- Die [[CPU]] kann mit einem **Koch (Chef)** verglichen werden, der Rezepte (Programme) ausführt.
- Da die CPU sehr schnell arbeitet, werden **Anweisungen** nicht direkt aus der Festplatte geladen, sondern in den **Arbeitsspeicher (RAM)** kopiert.
- Vergleich:
    - Festplatte = Kochbuch mit vielen Rezepten (langsam). (Bilder. Programme...)
    - [[RAM]] = Arbeitsfläche, auf der der Koch die Zutaten vorbereitet (schneller Zugriff). (temporäre Daten)

#### **4. Datenübertragung im Computer**
- Informationen bewegen sich über den **Externen Datenbus (EDB)**, ein Netzwerk aus Leitungen, das verschiedene Komponenten verbindet.
- Vergleich: Der EDB funktioniert wie **Blutbahnen im Körper**, die Daten in Form von elektrischen Signalen transportieren.
- Bits werden durch Spannung dargestellt:
    - **1 = Spannung an (Strom fließt)**
    - **0 = Spannung aus (kein Strom)**
- Unterschiedliche Busbreiten (8-bit, 16-bit, 32-bit, 64-bit) bestimmen, wie viele Daten gleichzeitig übertragen werden können.

#### **5. Register und interne Verarbeitung in der CPU**
- Die CPU speichert Daten in **Registern**, die sehr schnell zugänglich sind.
- Beispiel für eine Addition:
    - Wert A wird in Register **A** gespeichert.
    - Wert B wird in Register **B** gespeichert.
    - Das Ergebnis wird in Register **C** abgelegt.
- Vergleich: Die Register sind wie **die Arbeitsfläche des Kochs**, wo er Zutaten schnell bereitstellen kann.
#### **6. Zugriff auf den Arbeitsspeicher (RAM) über den Speichercontroller (MCC)**
- Der **Memory Controller Chip/Speichercontroller (MCC)** verwaltet den Zugriff auf den RAM und sendet benötigte Daten an die CPU.
- Der Speichercontroller stellt sicher, dass Daten in den RAM geschrieben und abgerufen werden (Effizienter und Schneller)
- Untergebracht ist der Speichercontroller entweder direkt im Prozessor oder auf dem Mainboard, dort meistens in der Northbridge.

### Die Kommunikation zwischen CPU und RAM
1. [[CPU]]
	Wenn die CPU eine bestimmte Information benötigt, schickt sie eine Anfrage über den **Adressbus** an den Speichercontroller (MCC). Diese Anfrage enthält die Speicheradresse der gewünschten Daten im RAM
2. Speichercontroller
	Der Speichercontroller empfängt die Adresse und lokalisiert die entsprechenden Daten im [[RAM]]
3. EDB
	Die gefunden Daten werden über den External Data Bus zur CPU transportiert
4. CPU
	Die CPU empfängt die Daten und verarbeitet sie weiter

#### **7. Cache-Speicher für schnellere Zugriffe**
- Neben RAM hat die CPU einen **Cache-Speicher**, der oft benötigte Daten speichert.
- **Drei Ebenen von Cache:**
    - **L1 (sehr klein, extrem schnell)**
    - **L2 (größer, langsamer als L1)**
    - **L3 (noch größer, langsamer als L2, aber schneller als RAM)**
- Vergleich:
    - [[RAM]] = **Kühlschrank** (viel Platz, aber langsamer Zugriff).
    - Cache = **Tasche in der Schürze des Kochs** (klein, aber sehr schnell zugänglich).

#### **8. Synchronisation mit der CPU-Taktfrequenz**
- Die CPU arbeitet in definierten **Takten**, gesteuert durch eine **Taktleitung**.
- Jeder Takt erlaubt eine **Operation**.
- Taktfrequenz wird in **GHz (Gigahertz)** gemessen:
    - **3.4 GHz = 3,4 Milliarden Takte pro Sekunde**.
- Vergleich: Die Taktleitung ist wie **ein Metronom für einen Musiker**, das den Rhythmus vorgibt.

#### **9. Übertakten der CPU (Overclocking)**
- **Overclocking** bedeutet, die Taktfrequenz der CPU zu erhöhen, um mehr Berechnungen pro Sekunde auszuführen.
- Wird oft von Gamern genutzt, um eine höhere Leistung zu erzielen.
- Risiko: **Erhöhte Wärmeentwicklung**, was zu Schäden führen kann.

---

### **Fazit**

- Die CPU ist das **Gehirn des Computers** und führt alle Berechnungen durch.
- Daten reisen über den **Datenbus** zur CPU, die sie in **Registern** speichert und verarbeitet.
- **RAM und Cache-Speicher** sorgen für schnelleren Zugriff auf häufig genutzte Daten.
- Die **Taktfrequenz** bestimmt, wie schnell Berechnungen durchgeführt werden können.
- Mit **Overclocking** kann man die CPU-Leistung steigern, allerdings mit dem Risiko von Überhitzung.

## References
1. [[CPU Taktfrequenz und übertakten]]
