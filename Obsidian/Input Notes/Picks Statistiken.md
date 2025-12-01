
--- 
Erstellt: 2025-09-02    06:47 
Tags: 
Link Up: 
Link Down:

--- 
### Übersicht Projekt 
1. Filter Funktion
	1. Standartmäßig sollen die letzten 30 Tage angezeigt werden
2. Aufträge (Ordnern, Orderlines, anzahl Positionen) in einzelnen Blöcken anzeigen
	1. Für jeden Mandant
	2. Es sollen nur die Mandanten angezeigt werden bei denen auch was steht



- Wir haben die verschiedenen Daten wie GepickteStücke, Anzahl Orders und Anzahl Positionen in getrennten Blöcken getrennt nach Datum

Was noch fehlt:
- Filtern nach Mandant
- Lagerplatztyp und Lagergruppe -> Jasmin fragen wo ich die Daten herbekomme 
- (Gesamte Anzahl an Artikeln) -> Gehört eigentlich nicht zur Statistik, kann weg gelassen werden
- Durchschnitt anzahl der artikel
- Aufklappbare Boxen für die Items (ist übersichtlicher bei vielen Items und vielen Mandanten)
- Ranking Zeilen (Bug fixen: Es sollen immer die obersten Elemente angezeigt werden je nachdem wie viele Zeilen gezeigt werden sollen) und auch in Kombination mit Ranking Ordern funktionieren

Nach Standort Filtern (Beide an bzw einen auschalten)
mobile twig template (retouren prozess, tableNoMore)



**Anforderungen von Ronny**
![[Pasted image 20251107104032.png]]

Was ist noch umsetzbar bis zur Deadline?
- [ ] Filtern nach Standort (Howe, Boizenburg oder beide)
- [ ] Wenn ich nur bestimmte Mandanten auswähle dann sollen auch nur von den die Artikel angezeigt werden
- [ ] Es soll eine maximale Anzahl an Zeilen geben die dargestellt werden, sonst geht die Liste nachher zu weit, wenn dort pro Tabelle 30 Datum's Zeilen sind
- [ ] Button korrekt importieren
	- [ ] Neben Clients ein Button mit dem man alle anwählen kann (Standardmäßig aktiviert)
	- [ ] Aktive und nicht aktive Mandanten sollen ein anderen Hintergrund haben
- [ ] Responsives Design (Nur die Cards müssen untereinander angezeigt werden)

- In der Twig müssen noch gewisse Namen mit yml übersetzt werden
- Es gibt in der Twig noch einige Css klassen die noch zu bootstrap Klassen geändert werden müssen

# Dokumentation
1. [x] 1.1 und 1.2 -> der erste Satz von 1.2 gefällt mir nicht so weil er genau das wiederholt was vorher gesagt wurden ist ✅ 2025-11-28
2. [x] Nutzwertanalyse ✅ 2025-11-27
3. [x] 4.3 Beispiel entfernen ✅ 2025-11-27
4. [x] ER Modell ✅ 2025-11-27
	1. [x] Beispiel entfernen aus 4.4 ✅ 2025-11-27
	2. [x] Schauen ob sich das lohnt ein ER Diagramm zu zeichnen ✅ 2025-11-27
5. [x] 5.3 Screenshots hinzufügen ✅ 2025-11-28
6. [x] Einführungsphase entfernen ✅ 2025-11-27
7. [x] Dokumentation ✅ 2025-11-28
	1. [x] neben der Projektdokumentation noch eine Benutzerdoku schreiben ✅ 2025-11-28
8. [x] Soll Ist vergleich Tabelle noch einmal anschauen ✅ 2025-11-27
9. [x] Lessons Learned ✅ 2025-11-27
10. [x] Literaturverzeichnis ✅ 2025-11-28

Abkürzungen ergänzen, falls noch welche nicht eingetragen sind


Diagramme / Ausschnitte
1. [x] A.1 Detaillierte Zeitplanung ✅ 2025-11-28
2. [x] A.4 Evtl das Use Case Diagramm noch einmal überarbeiten ✅ 2025-11-28
3. [x] Aktivitätsdiagramm erstellen ✅ 2025-11-28
4. [x] Code Screenshots ✅ 2025-11-28
5. [x] UI Screenshots -> In Punkt 5.3 erwähnen ✅ 2025-11-28
6. [x] Benutzerdoku Auszug ✅ 2025-11-28


# Todos Freitag
- [x] Code Screenshots in der Doku Abschnitt 5.2 einbinden ✅ 2025-11-28
	- [x] Code Screenshots vor dem UI Screenshots ✅ 2025-11-28
- [x] Zeiten anpassen detaillierter Zeitplan anhand des Projektantrags ✅ 2025-11-28
- [x] Abweichungen vom Projektantrag ergänzen oder löschen ✅ 2025-11-28
	- [x] Test schreiben wurde nicht gemacht, welches im Projektantrag erwähnt wurde ✅ 2025-11-28
	- [x] Deployment sollte ich nochmal erwähnen im Text ✅ 2025-11-28
	- [x] Planungsphase wurde im Projektantrag nicht erwähnt ✅ 2025-11-28
- [x] Abkürzungen erstellen ✅ 2025-11-28
- [x] Rechtschreibung prüfen ✅ 2025-11-28
- [x] Literaturverzeichnisse hinzufügen ✅ 2025-11-28
- [x] Klammern um die verlinkungen auf vorherige Kapitel ✅ 2025-11-28
- [x] A Anhang wegbekommen ✅ 2025-11-28















## References
1. 
