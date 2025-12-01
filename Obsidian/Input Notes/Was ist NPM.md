
--- 
Erstellt: 2025-05-30    22:50 
Tags: #Programming/JavaScript/NodeJS
Link Up: [[JavaScript]]
Link Down:

--- 
# NPM für Node.js 
NPM steht für Node Package Manager und ist der Standart-Paketmanager für die JavaScript Laufzeitumgebung Node.js. Stell dir eine NPM als eine riesige Bibliothek vor, in der Entwickler Code-Pakete teilen und wiederverwenden können.

Was ist NPM?
NPM ist ein essenzielles Werkzeug für die moderne Node.js-Entwicklung. Es ermöglicht dir:
- **Pakete installieren:** Du kannst Tausende von vorgefertigten Code-Paketen (Bibliotheken, Frameworks, Tools) aus dem NPM-Register direkt in dein Projekt herunterladen und nutzen. Das erspart dir das Rad neu zu erfinden und beschleunigt die Entwicklung enorm.
- **Abhängigkeiten verwalten:** Projekte haben oft viele externe Pakete, von denen sie abhängig sind. NPM verwaltet diese Abhängigkeiten automatisch, indem es sicherstellt, dass die richtigen Versionen installiert sind.
- **Eigene Pakete veröffentlichen:** Wenn du nützlichen Code geschrieben hast, kannst du ihn über NPM mit der Welt teilen, sodass andere Entwickler ihn ebenfalls nutzen können.
- **Skripte ausführen:** In der `package.json`-Datei deines Projekts kannst du benutzerdefinierte Skripte definieren (z.B. für Tests, Build-Prozesse), die du dann einfach mit `npm run <skriptname>` ausführen kannst.

### Warum ist NPM so wichtig?
- **Effizienz:** Du musst nicht alles von Grund auf neu programmieren. Nutze die kollektive Arbeit der Entwicklergemeinschaft.
- **Standardisierung:** NPM bietet einen standardisierten Weg, wie Projekte ihre Abhängigkeiten definieren und wie diese Abhängigkeiten installiert werden.
- **Gemeinschaft:** Es fördert die Zusammenarbeit und den Austausch von Code innerhalb der JavaScript-Community.

### Wichtige NPM-Befehle (Beispiele)
- `npm install`: Installiert alle im Projekt definierten Abhängigkeiten (aus der `package.json`).
- `npm install <paketname>`: Installiert ein spezifisches Paket in deinem Projekt.
- `npm install -g <paketname>`: Installiert ein Paket global auf deinem System, sodass du es von überall aus nutzen kannst (z.B. Kommandozeilen-Tools).
- `npm update`: Aktualisiert installierte Pakete auf neuere Versionen.
- `npm uninstall <paketname>`: Entfernt ein Paket aus deinem Projekt.
- `npm init`: Initialisiert ein neues Node.js-Projekt und erstellt eine `package.json`-Datei.

**Grundsätzlich kann man sagen das NPM das Pendant zu Composer für [[PHP]] ist**
## References
1. 
