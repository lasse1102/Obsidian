
--- 
Erstellt: 2025-05-20    11:31 
Tags: 
Link Up: 
Link Down:

--- 
### Was ist ein SLA? (Service Level Agreement)
- **Definition:** Ein Service Level Agreement (SLA) ist eine **schriftliche Vereinbarung zwischen einem Service-Dienstleister (Servicegeber) und einem Kunden (Servicenehmer)**, die die **Qualität, Verfügbarkeit und andere spezifische Merkmale** der zu erbringenden Dienstleistung oder des Produkts detailliert festlegt. Es ist quasi ein Vertrag über die Servicequalität.
- **Zweck:** Das Hauptziel eines SLA ist es, **klare Erwartungen** zu definieren, **Messbarkeit** zu schaffen und die **Transparenz** der erbrachten Leistungen zu erhöhen. Es dient dazu, Missverständnisse zu vermeiden und eine gemeinsame Basis für die Zusammenarbeit zu schaffen.

- **Beispiele außerhalb der IT:**
    - Ein Reinigungsunternehmen vereinbart mit einem Bürogebäude, dass die Büros täglich von 18:00 bis 20:00 Uhr gereinigt werden, der Müll geleert und die Oberflächen desinfiziert werden, mit einer Garantie von 95% Zufriedenheit der Mitarbeiter, gemessen durch monatliche Umfragen.
    - Ein Logistikunternehmen garantiert die Lieferung von Paketen innerhalb von 24 Stunden in einem bestimmten Liefergebiet, mit einer Erfolgsquote von 98%.
- **In der IT:**
    - Ein Cloud-Anbieter garantiert eine Verfügbarkeit seiner Server von 99,9% pro Monat und eine maximale Reaktionszeit auf kritische Störungen von 1 Stunde.
### Ziele eines SLA
SLAs haben mehrere wichtige Ziele für beide Seiten:

1. **Klarheit und Erwartungsmanagement:**
    - Sorgt dafür, dass sowohl der Dienstleister als auch der Kunde genau verstehen, welche Leistungen in welcher Qualität erwartet werden können.
    - Vermeidet Missverständnisse und unterschiedliche Interpretationen der Dienstleistung.
2. **Messbarkeit und Transparenz:**
    - Definiert messbare Kennzahlen (Service Levels, KPIs), anhand derer die Einhaltung der vereinbarten Qualität überprüft werden kann.
    - Macht die erbrachte Leistung objektiv beurteilbar und schafft Transparenz über die Servicequalität.
3. **Qualitätssicherung und -verbesserung:**
    - Dient als Basis für die Überwachung der Servicequalität.
    - Ermöglicht die Identifizierung von Schwachstellen und die Einleitung von Maßnahmen zur kontinuierlichen Verbesserung der Dienstleistung.
4. **Verantwortlichkeiten festlegen:**
    - Legt klar fest, wer für welche Aspekte der Dienstleistung verantwortlich ist (Kunde und Dienstleister).
    - Definiert Eskalationspfade für den Fall, dass die vereinbarten Service Levels nicht erreicht werden.
5. **Rechtliche Absicherung und Konfliktlösung:**
    - Bildet eine rechtliche Grundlage für die Geschäftsbeziehung.
    - Bietet einen Rahmen für die Beilegung von Streitigkeiten, da die vereinbarten Parameter schriftlich festgehalten sind. Oft sind darin auch Pönalen (Strafzahlungen) oder Boni bei Nichteinhaltung bzw. Übererfüllung vereinbart.
6. **Kostenkontrolle:**
    - Hilft beiden Parteien, die Kosten für den Service zu kalkulieren und zu steuern, da die Leistungsumfänge und Qualitätsstandards klar definiert sind.

---

### Bestandteile eines SLA (vereinfacht)

Ein typisches SLA enthält (oft in mehr oder weniger detaillierter Form) folgende Elemente:

1. **Parteien der Vereinbarung:** Wer sind der Servicegeber und der Servicenehmer?
2. **Gegenstand der Vereinbarung/Servicebeschreibung:**
    - Welche Dienstleistungen werden erbracht? (z.B. IT-Support, Hosting, Netzwerkbetreuung, Anwendungsentwicklung).
    - Was gehört dazu, was nicht? (Scope).
3. **Service Levels/Messgrößen (Key Performance Indicators - KPIs):**
    - **Verfügbarkeit:** Prozentsatz der Zeit, in der ein Dienst oder System verfügbar ist (z.B. 99,5% Verfügbarkeit des Servers).
    - **Performance/Antwortzeiten:** Wie schnell reagiert ein System oder eine Anwendung (z.B. Ladezeit einer Webseite unter 2 Sekunden, Antwortzeit einer Datenbankabfrage unter 500 ms).
    - **Reaktionszeit:** Wie schnell beginnt der Dienstleister, auf eine Anfrage oder Störung zu reagieren (z.B. 15 Minuten bei kritischen Störungen, 4 Stunden bei normalen Anfragen). (Hier siehst du den direkten Bezug zum vorherigen Merkblatt.)
    - **Lösungszeit:** Wie schnell wird ein Problem voraussichtlich behoben (z.B. Behebung einer kritischen Störung innerhalb von 2 Stunden).
    - **Fehlerrate:** Anzahl der Fehler pro Zeiteinheit oder Transaktion.
    - **Sicherheitsstandards:** Definition von Sicherheitsmaßnahmen und -protokollen.
    - **Kapazität:** Gewährleistete Bandbreite, Speicherplatz, Anzahl der möglichen Nutzer.
4. **Servicezeiten:**
    - Wann ist der Service verfügbar? (z.B. 24/7, Mo-Fr 8-17 Uhr).
    - Wann ist der Support erreichbar?
5. **Rollen und Verantwortlichkeiten:**
    - Wer ist für was zuständig? (z.B. Der Kunde ist für die Bereitstellung von Zugangsdaten verantwortlich, der Dienstleister für die Wartung der Server).
6. **Eskalationsverfahren:**
    - Was passiert, wenn ein Service Level nicht eingehalten wird?
    - Wer sind die Ansprechpartner auf jeder Ebene bei Problemen?
7. **Berichtswesen (Reporting):**
    - Wie oft und in welcher Form wird über die Einhaltung der Service Levels berichtet? (z.B. monatliche Berichte über Verfügbarkeit und Reaktionszeiten).
8. **Pönalen (Strafen) und Boni:**
    - Was sind die Konsequenzen, wenn ein Service Level nicht erreicht wird (z.B. anteilige Rückerstattung der Kosten)?
    - Gibt es Anreize, wenn der Dienstleister die Service Levels übererfüllt?
9. **Laufzeit und Kündigungsbedingungen:**
    - Wie lange ist der Vertrag gültig?
    - Wie kann er gekündigt oder verlängert werden?
10. **Änderungsmanagement:**
    - Wie werden Änderungen am SLA selbst oder an den vereinbarten Services vorgenommen?

---

### Vorteile eines SLA für den Servicenehmer (Kundenperspektive)

- **Transparenz und Planbarkeit:** Er weiß genau, welche Leistung er erwarten kann und welche Kosten damit verbunden sind. Er kann seine eigenen Prozesse besser planen.
- **Qualitätssicherung:** Er hat eine vertragliche Garantie für eine bestimmte Servicequalität und kann deren Einhaltung überprüfen.
- **Messbarkeit:** Die Leistung des Dienstleisters wird objektiv messbar.
- **Schutz vor Leistungsmängeln:** Er hat eine Grundlage für Reklamationen und eventuelle Kompensationsforderungen, falls die vereinbarten Leistungen nicht erbracht werden.
- **Bessere Budgetierung:** Die Kosten für die IT-Services sind klar definiert und planbar.
- **Fokus auf das Kerngeschäft:** Der Kunde kann sich auf seine Hauptaufgaben konzentrieren, da die IT-Leistungen vertraglich geregelt und abgesichert sind.

---

### Vorteile eines SLA für den Servicegeber (Dienstleisterperspektive)

- **Klarheit und Erwartungsmanagement:** Der Dienstleister weiß genau, was von ihm erwartet wird, und kann seine Ressourcen entsprechend planen. Er vermeidet unklare oder unerwartete Forderungen.
- **Effizienz und Standardisierung:** Durch die klare Definition der Services können Prozesse standardisiert und optimiert werden.
- **Abgrenzung und Schutz:** Das SLA definiert klar die Grenzen der eigenen Verantwortung und schützt vor unberechtigten Forderungen. Es legt fest, was NICHT Bestandteil des Services ist.
- **Messung der eigenen Leistung:** Der Dienstleister kann seine eigene Performance objektiv messen und nachweisen.
- **Verbesserungspotenziale erkennen:** Durch die Messung der KPIs können Engpässe und Bereiche für Verbesserungen identifiziert werden.
- **Vertrauensbildung und Wettbewerbsvorteil:** Ein transparentes und eingehaltenes SLA stärkt das Vertrauen der Kunden und kann ein Wettbewerbsvorteil sein.
- **Basis für Preisgestaltung:** Die Qualität und der Umfang der Leistung sind die Grundlage für die Preisgestaltung.

---

### Wichtige Qualitätsgrößen in SLAs

Dies sind die Kennzahlen, die in SLAs am häufigsten verwendet werden, um die Servicequalität zu messen:

- **Verfügbarkeit (Availability):**
    - Der Prozentsatz der Zeit, in der ein IT-Service, eine Komponente oder ein System nutzbar und betriebsbereit ist. Wird oft als "Uptime" gemessen.
    - **Beispiel:** "Der E-Mail-Dienst muss 99,9% der vereinbarten Servicezeiten verfügbar sein." (Das bedeutet, maximal ca. 43 Minuten Ausfall pro Monat).
- **Zuverlässigkeit (Reliability):**
    - Misst, wie lange ein Service ohne Unterbrechung oder Fehler funktioniert. Häufig gemessen als "Mean Time Between Failures (MTBF)" (durchschnittliche Zeit zwischen zwei Ausfällen) oder "Mean Time Between Service Incidents (MTBSI)".
    - **Beispiel:** "Die durchschnittliche Zeit zwischen zwei kritischen Softwarefehlern darf 30 Tage nicht unterschreiten."
- **Wartbarkeit (Maintainability):**
    - Bezieht sich darauf, wie schnell und einfach ein Service oder eine Komponente wiederhergestellt oder repariert werden kann. Gemessen oft als "Mean Time To Restore Service (MTRS)" (durchschnittliche Zeit zur Wiederherstellung des Services) oder "Mean Time To Repair (MTTR)".
    - **Beispiel:** "Die durchschnittliche Zeit zur Wiederherstellung des Datenbankdienstes nach einem Ausfall darf 2 Stunden nicht überschreiten."
- **Performance/Antwortzeit (Response Time):**
    - Die Zeit, die ein System oder eine Anwendung benötigt, um auf eine Benutzeranfrage zu reagieren.
    - **Beispiel:** "Die Antwortzeit für das Login in die Unternehmensanwendung darf 5 Sekunden nicht überschreiten."
- **Durchsatz (Throughput):**
    - Die Menge an Arbeit, die ein System in einer bestimmten Zeiteinheit verarbeiten kann (z.B. Anzahl der Transaktionen pro Sekunde).
    - **Beispiel:** "Das E-Commerce-System muss in der Lage sein, 500 Bestellungen pro Minute zu verarbeiten."
- **Sicherheit (Security):**
    - Definition von Maßnahmen und Standards zum Schutz von Daten und Systemen (z.B. Verschlüsselungsprotokolle, Zugriffskontrollen, Regelmäßigkeit von Sicherheitsaudits).
    - **Beispiel:** "Alle Kundendaten müssen End-to-End verschlüsselt sein und mindestens einmal jährlich einem externen Sicherheitsaudit unterzogen werden."

## References
1. 
