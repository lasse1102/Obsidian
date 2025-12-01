-
--- 
Erstellt: 2025-10-08    14:07 
Tags: 
Link Up: [[AP2]]
Link Down:

--- 
# Aktivitätsdiagramm
<mark style="background: #FFB86CA6;">Definition: Ein Aktivitätsdiagramm ist ein Verhaltensdiagramm, das den Fluss eines Systems oder Prozesses grafisch darstellt.</mark>
### Bestandteile
- **Beginn und Ende des Diagramms:** Zeigen den Einstieg in den Ablauf und den Ausstieg aus diesem
- **Aktivitäten:** Einzelne durchzuführende Schritte des Gesamtablaufs
- **Partitionen:** Mehrere Aktivitäten können mit Partitionen gruppiert werden (Morgenroutine, Arbeitstag)

![[Pasted image 20251015091133.png]]

--- 

**Bedingung:** Abhängig von einer Prüfung können unterschiedliche Pfade durch den Ablauf verfolgt werden.

![[Pasted image 20251015091902.png]]
- Bedingung steht in so eckigen Kästchen und nicht abgerundeten Quadraten
- Um die einzelnen Antwortpfade wieder zu einem zusammenzuführen, macht man als Zwischenschritt eine kleine raute von dem man dann weiter zum nächsten Punkt gehen kann
- Die Raute ist wie ein logisches Oder. Es benötigt nur ein Input um weiter zu gehen. In diesen Beispiel entweder Frühstücken oder Zeitung Lesen muss beendet sein.
---

**Wiederholungen:** Abhängig von einer Prüfung können Aktivitäten oder ganze Programme wiederholt durchgeführt werden.

![[Pasted image 20251016112653.png]]
- Es ist von der Syntax her genau das gleiche wie eine Bedingung, nur das bei der Wiederholung ganz logisch man wieder zurück zu der Anforderung springt. Wenn die dann irgendwann auf false ist dann gelangt man weiter

---
**Parallele Verarbeitung:** Aktivitäten lassen sich parallel ausführen und zusammenführen. Die nächsten Aktivitäten werden erste durchgeführt, wenn alle Aktivitäten abgeschlossen sind
![[Pasted image 20251016113116.png]]
- Wir starten hier mit dem installieren eines Webservers. Anschließend werden die 3 Aktivitäten gestartet (Implementiere Backend, Lerne JavaScript, Sichere Webserver ab)
- Erst wenn alle 3 Aktivitäten abgeschlossen sind wird "Aktualisiere DNS-Eintrag" angefangen 
- Sozusagen ein logisches und, es kann erste weitergemacht werden wenn alle Aktivitäten abgeschlossen sind
---
**Schwimmbahnen:** Wenn das Zusammenspiel verschiedener Systeme oder Akteure visualisiert werden soll, können Schwimmbahnen verwendet werden
![[Pasted image 20251016114031.png]]

# Übungsaufgaben
![[Pasted image 20251016171943.png]]






Lösung:
![[Pasted image 20251016172024.png]]




![[Pasted image 20251103091032.png]]







![[Pasted image 20251103091051.png]]


## References
1. 
