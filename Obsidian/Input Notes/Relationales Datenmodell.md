
--- 
Erstellt: 2025-10-26    23:31 
Tags: 
Link Up: [[AP2]]
Link Down:

--- 
# Normalisierung
Ziel der Normalisierung ist es, **Redundanz und [[Anomalien]] zu vermeiden**, um die Datenkonsistenz und Datenintegrität zu gewährleisten.
Folgende Normalformen sollte man beherrschen:
1. 1NF: Alle Attribute müssen atomar sein (unteilbar) und es dürfen keine wiederholten Gruppen geben
	- wiederholte Gruppen heißt, dass es in einer Spalte mehrere Werte gibt
	- nicht atomar bedeutet das mehrere Operationen zu einer einzigen logischen Einheit zusammengefasst werden (komplette Adresse in einer Spalte anstatt getrennt in Straße, PLZ, Ort). 
	- **Um die erste Normalform zu erreichen müssen wir alle Werte atomar machen und wiederholte Gruppen in Spalten vermeiden**
2. 2 NF: Die 1NF ist erfüllt und **alle nicht-primären Attribute** sind voll funktional abhängig vom gesamten Primärschlüssel
	- anstatt nun mehrere Schlüssel in einer Tabelle zu haben, haben wir nur noch ein Schlüssel und alle anderen Attribute (nicht-primären Attribute) sind nun von diesem Primärschlüssel abhängig
	- Wir teilen die Tabelle somit meist in mehrere Tabellen auf und haben dann in jeder Tabelle einen Primärschlüssel, somit hat eine Tabelle dann nur noch eine Aufgabe und nicht mehrere (Kunde, Bestellung, Position, Artikel)
	- Bei einer m zu n Beziehungen bildet man zusätzlich noch mit einer Zuordnungstabelle ab
3. 3 NF: Die 2 NF ist erfüllt und es gibt keine transitiven Abhängigkeiten (nicht primäre Attribute hängen nicht von anderen nicht primären Attributen ab)
	- Keine transitiven Abhängigkeiten: Diese Regel ist entscheidend. In einer 3NF-Tabelle darf eine Nicht-Primärschlüsselspalte nur vom Primärschlüssel abhängen und nicht indirekt über eine andere Nicht-Schlüsselspalte.
	- Um dies zu erreichen, teilen wir das wieder in separate Tabellen auf wie in NF2, nur das wir hier die transitiven Abhängigkeiten entfernen 


# Wichtig für die Prüfung
- Nachdem wir alle Tabellen heraus gefunden haben, sollten wir schauen ob es irgendwo eine n zu m Beziehung gibt, diese müssten wir dann in einer Zuordnungstabelle zuweisen

# Schritte zum Normalisierung
Ausgangssituation:
![[Pasted image 20251112113353.png]]


Hier ist eine Schritt für Schritt Anleitung, wie man sollte um eine nicht normalisierte Tabelle zu einer normalisierten Tabelle umzuwandeln.
1. Im ersten Schritt sollte man immer den vollständigen, kombinierten Primärschlüssel identifizieren.
	- Die Frage, die sie sich stellen müssen: "Hängt dieses Attribute vom gesamten Schlüssel ab oder nur von einen der mehreren Primärschlüssel"
2.  Wenden sie diesen Schritt auf jede Tabelle mit einem zusammengesetzten Primärschlüssel an: 
	1. **Was sie Suchen**: die vom gesamten Primärschlüssel abhängen. Diese bilden die Beziehungstabelle (n:m Tabelle). 
	2. **Regel**: Nur diese Attribute dürfen im neuen Schlüssel enthalten sein
	3. **Vorgehen**: Nehmen Sie den gesamten Primärschlüssel und alle Attribute, die von ihm voll funktional abhängig sind, in eine neue Tabelle auf 
	4. **Beispiel:** Die Prj-Std hängen von (PersNr,Projektnr) ab.
		→Tabelle 1:(PersNr​,Projektnr​,Prj-Std)
3. Partielle funktionale Abhängigkeiten identifizieren
	1. **Was sie suchen**: Attribute, die nur vom ersten Teil des Primärschlüssels abhängen. 
	2. **Vorgehen**: Entfernen sie diese Attribute aus der ursprünglichen Tabelle und erstellen sie eine neue Tabelle mit diesem Teil des Primäschlüssels als neuen, einfachen Primärschlüssel
	3. **Beispiel:** Name, Abt.Nr., Abteilung hängen nur von PersNr ab.
		→Tabelle 2 (Mitarbeiter):(PersNr​,Name,Abt.Nr.,Abteilung)
4. Partielle funktionale Abhängigkeiten identifizieren 
	1. **Was Sie suchen**: Attirbute, die nur vom zweiten Teil des Primärschlüssels abhängen.
	2. **Vorgehen**: Entefenen Sie diese Attribute aus der ursprünglichen Tabelle und erstellen Sie eine neue Tabelle mit diesem Teil des Primärschlüssels als neuen, einfachen Primärschlüssel.
	3. **Beispiel:** [[Projekt]] hängt nur von Projektnr ab.
		→Tabelle 3 :(Projektnr​,Projekt)
5. Dieser Schritt wird auf jeder der 2NF-Tabellen (Tabelle 1, 2 und 3) angewendet, um transitive Abhängigkeiten zu beseitigen.
	1. **Was sie suchen:** Wir suchen nicht primäre Attribute, die von nicht primären Attributen abhängig sind.
		- _Beispiel:_ In Tabelle 2 (Mitarbeiter) ist PersNr der Primärschlüssel. Es liegt die Abhängigkeit PersNr→Abt.Nr.→Abteilung vor.
	2. **Vorgehen:** 
		1. Identifizieren sie die transitive Abhängigkeit
		2. Spalten sie diese in eine neue Tabellle ab. Das Attribute A wird der neue Primärschlüssel dieser Tabelle
		3. Entfernen sie das Attribut B aus der ursprünglichen Tabelle. Attribute A bleibt als Fremdschlüssel zurück

		→Tabelle 4 (Abteilungen):(Abt.Nr.​,Abteilung) -> neue Tabelle
		→Tabelle 2 (Mitarbeiter_3NF):(PersNr​,Name,Abt.Nr.) -> alte Tabelle 

**Endergebnis sollte so aussehen in der 3 Normalform**
![[Pasted image 20251112120719.png]]

---

# Aufgaben
![[Pasted image 20251028120831.png]]








![[Pasted image 20251028120850.png]]



![[Pasted image 20251029113920.png]]



Lösung:
![[Pasted image 20251029113948.png]]




## References
1. [[08b - Übungen Datenbanknormalisierungen]]
2. [[08b - Übungen Datenbanknormalisierungen (Lösungen)]]
