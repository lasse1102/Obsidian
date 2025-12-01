
--- 
Erstellt: 2025-06-16    19:52 
Tags: 
Link Up: 
Link Down:

--- 
# NodeJS Projekt erstellen mit Docker
NodeJS Projekt mit Docker und Git

Projektstruktur

mein-super-projekt/ 
├── frontend/ 
│ ├── Dockerfile 
│ └── (hier kommt dein React/Vite Projekt rein) 
├── backend/ 
│ ├── Dockerfile 
│ └── (hier kommt dein Node.js Projekt rein) 
├── docker-compose.yml 
├── .gitignore 
└── README.md

### Voraussetzungen
- Docker Desktop (oder Docker Engine und Docker Compose)
- Installation für Windows
- Git: Installation

Schritte

1. Projektverzeichnis erstellen und Git initialisieren
	mkdir mein-super-projekt 
	cd mein-super-projekt 
	git init
	
2. Backend (Node.js) einrichten
	1. Verzeichnis erstellen: 
		mkdir backend 
		cd backend
    
	2. Einfaches Node.js Projekt initialisieren (optional): 
		npm init -y 
		npm install express 
		backend/index.js -> erstellen
		
	3. backend/Dockerfile erstellen: 
		```JavaScript
		FROM node:20-alpine 
		WORKDIR /app 
		COPY package*.json ./ 
		RUN npm install 
		COPY . .
		EXPOSE 3000 CMD ["node", "index.js"] 
		```
	4. Zurück ins Hauptverzeichnis: 
		cd ..

3. Frontend (React/Vite) einrichten
    
	1. Verzeichnis erstellen: 
		mkdir frontend 
		cd frontend
	2. Neues Vite-Projekt erstellen: 
		npm create vite@latest . -- --template react
	3. Abhängigkeiten installieren: 
		npm install
	4. frontend/Dockerfile erstellen:
	    ```JavaScript
		# frontend/Dockerfile
        # Phase 1: Build-Phase
        FROM node:20-alpine AS build
        WORKDIR /app
        COPY package*.json ./
        RUN npm install
        COPY . .
        RUN npm run build
        
	    # Phase 2: Serve-Phase (optional, aber empfohlen für    
	    Produktiv-Builds)
	    
        FROM nginx:stable-alpine
        COPY --from=build /app/dist /usr/share/nginx/html
        EXPOSE 80
        CMD ["nginx", "-g", "daemon off;"]
		```


  4. docker-compose.yml
```JavaScript
version: '3.8'

services: 
	backend: 
		build: 
			context: ./backend 
			dockerfile: Dockerfile 
		ports:
			"3000:3000" 
		volumes:
			./backend:/app
			/app/node_modules 
		environment: 
			NODE_ENV: development

	frontend: 
		build: 
			context: ./frontend 
			dockerfile: Dockerfile 
			ports:
				"80:80"
				"5173:5173" 
			volumes:
				./frontend:/app
				/app/node_modules 
			depends_on:
				backend
```


5. .gitignore erstellen
	```JavaScript
	#.gitignore
	node_modules/ 
	dist/ 
	.env 
	npm-debug.log* 
	yarn-debug.log* 
	yarn-error.log* 
	.DS_Store 
	*.log tmp/
```

6. Docker Compose starten
	docker compose up --build

7. Testen der Anwendung

- Backend: http://localhost:3000
- Frontend (Nginx): http://localhost:80
- Frontend (Vite Dev Server): http://localhost:5173

### Nützliche Docker Compose Befehle
- Container stoppen: docker compose stop
- Container stoppen und entfernen: docker compose down
- Logs anzeigen: docker compose logs -f
- Bestimmten Dienst starten: docker compose up backend
- Container neu starten: docker compose restart
- Images entfernen: docker compose down --rmi all

### Git-Integration
git add . 
git commit -m "Initial project setup with Docker Compose, Node.js and React/Vite" git branch -M main 
git remote add origin <dein_repository_url> 
git push -u origin main

### Zusätzliche Tipps
- Umgebungsvariablen: .env-Dateien und Docker Compose env_file.
- Datenbank: Weiteren Dienst in docker-compose.yml hinzufügen.
- Performance auf macOS/Windows: delegated oder cached in den Volume-Definitionen.
- Linter/Formatter: Prettier, ESLint oder TSLint.
- CI/CD: Integration in eine CI/CD-Pipeline.


---

##  Detaillierte Erklärung (Dockerfiles, docker-compose)

1. **`Dockerfile` für das Backend (Node.js)**
2. **`Dockerfile` für das Frontend (React/Vite)**
3. **`docker-compose.yml`**


##### 1. `Dockerfile` für das Backend (Node.js)

Ein `Dockerfile` ist eine Textdatei, die eine Reihe von Anweisungen enthält, die Docker verwenden kann, um ein **Image** zu bauen. Ein Image ist wie eine Vorlage oder ein Bauplan für einen Container. Es enthält alles, was zum Ausführen einer Anwendung benötigt wird: Code, Bibliotheken, Laufzeitumgebung, Systemwerkzeuge, etc.

Stell dir ein Dockerfile als ein Rezept für einen Kuchen vor. Jede Zeile ist eine Anweisung, wie eine Zutat hinzugefügt oder ein Schritt im Backprozess ausgeführt wird.

Dockerfile
![[Pasted image 20250616230326.png]]

- **`# backend/Dockerfile`**: Dies ist ein Kommentar. Zeilen, die mit `#` beginnen, werden von Docker ignoriert. Sie dienen nur der Lesbarkeit und Dokumentation.
    
- **`FROM node:20-alpine`**:
    - **Was es macht:** Dies ist die **erste und wichtigste Anweisung** in fast jedem Dockerfile. Sie definiert das **Basis-Image**, auf dem unser Image aufbaut.
    - **Warum es wichtig ist:** Anstatt ein komplettes Betriebssystem von Grund auf neu zu konfigurieren (was sehr aufwendig wäre), nutzen wir ein bereits existierendes, optimiertes Image. `node:20-alpine` ist ein offizielles Image, das bereits Node.js Version 20 und eine schlanke Alpine Linux-Distribution enthält. Alpine Linux ist bekannt für seine geringe Größe, was zu kleineren und schnelleren Images führt.
    - **Analogie:** Das ist, als würde man ein vorgefertigtes Kuchenboden-Rezept verwenden, anstatt den Teig von Grund auf neu zu machen.
- **`WORKDIR /app`**:
    - **Was es macht:** Diese Anweisung legt das **Arbeitsverzeichnis** innerhalb des Containers fest. Alle nachfolgenden Befehle (wie `COPY` oder `RUN`) werden relativ zu diesem Verzeichnis ausgeführt, es sei denn, ein absoluter Pfad wird angegeben.
    - **Warum es wichtig ist:** Es sorgt für Struktur und Konsistenz innerhalb des Containers. Statt Dateien irgendwohin zu kopieren, haben wir einen definierten Ort, wo unsere Anwendung liegen wird.
    - **Analogie:** Das ist wie das Festlegen des Bereichs auf der Arbeitsplatte, wo du alle deine Zutaten und Utensilien für den Kuchen ablegen wirst.
- **`COPY package*.json ./`**:
    - **Was es macht:** Dieser Befehl kopiert Dateien vom **Host-System** (deinem Computer, auf dem Docker läuft) in das **Container-Image**.
        - `package*.json`: Dies ist ein Wildcard-Muster, das sowohl `package.json` als auch `package-lock.json` (oder `yarn.lock`, falls du Yarn nutzt) erfasst. Diese Dateien enthalten die Metadaten deines Node.js-Projekts und die Liste seiner Abhängigkeiten.
        - `./`: Dies ist der Zielpfad im Container. Er bezieht sich auf das aktuelle `WORKDIR` (`/app`).
    - **Warum es wichtig ist:** Wir kopieren diese Dateien _bevor_ wir `npm install` ausführen. Docker nutzt ein Konzept namens "[[Layer-Caching]]". Wenn sich diese Dateien nicht ändern, kann Docker diesen Layer aus einem früheren Build wiederverwenden, was den Build-Prozess beschleunigt. Wenn du zuerst den gesamten Code kopieren würdest und dann `npm install`, müsste Docker bei jeder Code-Änderung (egal wie klein) auch `npm install` neu ausführen, da der Layer für den Code sich geändert hat.
    - **Analogie:** Du legst zuerst die Zutatenliste (package.json) auf deine Arbeitsplatte, bevor du mit dem tatsächlichen Kochen beginnst.
- **`RUN npm install`**:
    - **Was es macht:** Führt einen Befehl **innerhalb des Containers** während des Build-Prozesses aus. Hier installieren wir alle Node.js-Abhängigkeiten, die in `package.json` aufgeführt sind.
    - **Warum es wichtig ist:** Die Abhängigkeiten werden _im Image_ installiert. Das bedeutet, wenn der Container später gestartet wird, sind alle benötigten Pakete bereits vorhanden und müssen nicht bei jedem Start erneut heruntergeladen werden.
    - **Analogie:** Dies ist der Schritt, in dem du alle benötigten Zutaten aus deiner Speisekammer holst und vorbereitest (z.B. Mehl abmessen, Eier aufschlagen).
- **`COPY . .`**:
    - **Was es macht:** Kopiert den **restlichen Code** aus dem aktuellen Verzeichnis auf deinem Host-System (das `backend`-Verzeichnis) in das aktuelle Arbeitsverzeichnis (`/app`) im Container.
    - **Warum es wichtig ist:** Jetzt, da die Abhängigkeiten installiert sind (und dieser Layer gecacht werden kann), kopieren wir den eigentlichen Anwendungs-Code.
    - **Analogie:** Du legst jetzt das eigentliche Rezeptblatt (dein Code) auf die Arbeitsplatte.
- **`EXPOSE 3000`**:
    - **Was es macht:** Diese Anweisung **dokumentiert**, dass der Container beabsichtigt, auf dem angegebenen Port (hier 3000) zur Laufzeit zu lauschen.
    - **Warum es wichtig ist:** Es ist _keine_ Firewall-Regel und öffnet den Port nicht automatisch nach außen auf deinem Host-System. Es ist eher eine Information für andere Entwickler oder Tools, die mit diesem Image arbeiten. Die tatsächliche Port-Weiterleitung wird später in `docker-compose.yml` oder beim direkten `docker run` Befehl konfiguriert.
    - **Analogie:** Du schreibst auf das Kuchenrezept, dass der Kuchen bei X Grad gebacken werden soll. Das ist eine wichtige Information, aber der Ofen ist noch nicht eingeschaltet.
- **`CMD ["node", "index.js"]`**:
    - **Was es macht:** Dies definiert den **Standardbefehl**, der ausgeführt wird, wenn ein Container aus diesem Image gestartet wird.
    - **Warum es wichtig ist:** Es ist der "Startpunkt" deiner Anwendung. Wenn du einen Container aus diesem Image startest, weiß Docker, dass es `node index.js` ausführen soll, um deine Backend-Anwendung zu starten. Wenn du einen anderen Befehl beim Start angeben würdest (`docker run mein-image bash`), würde dieser `CMD` überschrieben.
    - **Analogie:** Das ist die letzte Anweisung im Rezept: "Den Kuchen für X Minuten backen." Es ist der endgültige Schritt, um das Endprodukt zu erhalten.

---

##### 2. `Dockerfile` für das Frontend (React/Vite)
Für das Frontend haben wir einen sogenannten **[[Single-Stage Build & Multi Stage Build|Single-Stage Build]]** verwendet. Das ist ein Konzept in Docker, welches ein Image in einen einzigen Schritt erstellt, ohne zwischen verschieden `FROM`- Anweisungen zu wechseln

**Option 1: Single-Stage Build für Entwicklungs-Server**
![[Pasted image 20250616230436.png]]
Lass uns die Phasen und neuen Befehle detailliert betrachten:

#### **Phase 1: Build-Phase**
- **`FROM node:20-alpine AS build`**:
    - **Was es macht:** Startet eine neue Build-Phase, genau wie ein normales Dockerfile. Das `AS build` gibt dieser Phase einen **Namen**, den wir später referenzieren können.
    - **Warum es wichtig ist:** In dieser Phase haben wir alle Tools, die zum Kompilieren (Build) unserer React-Anwendung benötigt werden (Node.js, npm, Babel, Webpack/Vite, etc.).
- **`WORKDIR /app`**, **`COPY package*.json ./`**, **`RUN npm install`**, **`COPY . .`**:
    - Diese Befehle funktionieren exakt wie im Backend-Dockerfile erklärt. Sie richten das Projekt ein und installieren die Abhängigkeiten.
- **`RUN npm run build`**:
    - **Was es macht:** Führt das `build`-Skript aus, das in deiner `package.json` definiert ist (typischerweise `react-scripts build` für Create React App oder `vite build` für Vite). Dieses Skript kompiliert deinen React-Code (JSX, TypeScript, Sass usw.) in statische HTML-, CSS- und JavaScript-Dateien, die für die Auslieferung an den Browser optimiert sind. Diese Dateien werden normalerweise in einem Verzeichnis namens `dist/` oder `build/` abgelegt.
    - **Warum es wichtig ist:** Dies ist der Kern der Build-Phase. Es erzeugt das fertige, statische Frontend, das später ausgeliefert werden soll.

#### **Phase 2: Serve-Phase**

- **`FROM nginx:stable-alpine`**:
    
    - **Was es macht:** Startet eine **zweite, unabhängige Build-Phase**. Dieses Mal verwenden wir das **Nginx**-Image. Nginx ist ein sehr leichter und performanter Webserver, der sich hervorragend zum Ausliefern statischer Dateien eignet. `stable-alpine` ist eine stabile Version basierend auf Alpine Linux.
    - **Warum es wichtig ist:** Wir benötigen Node.js nicht mehr, um die _fertige_ React-Anwendung auszuliefern. Nginx ist viel effizienter und kleiner für diese Aufgabe. Durch den Multi-Stage Build wird die "build"-Phase mit all ihren Tools und Abhängigkeiten (die oft sehr groß sind) nicht in das endgültige Image übernommen.
    - **Analogie:** Der Kuchen ist fertig gebacken. Jetzt brauchst du den Ofen nicht mehr, sondern nur noch eine Servierplatte, um ihn zu präsentieren. Nginx ist die Servierplatte.
- **`COPY --from=build /app/dist /usr/share/nginx/html`**:
    
    - **Was es macht:** Dies ist der Schlüsselbefehl des Multi-Stage Builds. Er kopiert Dateien **aus einer vorherigen Build-Phase** in die aktuelle Phase.
        - `--from=build`: Gibt an, dass die Dateien aus der Phase namens `build` (die erste Phase) kopiert werden sollen.
        - `/app/dist`: Dies ist der Quellpfad in der `build`-Phase. Dort hat `npm run build` die fertigen Frontend-Dateien abgelegt.
        - `/usr/share/nginx/html`: Dies ist der Standardpfad, aus dem Nginx statische Dateien ausliefert.
    - **Warum es wichtig ist:** Es ermöglicht uns, nur die _fertigen Artefakte_ (die optimierten HTML, CSS, JS-Dateien) in das finale, schlanke Nginx-Image zu übertragen, ohne die gesamten Node.js-Build-Tools mitzuschleppen. Das finale Image wird dadurch erheblich kleiner.
- **`EXPOSE 80`**:
    
    - **Was es macht:** Dokumentiert, dass der Nginx-Container auf Port 80 (Standard-HTTP-Port) lauscht.
- **`CMD ["nginx", "-g", "daemon off;"]`**:
    
    - **Was es macht:** Startet den Nginx-Webserver.
        - `-g "daemon off;"`: Stellt sicher, dass Nginx im Vordergrund läuft und nicht als Daemon im Hintergrund. Dies ist wichtig für Docker, da der Container am Leben bleibt, solange der Hauptprozess läuft. Wenn Nginx sich in den Hintergrund begeben würde, würde Docker denken, der Prozess ist beendet, und den Container beenden.
    - **Warum es wichtig ist:** Dies ist der Befehl, der den Webserver startet und somit deine React-App im Browser verfügbar macht.



### docker-compose
Die `docker-compose.yml` ist eine Konfigurationsdatei im YAML-Format, die von **Docker Compose** verwendet wird. Stell dir Docker Compose als ein Tool vor, das dir hilft, **mehrere Docker-Container gleichzeitig zu definieren, zu starten und zu verwalten**, die zusammen eine Anwendung bilden.

Im Grunde genommen ist die `docker-compose.yml` die "Blaupause" für deine Multi-Container-Anwendung. Anstatt jeden Container einzeln mit `docker run` zu starten und die Verbindungen manuell herzustellen, beschreibst du in dieser einen Datei:

- **Welche Dienste (Services) deine Anwendung benötigt:** Das können zum Beispiel ein Webserver (wie dein Frontend), eine Backend-API, eine Datenbank oder ein Message Broker sein. Jeder Dienst ist ein eigener Container.
- **Wie jeder dieser Dienste gebaut oder von einem Image gezogen werden soll:** Du gibst an, ob Docker ein Image aus einem `Dockerfile` im aktuellen Verzeichnis bauen soll (`build: .`) oder ob es ein bereits existierendes Image von Docker Hub ziehen soll (`image: nginx:latest`).
- **Welche Ports nach außen freigegeben werden sollen:** Damit deine Anwendung von außerhalb des Docker-Netzwerks erreichbar ist. Zum Beispiel `ports: - "80:80"` bedeutet, dass Port 80 des Containers auf Port 80 deines Host-Systems gemappt wird.
- **Welche Volumes (Volumes) gemountet werden sollen:** Das ist extrem wichtig für die Persistenz von Daten und für die Entwicklung. Ein Volume kann ein Verzeichnis auf deinem Host-System sein, das in den Container gemountet wird. Das ermöglicht:
    - **Hot-Reloading/Live-Reloading:** Änderungen am Code auf deinem Host-System werden sofort im Container sichtbar, ohne dass du den Container neu starten musst. (`- ./backend:/app`)
    - **Datenpersistenz:** Datenbanken oder andere Container, die Daten speichern sollen, können diese Daten auf deinem Host-System ablegen, sodass sie auch nach dem Entfernen des Containers erhalten bleiben.
- **Umgebungsvariablen (Environment Variables):** Du kannst Umgebungsvariablen definieren, die in den Containern verfügbar sind. Das ist nützlich für Konfigurationen, Datenbankzugangsdaten usw. (`environment: NODE_ENV: development`).
- **Abhängigkeiten zwischen Diensten (`depends_on`):** Du kannst festlegen, dass ein Dienst erst gestartet werden soll, nachdem ein anderer Dienst läuft. Im Beispiel oben ist `frontend` von `backend` abhängig, was bedeutet, dass der Backend-Container gestartet wird, bevor der Frontend-Container versucht, seine Verbindung herzustellen. Beachte, dass `depends_on` nur die Startreihenfolge regelt, nicht die vollständige Verfügbarkeit des Dienstes.

**Warum ist das so nützlich?**

1. **Vereinfachung der Entwicklungsumgebung:** Mit einer einzigen `docker-compose up`-Anweisung kannst du eine komplexe Anwendungsumgebung mit mehreren Diensten starten, die alle korrekt miteinander verbunden sind. Das spart enorm viel Zeit und Aufwand.
2. **Reproduzierbarkeit:** Jeder, der deine `docker-compose.yml` hat, kann exakt dieselbe Entwicklungsumgebung auf seinem Rechner starten. Das eliminiert das berüchtigte "Bei mir funktioniert es aber!"-Problem.
3. **Portabilität:** Du kannst dieselbe `docker-compose.yml` für die Entwicklung, das Testen und sogar für kleinere Produktivumgebungen verwenden.
4. **Versionierung:** Da die `docker-compose.yml` eine Datei ist, kannst du sie zusammen mit deinem Quellcode in die Versionskontrolle (Git) aufnehmen.

**Im Kontext deines NodeJS-Projekts:**

- `backend`: Definiert deinen Node.js-Backend-Dienst. Es wird ein Dockerfile im `backend`-Verzeichnis verwendet, Port 3000 wird nach außen freigegeben, und dein lokaler Backend-Code wird in den Container gemountet, sodass du Änderungen in Echtzeit siehst.
- `frontend`: Definiert deinen React/Vite-Frontend-Dienst. Ähnlich wie beim Backend wird ein Dockerfile im `frontend`-Verzeichnis verwendet. Hier werden Port 80 (für Nginx, das deinen gebauten Frontend-Code serviert) und Port 5173 (für den Vite-Entwicklungsserver) nach außen freigegeben. Es hängt vom Backend ab, um sicherzustellen, dass das Backend verfügbar ist.
```JavaScript
version: '3.8'

services: 
	backend: 
		build: 
			context: ./backend 
			dockerfile: Dockerfile 
		ports:
			"3000:3000" 
		volumes:
			./backend:/app
			/app/node_modules 
		environment: 
			NODE_ENV: development

	frontend: 
		build: 
			context: ./frontend 
			dockerfile: Dockerfile 
			ports:
				"80:80"
				"5173:5173" 
			volumes:
				./frontend:/app
				/app/node_modules 
			depends_on:
				backend
```













## References
1. 
