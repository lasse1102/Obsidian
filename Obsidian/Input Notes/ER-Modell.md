
--- 
Erstellt: 2025-02-26    10:04 
Tags: 
Link Up: [[AP1]]
Link Down:

--- 
# ER-Modell
Das ER-Modell (Entity-Relationship-Modell) ist ein grundlegendes Konzept in der Informatik, um Datenbanken zu entwerfen und zu visualisieren. Sie bestehen aus Entitäten, Attributen und Beziehungen, die in einem Diagramm dargestellt werden, um die Struktur eines Datenbankschemas zu veranschaulichen. 
- Entitäten: Die Objekte oder Konzepte, die in einer Datenbank gespeichert werden sollen, z. B. **Kunde** oder **Produkt**.
- Attribute: Die Merkmale oder Eigenschaften der Entitäten, z. B. **Name** oder **Preis**.
- Beziehungen: Die Verbindungen zwischen den Entitäten, z. B. **kauft** oder **besitzt**.


# Beziehungen
Die Beziehung stellt in einem ER-Modell die Verbindung zwischen zwei oder mehreren Entitäten dar. Durch die Verknüpfung wird das Verhältnis zwischen den Entitäten und deren Interaktion miteinander erklärt. Sie werden mit einer Raute dargestellt.

##### Kardinalität
Die **Kardinalität** beschreibt, wie viele **Instanzen** der einen Entität mit wie vielen **Instanzen** der anderen Entität **verknüpft** werden können. Das gibst du meist als **Verhältniszeichenpaar** an:
- **1:1** (auch „Eins-zu-Eins-Beziehung“) zeigt an, dass beide Entitäten jeweils nur **einmal** im Zusammenhang mit der verknüpften Entität auftreten können. So hat z. B. jeder Mitarbeiter einen Mitarbeiterausweis, und jeder Mitarbeiterausweis gehört genau zu einem Mitarbeiter.
- **1:n** (auch „Eins-zu-Viele-Beziehung“) drückt aus, dass eine Entität wieder nur **eine Verknüpfung** zur anderen Entität vorweist. In der entgegengesetzten Beziehungsrichtung kann die andere Entität nun jedoch mit **unbestimmt vielen** Entitätsinstanzen verbunden sein. Beispielsweise wird eine Bestellung immer nur **einem Kunden** zugeordnet. Ein Kunde kann jedoch **mehrere Bestellungen** aufgeben.
- **n:m** (auch „Viele-zu-Viele-Beziehung“) bedeutet, dass **beide Entitäten unbestimmt viele** verbundene Ausprägungen haben. So kann ein Lieferant **mehrere Produkte** liefern. Gleichzeitig kann ein Produkt aber auch von **mehreren Lieferanten** bezogen werden.
#### Beispiel Aufgabe AP1
![[Pasted image 20250226100524.png]]

**Lösung:**
![[Pasted image 20250226100552.png]]
## References
1. 
