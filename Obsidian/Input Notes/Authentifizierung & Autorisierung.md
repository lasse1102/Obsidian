
--- 
Erstellt: 2025-10-29    13:33 
Tags: 
Link Up: [[IT-Sicherheit]]
Link Down:

--- 
**Themencluster:**
- **Authentifizierung (Wer?):**
    - Sichere **Passwortspeicherung** (Mittel: **Hashing mit Salt**).
    - Verfahren: **2FA/MFA**, **Single-Sign-On (SSO)**.
    - Wissen: Das Protokoll **OAuth2** (kam oft in Prüfungen vor).
- **Autorisierung (Was darf?):**
    - Konzept: **Rollenbasierte Zugriffskontrolle (RBAC)**.


# Passwortspeicherung mit Hashing
Hashing ist ein **Einwegprozess**, bei dem eine Eingabe (das Passwort) durch eine **Hash-Funktion** in eine Zeichenkette **fester Länge** (den **Hashwert** oder **Digest**) umgewandelt wird.

- **Einweg:** Der Hashwert kann **sehr einfach** aus dem Passwort berechnet werden, aber es ist **mathematisch extrem schwer** (praktisch unmöglich), das ursprüngliche Passwort aus dem Hashwert zurückzurechnen.
- **Kollisionssicherheit (idealerweise):** Zwei unterschiedliche Passwörter sollten **nicht** denselben Hashwert ergeben.
- **Deterministisch:** Dasselbe Passwort ergibt **immer** denselben Hashwert.


## 💾 Passwortspeicherung
Beim Speichern von Passwörtern in einer Datenbank geht man wie folgt vor:
1. Ein Nutzer gibt sein Passwort (P) ein.
2. Bevor das Passwort in der Datenbank gespeichert wird, wird es durch eine kryptografische Hash-Funktion (H) geschickt.
3. Der **Hashwert** (H(P)) wird in der Datenbank gespeichert – **niemals** das Klartext-Passwort (P).

Wenn sich der Nutzer später anmeldet:
1. Der Nutzer gibt erneut sein Passwort (P′) ein.
2. Das System berechnet den Hashwert des eingegebenen Passworts: H(P′).
3. Das System **vergleicht** H(P′) mit dem in der Datenbank gespeicherten Hashwert H(P).
4. Sind beide Hashwerte identisch, ist das eingegebene Passwort korrekt.

---
## 🔒 Zwei-Faktor-Authentifizierung (2FA) / Multi-Faktor-Authentifizierung (MFA)
**2FA/MFA** ist eine Methode zur **Identitätsprüfung**, die eine deutlich höhere Sicherheit bietet als nur die Verwendung eines Passworts. Anstatt sich nur mit einem Faktor (dem Passwort) anzumelden, muss der Nutzer **zwei oder mehr** verschiedene Faktoren bereitstellen, um Zugriff zu erhalten.

### ❓ Die drei Faktoren
Die Faktoren stammen typischerweise aus drei Kategorien:
1. **Wissen** (_Something you know_): Ein **Passwort** oder eine **PIN**.
2. **Besitz** (_Something you have_): Ein **physisches Gerät** wie ein Smartphone (für eine Authenticator-App oder SMS-Code) oder ein Hardware-Token (z.B. YubiKey).
3. **Inhärenz** (_Something you are_): Ein **biometrisches Merkmal** wie Fingerabdruck, Gesichtsscan oder Iris-Scan.
    

### ⚙️ Funktionsweise
Bei der **2FA** werden **zwei unterschiedliche** Faktoren kombiniert (z.B. Passwort + Code vom Smartphone).
- Ein typisches Beispiel ist das Login mit **Passwort** (Wissen) und einem **sechsstelligen Code** aus einer Authenticator-App (Besitz).

### 🛡️ Sicherheitsgewinn
Selbst wenn ein Angreifer das Passwort (Faktor 1) stiehlt, benötigt er immer noch Zugriff auf den zweiten Faktor (z.B. das Smartphone des Nutzers), um sich anmelden zu können. Dies macht den unbefugten Zugriff **wesentlich schwieriger**.

---

## 🔑 Single-Sign-On (SSO)
**Single-Sign-On (SSO)** ist ein **Authentifizierungsverfahren**, das es einem Nutzer ermöglicht, sich mit **einer einzigen Anmeldeinformation** bei **mehreren, voneinander unabhängigen Anwendungen** und Diensten anzumelden. Es dient primär dem **Komfort** und der **Benutzerfreundlichkeit**, steigert aber auch die **Sicherheit**, da Nutzer nicht Dutzende Passwörter verwalten müssen.

### 🌐 Anwendungsgebiete
SSO wird häufig in Unternehmensnetzwerken, aber auch bei großen Webdiensten eingesetzt (z.B. Anmeldung bei Dutzenden von Drittanbieter-Websites mit dem Google- oder Facebook-Konto).

### 🛠️ Funktionsweise (vereinfacht)
1. Der Nutzer versucht, auf eine Anwendung (**Service Provider**) zuzugreifen.
2. Die Anwendung leitet den Nutzer an einen zentralen **Identitätsanbieter (Identity Provider, IdP)** weiter (z.B. Azure AD, Okta, oder der zentrale Server eines Unternehmens).
3. Der Nutzer meldet sich **einmalig** beim IdP an (mit Benutzername und Passwort).
4. Der IdP erstellt nach erfolgreicher Anmeldung einen **Token** (eine digitale Bestätigung der Identität).
5. Der Nutzer wird mit diesem Token zurück zur ursprünglichen Anwendung (Service Provider) geleitet.
6. Die Anwendung **vertraut** dem IdP und gewährt dem Nutzer **Zugriff**, ohne dass er sich dort separat anmelden muss.

### ⚖️ Vorteile

- **Komfort:** Nur ein Passwort muss gemerkt werden.
- **Sicherheit:** Ermöglicht es Unternehmen, **stärkere Passwörter** und MFA/2FA **zentral** zu erzwingen, da es nur eine Anmeldestelle gibt.
- **Effizienz:** Reduziert die Anfragen an den Helpdesk, da seltener Passwörter vergessen werden.

---

## 🔑 Was ist OAuth 2.0?
**OAuth 2.0** (**Open Authorization**) ist ein **Autorisierungs-Framework** (oft fälschlicherweise als Protokoll bezeichnet), das es einer Anwendung (dem **Client**) ermöglicht, in Ihrem Namen auf geschützte Ressourcen zuzugreifen, **ohne** dass Sie der Anwendung Ihr Passwort geben müssen.

Es geht **nicht** um **Authentifizierung** (Wer bist du?), sondern um **Autorisierung** (Was darf diese Anwendung in deinem Namen tun?).

### 💡 Ein Beispiel zur Veranschaulichung
Stellen Sie sich vor, Sie möchten, dass eine Fotobearbeitungs-App (der **Client**) Ihre Bilder von Google Fotos (der **Ressourcen-Server**) abrufen kann, um sie zu bearbeiten:

- **Ohne OAuth:** Sie müssten der App Ihr Google-Passwort geben. Sie hätte dann vollen Zugriff auf _alle_ Ihre Google-Dienste (E-Mails, Kalender, Drive usw.).
- **Mit OAuth:** Sie geben der App **kein** Passwort. Stattdessen erhalten Sie von Google ein **Access Token** (ein Zugangsschlüssel), der **nur** die Berechtigung hat, Bilder zu lesen, und der **jederzeit** widerrufen werden kann.

---

## ⚙️ Die Hauptakteure

OAuth 2.0 definiert vier Hauptrollen im Autorisierungsprozess:
- **Ressource Owner (Ressourcen-Eigentümer):** Die Person, die die Daten besitzt (z.B. Sie, der Nutzer).
- **Client (Anwendung):** Die Anwendung, die Zugriff auf die geschützten Ressourcen benötigt (z.B. die Fotobearbeitungs-App).
- **Resource Server (Ressourcen-Server):** Der Server, der die geschützten Ressourcen hostet (z.B. Google Fotos API).
- **Authorization Server (Autorisierungs-Server):** Der Server, der die Identität des Besitzers bestätigt und Access Tokens ausstellt (z.B. der Google Login-Dienst).

---

## 🔄 Der Ablauf (Authorization Code Grant Flow)

Der am häufigsten verwendete und sicherste Ablauf (Flow) ist der **Authorization Code Grant Flow**:

1. **Anfrage:** Der **Client** (App) leitet den **Ressource Owner** (Nutzer) zum **Authorization Server** (Google Login) weiter und teilt ihm mit, welche Berechtigungen (**Scopes**) er benötigt.
2. **Authentifizierung & Zustimmung:** Der **Nutzer** meldet sich **direkt** beim **Authorization Server** an und stimmt zu, der App die angefragten Berechtigungen zu erteilen.
3. **Autorisierungscode:** Der **Authorization Server** sendet einen **temporären Autorisierungscode** an den **Client** zurück.
4. **Token-Anfrage:** Der **Client** sendet diesen Code zusammen mit seiner geheimen **Client Secret** an den **Authorization Server**.
5. **Access Token:** Der **Authorization Server** prüft die Anmeldeinformationen des Clients und tauscht den Code gegen ein **Access Token** (Zugangsschlüssel) aus.
6. **Zugriff:** Der **Client** verwendet das **Access Token**, um **direkt** beim **Resource Server** (Google Fotos) die Daten anzufordern. Das Access Token gewährt **nur** die zuvor erteilten Berechtigungen.

### 🛡️ Sicherheit durch Tokens
Das Access Token hat typischerweise eine **kurze Gültigkeitsdauer** und gewährt **keinen** Zugriff auf das Nutzerpasswort. Sollte das Token gestohlen werden, kann es nach kurzer Zeit nicht mehr verwendet werden.
## References
1. 
