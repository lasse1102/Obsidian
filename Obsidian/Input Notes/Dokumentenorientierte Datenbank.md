
--- 
Erstellt: 2025-11-04    12:03 
Tags: 
Link Up: [[AP2]]
Link Down:

--- 
Dokumentenorientierte Datenbank sind eine Unterart der NoSQL-Datenbanken und speichern Daten in dokumentähnlichen Strukturen. Dokumentenorientierte Datenbanken sind aufgrund ihrer Flexibilität und Skalierbarkeit eine beliebte Wahl für Entwickler.

# Entwicklung von Datenbanken
- In den letzten Jahren wurden Dokumentenorientierte Datenbanken, die auch als NoSQL Datenbanken bezeichnet werden immer beliebter
- Sie zeichnen sich aus durch ihre starre Struktur, welches dem Gegenteil von Relationalen Datenbanken gilt
- Sie bieten ein hohes Maß an Skalierbarkeit und Flexibilität in Bezug auf die Datenstruktur. Dies machen NoSQL-Datenbanken nützlich für die Bewältigung großer Datenmengen und für schnelle, agile Entwicklung

## Was ist eine Dokumentdatenbank?
Dokumentenorientierte Datenbanken speichern Daten als Dokumente. Ein solches Dokument kann man sich als eigenständigen Datensatz vorstellen, der alles enthält, was benötigt wird, um seine Bedeutung zu verstehen – ähnlich wie Dokumente, die in der realen Welt verwendet werden.
![[Pasted image 20251104122953.png]]
Beachten Sie, dass das Dokument als JSON-Objekt geschrieben ist.
- Sie können auch in XML oder YAML geschrieben werden (JSON wird am häufigsten genutzt)

Alle Daten in JSON-Dokumenten werden als Feld-Wert-Paare dargestellt, die die Form Feld: Wert haben. Im vorherigen Beispiel zeigt die erste Zeile ein Feld _id mit dem Wert "annameier". Das Beispiel enthält auch Felder für den Vornamen und Nachnamen der Mitarbeiterin, ihre E-Mail-Adresse sowie die Abteilung, in der sie arbeitet.

![[Pasted image 20251104123222.png]]
In Dokumentdatenbanken sind Dokumente nicht nur selbstbeschreibend, sondern ihr Schema ist auch **dynamisch**. Das bedeutet, dass Sie es nicht vordefinieren müssen, bevor Sie Daten speichern. Felder können zwischen verschiedenen Dokumenten in derselben Datenbank variieren, und Sie können die Struktur des Dokuments nach Belieben ändern, Felder hinzufügen oder entfernen. Dokumente können auch verschachtelt sein, d.h., ein Feld in einem Dokument kann einen Wert in Form eines anderen Dokuments haben, was es ermöglicht, komplexe Daten in einem einzigen Dokument zu speichern.

# Vergleich zu relationalen Datenbanken
In einer relationalen Datenbank könnten Sie diese beiden Beispielkontaktkarten nicht in derselben Tabelle speichern, da sie sich in ihrer Struktur unterscheiden. Sie müssten das Datenbankschema anpassen, um sowohl das Speichern von mehreren Abteilungen als auch von zweiten Vornamen zu ermöglichen, und Sie müssten einen zweiten Vornamen für Anna hinzufügen oder die Spalte für diese Zeile mit einem NULL-Wert füllen. Dies ist bei Dokumentdatenbanken nicht der Fall, die Ihnen die Freiheit bieten, verschiedene Dokumente mit unterschiedlichen Schemata ohne Änderungen an der Datenbank selbst zu speichern.

---

## Zusammenfassung
- **Definition:** Dokumentenorientierte Datenbanken speichern Daten in sogenannten **Dokumenten** (meist im **JSON**) anstatt in festen Tabellen. Sie gehören zu den **NoSQL-Datenbanken**.
- **Struktur:** Jedes Dokument kann eine **unterschiedliche Struktur** (Schema) haben. Ein Dokument kann Attribute, Arrays und sogar andere verschachtelte Dokumente enthalten.
**Vorteile:**
- **Flexibles Schema:** Ideal, wenn sich die Datenstruktur häufig ändert oder die Daten von Natur aus unstrukturiert oder semi-strukturiert sind. Dies vereinfacht die Anwendungsentwicklung.
- **Einfache Modellierung von Hierarchien:** Verschachtelte oder hierarchische Daten (z.B. Bestellungen mit vielen Positionen, Blogs mit Kommentaren) lassen sich sehr natürlich in einem einzigen Dokument abbilden.
- **Leistung (Lese-Performance):** Das Lesen des gesamten Dokuments erfordert nur einen Datenbankzugriff, da alle zusammengehörigen Daten beieinander liegen ("Colocation").

# Aufgaben
![[Pasted image 20251113182701.png]]





![[Pasted image 20251113182732.png]]
## References
1. 
