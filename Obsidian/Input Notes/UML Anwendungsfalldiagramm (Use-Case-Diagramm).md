
--- 
Erstellt: 2025-10-08    14:07 
Tags: 
Link Up: [[AP2]]
Link Down:

--- 
#### Anwendungsfalldiagramm (Use-Case-Diagramm) 
Ein UML Use-Case Diagramm(Anwendungsfalldiagramm) dient zur Veranschaulichung der unterschiedlichen Interaktionsmöglichkeiten zwischen einem Benutzer und einem System 
Akteure:
	Die Nutzer, die mit einem System interagieren. Dabei kann es sich um Personen, Organisationen oder auch externe Systeme handeln, die mit Ihrer Anwendung bzw. Ihrem System interagieren. In jedem Fall handelt es sich um externe Objekte, die Daten produzieren oder konsumieren.
System:
	Eine bestimmte Abfolge von Aktionen und Interaktionen zwischen Akteuren und dem System. Ein System wird auch manchmal als Szenario bezeichnet.
Ziele:
	Das Endergebnis der meisten Anwendungsfälle. Ein gelungenes Diagramm sollte die Aktivitäten und Varianten darstellen, die zur Verwirklichung des Ziels führen.

<mark style="background: #FFB86CA6;">MEKRE: Zuerst die Aktuere heraussuchen bevor man die Aktivitäten aufzeichnet</mark>
#### Bestandteile
- Systemkontext
	Dies beschreibt das ganze System, also das Quadrat, worin die einzelnen Anwendungsfälle hinein geschrieben werde.
- Akteure
	Sind die Menschen/Maschinen die mit dem System interagieren. Sie werden außerhalb des Systemkontext geschrieben
- Use-Case
	Ein Anwendungsfall, den ein Akteur im System durchführen kann. Wird mit einen oval gekennzeichnet 
- Assoziation
	Anwendungsfällen werden Akteuren mit Strichen zugewiesen 

<mark style="background: #FFB86CA6;">Das sind die Basics, oft reichen die schon für die AP2 Prüfungen, da oft nicht mehr verlangt wird.</mark>

---

Vererbung von Akteuren: Akteure können von anderen Akteuren "erben" und haben damit Zugriff auf deren Anwendungsfälle. Häufig ist dies eine "Ist-Ein-Beziehung". Zusätzlich können sie dann ggfs. weitere Anwendungsfälle durchführen.

Vererbung von Anwendungsfälle: Anwendungsfälle können andere Anwendungsfälle spezialisieren.
![[Pasted image 20251104080456.png]]

---
#### Beziehungen 
- Include-Beziehung:
	Anwendungsfälle können andere Anwendungsfälle inkludieren, was bedeutet, dass beim Durchführen eines Anwendungsfalls immer auch alle inkludierten mit durchgeführt werden müssen
![[Pasted image 20251104080831.png]]
<mark style="background: #FFB86CA6;">MEKRE: Includes erkennt man gut daran das es das tuen MUSS</mark>

- Extends-Beziehung:
	- Anwendungsfälle können von anderen Anwendungsfällen **OPTIONAL** erweitern, wenn bestimmte Bedingungen erfüllt sind.
	- Extension Point: Ein Ergebnis, bei dem geprüft wird, ob der Anwendungsfall erweitert werden soll
	- Notiz: In einer Notiz wird spezifiziert, unter welcher Bedingung ein Anwendungsfall an welchen Extension Point erweitert wird
![[Pasted image 20251104081728.png]]
Der Bankkunde kann Bargeld abheben und einzahlen.
- Wenn nun will kann er bestimmte Banknoten auswählen oder beim einzahlen die Quittung ausdrucken lasse
- Dies ist nur Optional

<mark style="background: #FFB86CA6;">MEKRE: extends erkennt man gut, wenn man es nicht machen muss sondern machen KANN</mark>




















**Aufgabe:**
![[Pasted image 20250226095554.png]]

### Lösung
![[Pasted image 20250226095623.png]]


## References
1. 
