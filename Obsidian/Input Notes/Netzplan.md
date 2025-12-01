
--- 
Erstellt: 2025-01-31    13:29 
Tags: 
Link Up: 
Link Down:

--- 
# Netzplan
Bei den Prüfungsaufgaben ist meist eine Legende gegeben. Die Anordnung / Namen der einzelnen Felder muss also nicht auswendig gelernt werden. Kommt oft in Prüfungen dran.
![Netzplan](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil1/projektmanagement/netzplan/Netzplan.png) [Wikipedia Commons](https://de.wikipedia.org/wiki/Datei:NetzplanBsp.png#file)

## Legende[](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil1/projektmanagement/netzplan/#legende)

|Abkürzung|Name|
|---|---|
|FAZ|Frühester Anfangszeitpunkt|
|FEZ|Frühester Endzeitpunkt|
|GP|Gesamtpuffer|
|FP|Freier Puffer|
|SAZ|Spätester Anfangszeitpunkt|
|SEZ|Spätester Endzeitpunkt|

## Was ist der freie Puffer?
Der freie Puffer ist der Zeitraum, um den ein Vorgang maximal verschoben werden kann, ohne den frühesten Termine seiner nachfolgenden Vorgänge zu beeinflussen.

## Was ist der Gesamtpuffer?
Der Gesamtpuffer ist der Zeitraum, um den ein Vorgang maximal verschoben werden kann, ohne die spätesten Termine seiner nachfolgenden Vorgänge zu beeinflussen.

## Was ist der kritische Pfad?
Der kritische Pfad ist der Weg vom ersten bis zum letzten Vorgang eines Netzplans, auf dem die Pufferzeiten minimal sind.


# Ablauf
1. Vorgänge miteinander verknüpfen und die Dauer eintragen
2. Vorwärtsterminierung
	1. FAZ des ersten Vorgangs ist immer 0
	2. FEZ ist (FAZ + Dauer)
	3. Der FEZ bestimmt den frühsten FAZ des Nachfolgers
	4. Wenn es mehrere Nachfolger gibt wird der höchste FEZ genommen
3. Rückwärtsterminierung
	1. SEZ des letzten Vorgangs ist gleich seinem FEZ
	2. SAZ ist (SEZ - Dauer)
	3. SAZ ist gleich der SEZ des Vorgängers
	4. Wenn es mehrere Nachfolger gibt, dann nimmt man den kleinsten SAZ
4. Pufferzeiten
	1. Gesamtpuffer = SAZ - FAZ
	2. Zeigt an wie viel Verzögerung man sich bei der Bearbeitung des Vorgangs leisten kann.
5. Freier Puffer
	1. Freierpuffer = FAZ des Nachfolgers - dem eigenen FEZ
	2. Bei mehreren Nachfolgern nimmt man den kleinsten FAZ
	3. zeigt an wie viel Verzögerung man sich bei der bearbeitung leisten kann, um die bearbeitung des unmittelbaren nachfolgers nicht zu gefährden
6. Kritischer Pfad
	1. Das ist der Pfad bei denen es keinen Puffer gibt. Selbst die kleinste Verzögerung führt automatisch zu einer Verzögerung des Projektendes

## References
https://www.inloox.de/unternehmen/blog/artikel/einfuehrung-ins-pm-10-was-ist-ein-netzplan/
1. [Was ist ein Netzplan?](https://www.inloox.de/projektmanagement-glossar/netzplan/)  
[Netzplantechnik einfach erklärt + Beispiel mit kritischem Pfad!](https://www.youtube.com/watch?v=OfrfVY-eYQY)
