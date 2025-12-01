

--- 
Erstellt: 2025-10-14    07:06 
Tags: 
Link Up: [[AP2]]
Link Down:

--- 
Ziel: Visualisierung einer Interaktion mittels Nachrichtenaustausch zwischen Objekten (meist zur Darstellung von Methodenaufrufen)
## Bestandteile

- **Objekte:** Die an der Interaktionen beteiligten Objekte haben eigene Lebenslinien die von oben nach unten gelesen werden.
- **Aufrufe:** Objekte können sich Nachrichten schicken (meist Methodenaufrufe), die auch einen Rückgabewert haben können. Synchrone Nachrichten werden mit einer gefüllten Pfeilspitze, asynchrone Nachrichten mit einer offenen Pfeilspitze gezeichnet.
![[Pasted image 20251014073038.png]]
Rückgabeoption (neuerKilometerstand) wird mit einer gestrichelten Linie gezeichnet.

- **Aktivierung von Objekten:** Das aktuell aktivierte Objekt steuert den Kontrollfluss. Objekte können sich auf auch selbst aktivieren, indem sie eigene Methoden aufrufen
- **Erzeugung von Objekten:** Ein Objekt kann auch erst während der Interaktion erzeugt und zerstört werden (siehe Dateipruefer, welches erst während der laufenden Sequenz erstellt wird. Dateiverarbeiter und Dateileser existieren von Anfang an)
![[Pasted image 20251014074105.png]]

Erläuterung:
1. Der Aufruf der Methode oeffneDatei(pfad) im **Dateileser** vom **Dateiverarbeiter** aus wird auf den Stack gelegt und beginnt die Ausführung.
2. Die Methode oeffneDatei im **Dateileser** liegt jetzt oben auf dem Stack.
3. Innerhalb dieser Methode wird ein neues **Objekt** der **Klasse Dateipruefer** erstellt (new). Anschließend wird die Methode istVorhanden(pfad) dieses neuen Dateipruefer-**Objekts** aufgerufen und somit oben auf den Stack gelegt. Wir befinden uns jetzt in der istVorhanden-Methode.
4. Wenn die istVorhanden-Methode fertig ist, wird sie vom Stack genommen. Im gezeigten Diagramm liefert sie vorhanden zurück, und ihre Lebenslinie endet dann (symbolisiert durch das Kreuz ×).
5. Die Ausführung kehrt zum Dateileser zurück (der jetzt wieder oben auf dem Stack liegt) und führt pruefeEncoding() aus. Dieser Aufruf landet wieder oben auf dem Stack.
6. Nachdem pruefeEncoding() beendet ist, wird es vom Stack genommen, und die Ausführung der oeffneDatei-Methode im Dateileser endet.
7. oeffneDatei(pfad) liefert den dateihandle zurück an den Dateiverarbeiter. Danach wird die gesamte oeffneDatei(pfad)-Methode vom Stack genommen, und die Ausführung geht im Dateiverarbeiter weiter.
**Wenn wir eine Synchrone Methode wie pruefeEncoding aufrufen, müssen wir diese mit einen gestrichenen Pfeil beenden auch wenn es kein Rückgabewert hat (Pfeil geht von oberen Rechteck zum davorliegenden Rechteck)**

Kurz gesagt: Es wird immer das gerade ausgeführt, welches ganz oben auf dem Stack liegt. Und wenn diese Methode fertig ist dann wird sie von den Stack sozusagen runtergeschmissen und wir befinden uns in der Methode davor


--- 

### Fragmente

**Fragmente:** Mittels Fragmente können Verzweigungen, Wiederholungen und andere steuernde Abläufe modelliert werden
- alt -> ähnlich wie if-else/ switch-case
- opt -> ähnlich wie eine if Struktur nur ohne else
- loop -> ähnlich wie eine for schleife oder einer while schleife
![[Pasted image 20251014112343.png]]
**Wichtig:** Auf dem Bild müsste die Methode von Dateileser bis zum Ende der alt Anweisung gehen, also auch bis über den "else" Block.



**Wichtig: Was oft falsch gemacht wird sind die korrekten Pfeilspitzen (synchron vs. asynchron)**







## References
1. https://www.youtube.com/watch?v=CHkVwoxxg58
