
--- 
Erstellt: 2025-11-01    00:33 
Tags: 
Link Up: [[AP2]]
Link Down:

--- 

# Manuelles vs. automatisiertes Testen
Softwaretests lassen sich im wesentlichen in zwei große Kategorien einteilen
### Manuelles Testen
Manuelles Testen ist der Prozess, bei dem Tester Testfälle manuell und ohne die Unterstützung von Tools ausführen. Tester führen Aktionen wie das Klicken auf Schaltflächen, die Eingabe von Text und die Überprüfung von Ausgaben durch und simulieren so, wie ein Endbenutzer mit der Software interagieren würde.
### automatisiertes Testen
Beim automatisierten Testen werden Skripte und Tools verwendet, um Tests an Software automatisch auszuführen. Dieser grundlegende Ansatz ist vorteilhaft für sich wiederholende Testaufgaben und für größere Systeme, bei denen dieselben Tests mehrfach durchgeführt werden müssen.

Automatisierte Tests sorgen dafür, dass Software schneller und konsistenter getestet werden kann. Außerdem werden menschliche Fehler reduziert und die Testeffizienz im Laufe der Zeit verbessert.

---

# Stufen von Softwaretests
Im Allgemeinen erfolgt das Testen von Software auf vier verschiedenen Ebenen – oder Phasen – innerhalb des [Softwareentwicklungszyklus](https://www.ibm.com/de-de/think/topics/software-development), wobei jede Ebene sich auf bestimmte Teile der Anwendung konzentriert:
- Unit-Tests(Komponententest)
- Integration Testing
- Systemtests
- Abnahmetests


**Unit-Tests(Komponententest):**
Unit-Tests sind sehr einfach zu erfolgen nah an der Quelle der Anwendung. Sie dienen, zum Testen einzelner Methoden und Funktionen der von der Software verwendeten Klassen, Komponenten oder Module. In der Regel lassen sich Unit Test kostengünstig automatisieren.
Oft werden sie in derselben Programmiersprache wie das zu testende Objekt verfasst. Unit-Tests unterstützen Praktiken wie testgetriebene Entwicklung (TDD) und Refactoring.



**Integration Testing:**
Mit Integrationstest wird sichergestellt, dass verschiedene von deiner Anwendung genutzte Module oder Services problemlos ineinandergreifen. So kann beispielsweise die Interaktion mit der Datenbank oder das Zusammenspiel von Mikroservices getestet werden. Test dieser Art sind kostspieliger, weil dafür mehrere Teile der Anwendung funktionsfähig sein müssen



**Systemtests**
Systemtests sind eine Teststufe, bei der das **komplett integrierte Softwaresystem** als Ganzes überprüft wird, um sicherzustellen, dass es die **gesamten spezifizierten Anforderungen** erfüllt. Sie werden in einer **realitätsnahen Umgebung** durchgeführt und konzentrieren sich darauf, ob das System als Endprodukt funktioniert und alle funktionalen und nicht-funktionalen Anforderungen, wie beispielsweise die Performance, eingehalten werden. Der Fokus liegt darauf zu bestätigen, dass das System die Erwartungen des Benutzers oder Kunden erfüllt.



Abnahmetests
Abnahmetests sind die **abschließende Teststufe** im Softwareentwicklungsprozess. Ihr Hauptzweck ist es festzustellen, ob das gelieferte System die **vertraglich vereinbarten oder spezifizierten Anforderungen** und die **Geschäftsanforderungen** des Kunden erfüllt. Sie werden in der Regel vom **Endkunden oder dessen Vertreter** durchgeführt, um die **Tauglichkeit für den Echtbetrieb** zu bestätigen und damit die formelle Übernahme zu ermöglichen.

---
# Testmethoden & Vorgehensweisen
**TDD:**
TDD ist keine Testart, sondern eine Disziplin des Programmierens, bei der man nicht beginnt, indem man die Funktion schreibt, sondern indem man den **Test für die Funktion** schreibt. Dies geschieht in einem schnellen, wiederholten Zyklus
1. Red: Schreibe einen fehlschlagenden Unit-Test
	- Du definierst zunächst das gewünschte Verhalten in Form eines Unit-Test. Da die Funktion die diese Verhalten erfüllen soll, noch nicht existiert, schlägt der Test fehl (daher: rot)
2. Green: Schreibe gerade genug Code
	- Du schreibst so wenig Produktiv-Code wie nötig, damit der zuvor fehlschlagende Test erfolgreich durchläuft (grün)
	- Zweck: Die neue Funktionalität minimal implementieren und den Test erfolgreich bestehen
3. Refactor (Überarbeiten) 
	- Sobald alle Tests grün sind, **verbesserst** du die interne Struktur des Codes (z. B. Lesbarkeit, Effizienz), ohne die Funktionalität zu ändern. **Alle Unit-Tests** werden danach erneut ausgeführt, um sicherzustellen, dass das Refactoring keine Fehler verursacht hat.
	- _Zweck:_ Sicherstellen, dass der Code **sauber** und **wartbar** bleibt, während die Tests die Funktionalität schützen.

**White-Box Test**
Beim White-Box-Test hat der Tester vollständiges Wissen über die interne Struktur, den Quellcode und das Design der Software
	Funktionsweise:
		Der Tester verwendet sein Wissen über den Code, um Testfälle zu entwickeln, die spezifische Codepfade, interne Schleifen, Datenstrukturen und Entscheidungslogik abdecken
		Das Ziel ist es sicherzustellen, dass jeder Teil des Codes mindestens einmal ausgeführt wird.

**Black-Box-Test**
Beim Black-Box-Test hat der Tester kein Wissen über die interne Struktur, den Code oder das Design der Software
	Funktionsweise
		Beim Black-Box-Test tappen Testerinnen und Tester gewissermaßen im Dunkeln, sie wissen nicht, wie eine Software funktioniert, wie sie implementiert ist oder aus welchen Komponenten sie besteht. Stattdessen erfolgt der Test anhand der Spezifikationen, getestet werden also alle sichtbaren Komponenten. Black-Box-Tests erfolgen etwa durch valide und invalide Inputs, bei denen User die Funktionsweise eines Systems durch zu erwartende und fehlerhafte Eingaben und Aktionen untersuchen.

---
# Typen von Softwaretests
Es gibt viele verschiedene Arten von Softwaretests, die unter die zuvor beschriebenen Stufen fallen und in der Regel in zwei Hauptkategorien unterteilt werden können:
1. Funktionale Tests
	überprüft, ob eine Softwareanwendung gemäß den festgelegten Anforderungen funktioniert 
2. Nichtfunktionale Tests
	bewertet, wie sich die Software unter verschiedenen Bedingungen verhält, beispielsweise unter Last, Stress oder in unterschiedlichen Umgebungen.

#### A. Funktionale Tests (Prüft, ob es **WAS** tut)
- **Systemtest, Integrationstest, Unit-Test, Abnahmetest** (alle oben genannten Stufen)
- **Regressionstest:** Überprüft, ob neue Änderungen **alte, bereits funktionierende** Features beschädigt haben.
- **Smoketest:** Schnelle, kritische Tests nach einem neuen Build/Deployment, um zu prüfen, ob die **Kernfunktionalität stabil** ist ("Rauchtest").
- **API-Test:** Prüft die Funktionalität der Schnittstellen (oft Teil des Integrations- oder Unit-Tests).
    

#### B. Nicht-Funktionale Tests (Prüft, wie gut es **WIE** tut)
- **Leistungstest/Performancetest:** Misst Antwortzeiten und Durchsatz unter **erwarteter** Last.
- **Stresstest:** Testet das System **über die erwartete Last hinaus** bis zum Fehlerpunkt (Belastbarkeit).
- **Sicherheitstest:** Identifiziert Schwachstellen und überprüft Schutzmechanismen (z.B. gegen SQL Injection).
- **Usability-Test:** Bewertet die **Benutzerfreundlichkeit**, Zugänglichkeit und die Lernkurve.
- **Recovery-Test:** Prüft die Fähigkeit des Systems zur **Wiederherstellung** nach einem Ausfall.



---
# Übungsaufgaben aus Prüfungen

![[Pasted image 20251113170811.png]]


![[Pasted image 20251113172458.png]]













































































# Die unterschiedlichen Arten von Test
### Unit Test
Unit-Tests sind sehr einfach zu erfolgen nah an der Quelle der Anwendung. Sie dienen, zum Testen einzelner Methoden und Funktionen der von der Software verwendeten Klassen, Komponenten oder Module. In der Regel lassen sich Unit Test kostengünstig automatisieren und können von einem Continuous-Integration-Server sehr schnell durchgeführt werden.
### Integrationstest
Mit Integrationstest wird sichergestellt, dass verschiedene von deiner Anwendung genutzte Module oder Services problemlos ineinandergreifen. So kann beispielsweise die Interaktion mit der Datenbank oder das Zusammenspiel von Mikroservices getestet werden. Test dieser Art sind kostspieliger, weil dafür mehrere Teile der Anwendung funktionsfähig sein müssen
### Funktionstest
Funktionstests konzentrieren sich auf die Geschäftsanforderungen einer Anwendung. Sie verifizieren nur die Ausgabe einer Aktion und überprüfen bei der Durchführung dieser Aktion nicht die Zwischenzustände des Systems.

Integrationstests und Funktionstests sind nicht ganz leicht auseinanderzuhalten, da bei beiden mehrere Komponenten miteinander interagieren müssen. Der Unterschied besteht darin, dass mit einem Integrationstest vielleicht nur überprüft wird, ob Datenbankabfragen generell möglich sind, während bei einem Funktionstest ein bestimmter, von den Produktanforderungen vorgegebener Wert aus der Datenbank abgerufen wird.

---

## Funktionale vs. Nicht-Funktionale Tests
### Funktionalität (Was die Software tun soll)
Diese Tests prüfen, ob die Software macht, was sie laut den Anforderungen soll:
- **Black-Box-Tests:** Das Testen der **extern sichtbaren Funktionen** ohne Kenntnis des internen Quellcodes. Die Tests basieren auf den Spezifikationen und Anforderungen.
- **Smoke-Tests:** Ein schneller, oberflächlicher Test der **wichtigsten Funktionen**, um zu prüfen, ob die kritischsten Teile der Anwendung überhaupt funktionieren (z. B. nach einem neuen Build).
- **Regressionstests:**
    - **Ziel:** Sicherstellen, dass **Code-Änderungen** (Korrekturen oder Erweiterungen) keine neuen Fehler in bereits funktionierenden Bereichen verursacht haben.    
    - **Durchführung:** Wiederholtes Ausführen früherer Testfälle.   
- **End-to-End-Tests (E2E):** Testen eines **kompletten Geschäftsprozesses** über mehrere Komponenten und Systeme hinweg, aus der Sicht des Endbenutzers.
### Qualität (Wie gut die Software es tut)
Diese Tests prüfen qualitative Aspekte der Software:
- **Performancetests (Leistungstests):**
    - **Lasttests:** Überprüfen, wie sich das System unter **normaler bis hoher Last** (Anzahl der Benutzer oder Transaktionen) verhält.
    - **Stresstests:** Bringen das System absichtlich **an seine Belastungsgrenzen** oder darüber hinaus, um das Verhalten unter extremen Bedingungen zu ermitteln.
- **Usability-Tests (Benutzerfreundlichkeit):** Bewertung, wie **einfach und intuitiv** die Software für den Endbenutzer zu bedienen ist.
- **Sicherheitstests (Security Testing):**
    - **Ziel:** Identifizieren von **Schwachstellen** (z. B. durch Penetrationstests) zum Schutz vor unbefugtem Zugriff oder Datenverlust.
- **Kompatibilitätstests:** Überprüfung der Funktion auf **verschiedenen Plattformen** (Betriebssysteme, Browser, Geräte).








## References
1. 
