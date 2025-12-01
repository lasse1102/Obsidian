
--- 
Erstellt: 2024-04-11    14:54 
Tags: 
Link Up: [[Internal Shop]]
Link Down:

--- 
# Grundvoraussetzung
- Produkte werden auf einer Liste von Träger LHM's gelagert
- Wenn ware rauf gebucht wird, muss die DB geupdatet werden
- Bei einer Buchung auf eine Träger LH, muss die endgültige Entfernung festgehalten werden
- Wenn Mitarbeiter ware abholt, bucht er sie auf sein Lagerplatz und von dort ins Nirvana
- Es muss ein Auftrag erstellt werden
- Durchlassschein muss erstellt werden
	- Durchlassschein muss ins WMS exportiert werden
- Nicht "Wer zuerst kommt, mahlt zuerst" -> Fair Verteilung

# Produktverteilung
### Lösung 1
- Alle verfügbaren Produkte aus der DB auf
- Jeder Benutzer kann sich eintragen bei den Produkten die er will (kein Limit)
- Am Ende jeden Monats wird per Zufallsprinzip ausgelost, angefangen mit den Produkt was für was sich die meisten eingetragen haben bis hin zum Produkt indem sich die wenigsten eingetragen haben  
-  Es werden immer die Leute bevorzugt, die am wenigsten Produkte bekommen haben, heißt wenn 10 Leute sich für ein Produkt eingetragen haben, aber 5 von den Leuten schon mindestens ein Produkt gewonnen haben, wird dieses Produkt an die 5 Leute ausgelost, welche noch kein Produkt gewonnen haben. Erst, wenn alle schon ein Produkt gewonnen haben, wird unter den Leuten ausgelost, die ein Produkt gewonnen haben, nicht aber unter die, die mehr als eins gewonnen haben. Dies setzt sich fort, bis das Produkt ausgelost werden kann.
- Produkte können Kategorisiert werden
	-  Artikeltyp
	- Wert
	- Zustand des Artikels

|   |   |
|---|---|
|Vorteile|Nachteile|
|- Auch unbeliebte Produkte werden höchstwahrscheinlich ausgelost, da man sich bei unbegrenzt vielen Produkten eintragen kann<br>- Die Leute werden bevorzugt, die weniger bekommen haben (Faire Verteilung)|- Es wird ein Anreiz geschaffen, sich auch bei Produkten eintragen, die man eigentlich nicht haben will, was dazu führen kann, dass dieselben Produkte im Müll landen|

### Lösung 2
#### Artikel
- Alle verfügbaren Produkte aus der DB werden aufgelistet
- Monatlich wird ausgelost, die Benutzer haben so viele Stimmen zu Verfügung, wie Produkte vorhanden sind(Bei 20 Produkten = 20 Stimmen). Dadurch können auch alle stimmen auf ein Produkt gesetzt werden, je mehr stimmen man gesetzt hat, desto höher ist die Chance es zu gewinnen
	- Wenn es von ein Produkt mehr als 1 gibt, werden die stimmen natürlich auch erhöht
- Wenn es von 1 Artikel beispielsweise 500 gibt, könnte man hierfür ein bundle machen, sodass man sie nur als 10erpack bekommt
#### Zeit
- Im Tool muss sichtbar sein wann die nächste Auslosung stattfindet, damit die Mitarbeiter es auch rechtzeitig sehen
- Die Zeit wie lange die Mitarbeiter zeit haben Abzustimmen (z.B 1 Woche)
- Wie viele Stimmen sie noch zur Verfügung haben
- Ob gerade eine Verlosung läuft, indem Mitarbeiter abstimmen können (Grün) oder ob gerade keine Auslosung stattfindet (rot)

#### Benachrichtigung und Abholung 
- Wenn die Mitarbeiter, etwas gewonnen haben, werden sie Benachrichtigt
- Bei der Abholung, wird das Produkt auf seinen Lagerplatz gebucht und von dort in Nirvana (Vorteil: Historische Verfolgung)
- Durchlassschein muss erstellt werden (Dieser wird ins WMS exportiert)
- Wenn der Mitarbeiter gerade im Urlaub ist, kann es auch später abgeholt werden, deswegen sollte man mehrere Läufe zur zeit machen können, heißt die Produkte die schon Verlost wurden sind aber noch nicht abgeholt wurden sind müssen beim nächsten Lauf aussortiert werden


| Vorteile | Nachteile |
| -------- | --------- |
|          |           |
|          |           |



# Projektplanung (Umsetzung)
1. Endgültige Planung festlegen (Vision haben), wie soll das Projekt am ende aussehen mit welchen Funktionen
2. Datenbank anlegen
	- Tabelle für Artikel erstellen (uuid ,Artikelname, ean, Anzahl, Lagerplatz)
	- Tabelle für bereits Verloste Produkte(uuid Arikelname, ean, an wen)
	- Datenbank in PHP integrieren
3. Backend Entwicklung
	- Anlegen des Controller mit den benötigten Routen
4. Algorithmus entwickeln
	- Die Idee umsetzten, wie die Produkte fair verteilt werden
5. Frontend Entwicklung
	- UI entwickeln
	- anhand des Backend




## Tipps 
- In Middleware/Service kommt die tatsächliche Anwendung rein also die Logik in diesem Fall zum Beispiele der Algorithmus
## Fragen 
1. Was für Routen benötige ich?

## References
1. 

## Quellen
1. 