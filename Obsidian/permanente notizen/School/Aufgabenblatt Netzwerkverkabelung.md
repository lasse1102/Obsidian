
--- 
Erstellt: 2024-04-22    10:38 
Tags: #School/LF02/Verkabelung
Link Up: [[Verkabelung]]
Link Down:

--- 
# Welche Daten-Kabelarten gibt es & wofür werden sie verwendet

# Definiere die Bedeutung folgende Abkürzungen:
a) U/UTP Cat.5
- Steht für Unshielded Twisted Pair
- keine Abschirmung sondern besteht nur aus verdrillten Adernpaaren besteht. 
- Hat eine Datenübertragungsgeschwindigkeit von bis zu 100 Mbit/s
b) F/UTP Cat.5 / Cat.5e
- Steht für Foiled Unshielded Twisted Pair 
- Gesamtabschirmung aus Aluminiumfolie, aber die Adernpaare selbst sind nicht abgeschirmt. Cat.5e (Category 5 Enhanced) ist eine verbesserte Version von Cat.5, 
- Hat eine Datenübertragungsgeschwindigkeiten von bis zu 1000 Mbit/s (1 Gbit/s).
c) U/FTP Cat.6
- Steht für Unshielded Foiled Twisted Pair
- die Adernpaare des Kabels sind einzelnt mit Folie abgeschirmt, aber es gibt keine Gesamtabschirmung. 
- Datenübertragungsgeschwindigkeit von bis zu 10 Gbit/s
d) S/FTP Cat.7A
- Steht für Screened Foiled Twisted Pair
- due Adernpaare des Kabels sind einzelnt mit Folie abgeschirmt und es gibt zusätzlich eine Gesamtabschirmung 
- Datenübertragungsgeschwindigkeit von bis zu 40 Gbit/s
e) S/FTP Cat 8
- Steht für Screened Foiled Twisted Pair
- Ist die neueste und leistungsfähigste Datenübertragungsgeschwindigkeit von bis zu 40 Gbit/s

# Vergleichstabelle der Kabeltypen
![[Pasted image 20240422111536.png]]

# Wie lang kann ein Netzwerkkabel maximal sein, bevor die Signalqualität beeinträchtigt wird?

| Cat 5 und Cat 5.e | Bis zu 100 Meter                                                                                                                  |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Cat 6             | Bis zu 250 Meter (empfohlen nicht mehr als 100 Meter, da die optimale Leistung sonst schwächer wird)                              |
| Cat 7             | Bis zu 100 Meter für 10 Gbit/s und bis zu 15 Meter für 40 Gbit/s                                                                  |
| Cat 8             | Wird hauptsächlich in Serverräumen oder Rechenzentren verwendet. Also ist die maximale Entfernung nicht alt so hoch (ca 30 Meter) |

# Welche Farbcodierung wird für die Adern eines Netzwerkkabels verwendet und warum ist sie wichtig?
Der Hauptgrund, dass Netzwerkabel Farben haben, ist die Vermeidung von Verwechslungen. Die UTP Kabel bestehen aus 8 Drähten, wobei jede Ader eine andere Farbe hat. Allerdings sind die Farben der Drähte in den UTP Kabeln immer gleich, um den Standard-Farbcode UTP beizubehalten.
![[Pasted image 20240422112303.png]]

Es gibt 2 gängige Standarts für die Farbcodierung von Netzwerkkabeln **T568A** und **T568B**. Beide Standarts haben ihre Berechtigung und Anwendungsfelder, sie unterscheiden sich in der genauen Reihenfolge der Farben der Adern

**T568A** Reihenfolge:
- weiß-grün  
- grün  
- weiß-orange  
- blau  
- weiß-blau  
- orange  
- weiß-braun  
- braun

**T568B**  Reihenfolge:
- weiß / orange
- orange
- weiß / grün
- blau
- weiß / blau
- grün
- weiß / braun
- braun

# Wie kann ein defektes Netzwerkkabel identifizieren und reparieren?

Identifizierung:
- Visuelle Inspektion: Überprüfen ob das Kabel auf offentsichtliche physische Schäden wie Schnitte, Knicke hinweisen
- Verwendung von einem Netzwerkkabeltester, falls sowas vorhanden ist

Reparatur eines defekten Netzwerkkabels:
- Abschneiden des beschädigten Endes: Verwenden eines Kabelschneidewerkzeug, um das Ende abzuschneiden
- 2cm der äußeren Hülle mit ein abisolierwerkzeug abziehen
- Adern in richtiger Reihenfolge ordnen
- Adern zurecht schneiden in gleicher länge
- Stecker befestigen
- Den Stecker Crimpen

# Begründe, ob es sinnvoll ist, ein Netzwerkkabel >90 Grad zu biegen?
Es ist generell nicht empfehlenswert, ein Netzwerkkabel um mehr als 90° zu biegen. Der Grund dafür ist, dass eine scharfe Biegung die physische Struktur der Kabeladern beeinträchtigen und zu einer Verschlechterung der Signalqualität führen kann. Dies kann zu langsameren Datenübertragungsraten oder sogar zu Verbindungsabbrüchen führen

# Welche Vorteile bietet die Verwendung von abgeschirmten Netzwerkkabeln gegenüber ungeschirmten Kabeln?

Abgeschirmte Netzwerkkabel: 
- Schutz vor elektromagnetischen Interferenzen
	Die haben eine zusätzliche Abschirmung, die die Datenübertragung schützt, indem Störsignale über eine Erdung abgeleitet werden
- Höhere Datenübertragungsqualität

Ungeschirmte Netzwerkkabel
- Flexibilität und einfache Installation
	Sie sind Flexibler und einfacher zu installieren, was Planungs- und Arbeitskosten sparen kann
- Günstigere Anschaffung
	Ungeschirmte Kabel sind in der Regel günstiger in der Anschaffung


# Welche Rolle spielt die Übertragungsgeschwindigkeit bei der Auswahl eines geeigneten Netzwerkkabels?

- Leistungsfähigkeit
	Die Übertragungsgeschwindigkeit bestimmt, wie schnell Daten von einem Gerät zum anderen Gerät übertragen werden können.
- Zukunftssicherheit
- Qualität der Datenübertragung
	Die Übertragungsgeschwindigkeit  eines Kabels kann auch die Qualität der Datenübertragung beeinflussen
- Kosten
	Kabel mit höhere Übertragungsgeschwindigkeit sind in der Regel teurer



## References
1. 

## Quellen
1. 