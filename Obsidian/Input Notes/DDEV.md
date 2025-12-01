
--- 
Erstellt: 2025-04-03    07:17 
Tags: #Programming/Docker
Link Up: [[Docker]]
Link Down:

--- 
# Was ist DDEV
DDEV ist ein Open-Source-Tool, das speziell für Entwickler von [[PHP]] basierten Webanwendungen entwickelt wurde. Es vereinfacht die Einrichtung und Verwaltung lokaler Entwicklungsumgebungen erheblich. 

- **Entwicklungsumgebung**
	- DDEV ermöglicht es Entwicklern, schnell und einfach eine lokale Entwicklungsumgebung für ihre Webprojekte einzurichten
	- Es abstrahiert die Komplexität der Konfiguration und bietet vorkonfigurierte Umgebungen für gängige PHP-basierte Anwendungen wie WordPress, Drupral, TYPO3 und Laraval.
- **[[Docker]]-basiert:**
	- DDEV basiert auf [[Docker]], was bedeutet, dass es Container verwendet, um isolierte und reproduzierbare Entwicklungsumgebungen zu erstellen.
	- Dadurch wird sichergestellt, dass die Entwicklungsumgebung auf verschiedenen Systemen konsistent ist.
- **Benutzerfreundlichkeit:**
	- DDEV ist darauf ausgelegt, benutzerfreundlich zu sein. Es bietet eine einfache Befehlszeilenschnittstelle, mit der Entwickler ihre Entwicklungsumgebungen verwalten können.
	- Es automatisiert viele Aufgaben, die normalerweise manuell durchgeführt werden müssten, wie z. B. die Konfiguration von Webservern, Datenbanken und anderen Diensten.


**Zusammenfassend:**
DDEV ist ein Werkzeug, das die Vorteile von Docker nutzt, um die Entwicklung von PHP-basierten Webprojekten zu vereinfachen. Es bietet eine benutzerfreundliche Schnittstelle und automatisiert viele Aufgaben, die mit der Einrichtung und Verwaltung von Entwicklungsumgebungen verbunden sind.



# Neues Projekt mit ddev erstellen in PHPStorm
1. Terminal öffnen (optimal fall das aus der Entwicklungsumgebung) und in das Verzeichnis des Projektes navigieren
2. ddev config eingeben
3. den Projektnamen auswählen
4. Das Document Root Verzeichnis auswählen (normal fall "Public")
5. Vorhandene Frameworks auswählen
6. zum Schluss auf "ddev start" eingeben 

Projekt ist nun unter der angegebenen Route aufrufbar. Hier wird jedoch noch ein Fehler angezeigt, da Composer und die dazugehörigen Abhängigkeiten noch nicht installiert wurden sind.
1. ddev composer install

## References
1. https://ddev.readthedocs.io/en/stable/
