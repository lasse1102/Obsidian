
--- 
Erstellt: 2025-10-13    10:31 
Tags: 
Link Up: [[AP2]]
Link Down:

--- 
<mark style="background: #FFF3A3A6;">Verschlüsselung bezieht sich auf die Schutzziele Vertraulichkeit und Integrität</mark>
**Inhalt der Notiz:**
- **Verschlüsselung:** Unterschiede zwischen **Symmetrisch** (z.B. AES) und **Asymmetrisch** (z.B. RSA).
- **Anwendung:** **Hybride Verschlüsselung** (z.B. in **TLS/SSL/HTTPS**).
- **Zertifikate & PKI:** Zweck der Zertifikate zur Authentifizierung und zum Schlüsselaustausch.
- **Integritätsschutz:** **Hashing** (zur Überprüfung), **[[Digitale Signatur]]**.
- **Schwachstellen:** **Ende-zu-Ende-Verschlüsselung** (Risiken vs. Nutzen).

# symmetrische Verschlüsselung
Bei der symmetrischen Verschlüsselung, verwendet man im Gegensatz zur asymmetrischen Verschlüsselung nur einen Schlüssel zum Verschlüsseln und Entschlüsseln. Man unterscheiden die symmetrischen Verschlüsselungsverfahren nach Blockchiffre-basierten Verfahren und Stromchiffren.

**Steps:**
1. **Schlüsselerzeugung und -austausch:**
    - Zuerst muss ein **starker, geheimer Schlüssel** erzeugt werden (z. B. 128 oder 256 Bit).
    - Dieser Schlüssel muss **sicher** zwischen dem Sender und dem Empfänger **ausgetauscht** werden, da nur Personen, die den Schlüssel besitzen, die Nachricht ver- oder entschlüsseln können. Dies ist der kritischste Punkt der symmetrischen Verschlüsselung (das **Schlüsselaustauschproblem**).
2. **Verschlüsselung:**
    - Der Sender nimmt den **Klartext** (die ursprüngliche Nachricht).
    - Mithilfe des **geheimen Schlüssels** und eines **symmetrischen Verschlüsselungsalgorithmus** (wie z. B. **AES - Advanced Encryption Standard**) wird der Klartext in einen **Geheimtext** (auch Chiffretext genannt) umgewandelt.
3. **Übertragung:**
    - Der Geheimtext wird über einen (auch unsicheren) Kanal an den Empfänger gesendet. Selbst wenn die Nachricht abgefangen wird, ist sie ohne den Schlüssel unlesbar.
4.  **Entschlüsselung:**
    - Der Empfänger erhält den Geheimtext.
    - Mithilfe **desselben geheimen Schlüssels** und des zugehörigen **Entschlüsselungsalgorithmus** wandelt der Empfänger den Geheimtext wieder in den ursprünglichen **Klartext** um.

# asymmetrische Verschlüsselung
Jeder Teilnehmer, der sicher kommunizieren möchte, erzeugt ein **Schlüsselpaar** :

1. **Öffentlicher Schlüssel (Public Key):**  
    - Dieser Schlüssel dient dazu, **Daten zu verschlüsseln** oder digitale Signaturen zu verifizieren.    
    - Er kann **frei verteilt** und an jeden weitergegeben werden.    
    - _Analogie:_ Wie ein offenes Vorhängeschloss, das jeder benutzen kann, um eine Nachricht einzuschließen. 
2. **Privater Schlüssel (Private Key):**
    - Dieser Schlüssel dient dazu, **Daten zu entschlüsseln** oder digitale Signaturen zu erstellen.
    - Er muss **unbedingt geheim** gehalten werden, da nur sein Besitzer damit die verschlüsselten Nachrichten entschlüsseln kann.
    - _Analogie:_ Wie der einzige Schlüssel, der das Vorhängeschloss wieder öffnen kann.

#### Der Verschlüsselungsprozess
Wenn Sender **A** eine geheime Nachricht an Empfänger **B** senden möchte.
1. **A** besorgt sich den **öffentlichen Schlüssel** von **B**.
2. **A** verschlüsselt die Nachricht mit **B's öffentlichem Schlüssel**.
3. Die verschlüsselte Nachricht wird an **B** gesendet.
4. **B** kann die Nachricht nur mit **seinem privaten Schlüssel** entschlüsseln und lesen.

Selbst wenn ein Angreifer den öffentlichen Schlüssel von B kennt und die verschlüsselte Nachricht abfängt, kann er sie nicht entschlüsseln, da ihm B's privater Schlüssel fehlt.

**Vorteile:**
- Der größte Vorteil der asymmetrischen Verschlüsselung ist, das sie das Probelm des **sicheren Schlüsselaustauschs** der symmetrischen Verschlüsselung löst.
- Ermöglicht digitale Signaturen und somit Authentizität 
**Nachteile:**
- Deutlich langsamer als symmetrische Verschlüsselungsverfahren
- Höhere Komplexität und größerer Rechenaufwand durch die zugrunde liegendenden komplexen mathematischen Probleme


# Aufgaben
![[Pasted image 20251029113727.png]]



![[Pasted image 20251029113814.png]]
## References
1. [[16 - Verschlüsselung]] 
