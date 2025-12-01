
--- 
Erstellt: 2024-12-04    08:24 
Tags: #School/LF08
Link Up: [[School]]
Link Down:

--- 
# Änderungen
- Anstatt "tabellenName_Id" nur noch **id**
- Filme -> Anstatt altersfreigabe "fsk"
- Aus Name wurde überall vorname und nachname 
- Kinosäle -> Anstatt Sitzplatz Sitzanzahl
- Besucher -> treuepunkte weg


# Vorstellung 
- 3 Fragen vorbereitet

```PHP
SELECT v.datum, v.uhrzeit, f.titel AS Film, v.sprache, k.name AS Kinosaal FROM vorführungen v 
JOIN filme f ON v.film_id = f.id 
JOIN kinosäle k ON v.saal_id = k.id;
```
- Mit der Abfrage, können wir alle Vorführungen die zurzeit existieren ausgeben
- Im Select Befehl geben wir die Daten an die wir haben wollen(datum, uhrzeit,Titel, Sprache und Name)
- Nicht alle Daten kommen aus der Vorführungstabelle, dadurch haben wir 2 Join Befehle geschrieben
- Wie Timo eben gezeigt hat, haben wir die Tabellen mit PK und FK verknüfpt, sodass wir leicht zwischen den Tabellen Abfragen über beispielsweise Join Befehle machen können
- Genau mit den ersten Join Befehl holen wir uns den Titel aus der Film Tabelle, indem wir die id miteinander vergleichen und prüfen ob sie übereinstimmen
- Und beim Zweiten Join genau das gleiche nur dass wir uns dort den Namen des Kinosaals holen
- 

Ergebnis der Abfrage zeigen

Abfrage 2:
![[Pasted image 20250107072313.png]]
- Mit der zweiten Abfrage können wir die verkauften Tickets pro Vorführung einsehen
- Im Select Befehl geben wir dann wieder wie in der Abfrage davor, die Daten an die wir dann auch schließlich ausgegeben haben wollen. In dem Fall ist das die id, der Titel vom Film und die verkauften tickets 
- Was hier nun anders ist als eben ist das wir hier ein LeftJoin verwenden mit den wir alle Daten aus der Linken Tabelle ausgeben und die übereinstimmenden Daten aus der rechten Tabelle ausgeben
- Und mit den COUNT Keyword zählen wir dann die Anzahl der Stimmen
- Auch bei 0 Verkauften Tickets wird eine Zeile erzeugt, indem dann einfach nur eine 0 drin steht, weil wir ja durch den Left Join alle Daten aus der Vorführungstabelle ausgeben
- Mit den GroupBy gruppieren wir dann noch nach der id und nach dem titel

Ergebnis der Abfrage anzeigen

Abfrage 3:
![[Pasted image 20250107072534.png]]
- Bei der letzten Abfrage, geben wir alle Besucher aus, die ein Ticket gekauft haben und die dazugehörige Ticket Daten
- Wir geben hier einmal den vor und nachnamen aus der Besucher Tabelle aus, die sitznummer und den Preis aus de Ticket Tabelle, den Titel aus der Film Tabelle, den Kinosaal namen aus der Kinosäle Tabelle und die uhrzeit aus der vorführungstabelle
- Genau und dann machen wir da wieder die jeweiligen Joins drauf, um die Daten aus den unterschiedlichen Tabellen zu holen
- 


## References
1. 
