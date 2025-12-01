
--- 
Erstellt: 2025-10-29    13:21 
Tags: 
Link Up: [[IT-Sicherheit]] 
Link Down:

--- 
Hier liegt der direkte Fokus der Anwendungsentwicklung. Sie müssen wissen, wie Sie **sicheren Code** schreiben.

### 💻 Gängige Angriffe & Prävention
- **Fokus:** **Eingabevalidierung** und **Ausgabe-Encoding** sind die Schlüsselwörter.
- **Angriffe (Begriffe kennen):**
    - **SQL-Injection:** (Gegenmittel: **Prepared Statements**).
    - **XSS** (Cross-Site Scripting).
    - **CSRF** (Cross-Site Request Forgery).
    - **Man-in-the-Middle** (MITM).
    - **Ransomware** (Digitale Erpressung).


### 1. SQL-Injection (SQLi) 🧱
- **Angriffsziel:** Die **Datenbank**.
- **Beschreibung:** Der Angreifer schleust bösartigen **SQL-Code** in eine Anwendung ein, indem er die erwarteten Datenfelder missbraucht (z. B. in einem Anmelde- oder Suchfeld). Dieser Code wird dann von der Anwendung ausgeführt, was zum Auslesen, Ändern oder Löschen von Daten führen kann.
    
- **Gegenmittel:**
    - **🔑 Prepared Statements (parametrisierte Abfragen):** Dies ist das wichtigste Gegenmittel. Hierbei werden die SQL-Abfrage und die Benutzerdaten getrennt an die Datenbank gesendet. Die Benutzerdaten werden **immer als reine Daten** behandelt und können den Aufbau der Abfrage nicht mehr verändern, was eine Code-Einschleusung verhindert.
    - **Eingabevalidierung:** Stellen Sie sicher, dass die Eingabe dem erwarteten Format entspricht (z.B. nur Ziffern für eine ID).
        

### 2. Cross-Site Scripting (XSS) 📝
- **Angriffsziel:** **Andere Benutzer** der Anwendung.
- **Beschreibung:** Der Angreifer injiziert bösartigen **Client-Side-Code** (meist JavaScript) in eine Webanwendung, der dann im Browser eines anderen Benutzers ausgeführt wird. Dies kann zum Diebstahl von **Sitzungscookies** (Session Hijacking), Anmeldeinformationen oder zur Umleitung auf bösartige Websites führen.
    
- **Gegenmittel:**
    - **🔑 Ausgabe-Encoding (Output Encoding/Escaping):** Der Schlüssel zur XSS-Prävention. Bevor Benutzerdaten auf einer Webseite angezeigt werden, müssen Sonderzeichen (wie `<`, `>`) in ihre Entitäten umgewandelt werden (z.B. `&lt;`, `&gt;`). Der Browser interpretiert den Code dann nur noch als harmlosen Text anstatt ihn als aktives Skript auszuführen.
    - **Eingabevalidierung:** Filtern Sie potenziell schädliche Zeichenketten heraus.

### 3. Cross-Site Request Forgery (CSRF) 🔄
- **Angriffsziel:** Die **Webanwendung** im Namen eines **authentifizierten Benutzers**.
- **Beschreibung:** Ein Angreifer verleitet einen bereits **angemeldeten** Benutzer dazu, unwissentlich eine schädliche HTTP-Anfrage (z.B. eine Geldüberweisung oder Passwortänderung) an die Webanwendung zu senden, der er vertraut. Da der Benutzer authentifiziert ist, führt die Anwendung die Anfrage aus.
    
- **Gegenmittel:**
    - **🔑 Anti-CSRF-Token:** Bei allen zustandsändernden Anfragen (POST, PUT, DELETE) wird ein **zufälliger, geheimer Token** im Formular mitgesendet und auf dem Server geprüft. Da ein Angreifer diesen geheimen Token nicht kennt, schlägt die gefälschte Anfrage fehl.
    - **SameSite-Cookies:** Moderne Browser-Funktion, die hilft, CSRF zu verhindern.

### 4. Man-in-the-Middle (MITM) 🕵️
- **Angriffsziel:** Die **Kommunikation** zwischen zwei Parteien.
- **Beschreibung:** Der Angreifer schaltet sich **unbemerkt** in die Kommunikation zwischen dem Benutzer und dem Server ein. Er kann die übertragenen Daten abhören (eavesdropping) und/oder manipulieren.
    
- **Gegenmittel:**
    - **🔑 TLS/SSL (HTTPS):** Die **Verschlüsselung** der gesamten Kommunikation mittels **Transport Layer Security (TLS)** macht die abgefangenen Daten für den Angreifer unlesbar.
    - **Zertifikatsprüfung:** Sicherstellen, dass die verwendeten SSL/TLS-Zertifikate vertrauenswürdig sind.

### 5. Ransomware (Digitale Erpressung) 💸
- **Angriffsziel:** **Benutzer oder Organisationen** durch Blockieren des Zugangs zu ihren Daten.
- **Beschreibung:** Eine Art von **Malware**, die die Dateien des Opfers verschlüsselt oder den Zugriff auf das System blockiert. Anschließend wird ein **Lösegeld** (ransom) für die Entschlüsselung gefordert. Der Befall erfolgt oft über E-Mail-Anhänge (Phishing) oder ungepatchte Sicherheitslücken.
- **Gegenmittel:**
    - **🔑 Regelmäßige Backups:** Offline- und Offsite-Backups sind der wichtigste Schutz, um Daten wiederherzustellen, ohne das Lösegeld zahlen zu müssen.    
    - **Schulung der Mitarbeiter:** Bewusstsein für Phishing und verdächtige E-Mails schaffen.
    - **Patch-Management:** Software und Betriebssysteme stets aktuell halten, um bekannte Sicherheitslücken zu schließen.
    - **Antiviren-/Endpoint-Schutzsoftware** verwenden.

|Angriff|Kurzfassung|Hauptgegenmittel|
|---|---|---|
|**SQL-Injection**|Einschleusen von SQL-Code in Datenbank-Abfragen.|**Prepared Statements**|
|**XSS**|Einschleusen von Code (z.B. JavaScript) in eine Webseite.|**Ausgabe-Encoding**|
|**CSRF**|Ausführen einer schädlichen Aktion im Namen eines eingeloggten Benutzers.|**Anti-CSRF-Token**|
|**MITM**|Abhören/Manipulieren der Kommunikation.|**HTTPS (TLS/SSL)**|
|**Ransomware**|Verschlüsselung von Daten und Forderung eines Lösegelds.|**Regelmäßige Backups**|


## References
1. 
