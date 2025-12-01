
--- 
Erstellt: 2025-02-17    09:58 
Tags: #IT/Hardware
Link Up: [[IT]]
Link Down:

--- 
## Computer zusammenbauen: Schritt für Schritt
In dieser Lektion bauen wir einen kompletten Desktop-Computer zusammen. Das Zusammenbauen eines Computers ist eine nützliche Fähigkeit für IT-Support-Spezialisten und kann auch für andere Projekte (Gaming-PCs, Medienserver) eingesetzt werden.

###### **Sicherheitsvorkehrungen (ESD - Elektrostatische Entladung):**
ESD kann elektronische Komponenten beschädigen. Daher ist es wichtig, sich vor dem Anfassen von Komponenten zu erden:

- **Methode 1:** Ein geerdetes, aber nicht eingeschaltetes elektrisches Gerät berühren (z.B. ein an die Steckdose angeschlossenes, aber ausgeschaltetes Netzteil). Dies sollte regelmäßig während des Zusammenbaus wiederholt werden.
- **Methode 2:** Ein antistatisches Armband verwenden. Das Armband wird am Handgelenk befestigt und das Kabel an einem unlackierten Metallteil des Gehäuses befestigt.

[[Komponenten]] werden in antistatischen Beuteln geliefert. Diese sollten erst geöffnet werden, wenn die Komponente tatsächlich eingebaut wird.

###### **Schritt-für-Schritt-Anleitung:**
1. **Motherboard vorbereiten:** Das [[Motherboard]] auf die Abstandshalter im Gehäuse schrauben. Bei einigen Gehäusen sind die Abstandshalter bereits eingebaut.
2. **CPU installieren:**
    - [[CPU]] vorsichtig aus der antistatischen Verpackung nehmen.
    - Die Markierung auf der CPU muss mit der Markierung auf dem CPU-Sockel des Motherboards übereinstimmen.
    - CPU vorsichtig in den Sockel einsetzen und verriegeln. Dabei ist etwas Kraft erforderlich.
3. **Kühlkörper installieren:**
    - Etwas Wärmeleitpaste auf die CPU auftragen (eine kleine Menge reicht). Die Wärmeleitpaste sorgt für eine bessere Wärmeübertragung zwischen CPU und Kühlkörper.
    - Den Kühlkörper auf die CPU setzen und die Schrauben diagonal anziehen, um einen gleichmäßigen Druck zu gewährleisten.
    - Den Lüfter des Kühlkörpers an den entsprechenden Anschluss auf dem Motherboard anschließen.
4. **RAM installieren:**
    - Die DIMM-Slots auf dem Motherboard suchen.
    - Die Kerben am [[RAM]]-Modul müssen mit den Kerben im RAM-Slot übereinstimmen.
    - RAM-Modul in den Slot einsetzen, bis es einrastet. Die seitlichen Halterungen verriegeln das Modul. In der Regel werden die weißen RAM-Slots zuerst bestückt.
5. **SSD/HDD installieren:**
    - SSD/HDD in den entsprechenden Einbauschacht im Gehäuse einsetzen.
    - Das SATA-Kabel mit der SSD/HDD und dem Motherboard verbinden.
6. **Gehäuselüfter installieren:**
    - Den Gehäuselüfter an der vorgesehenen Stelle im Gehäuse anbringen.
    - Den Lüfter an den entsprechenden Anschluss auf dem Motherboard anschließen.
7. **Netzteil installieren:**
    - Das Netzteil in den vorgesehenen Platz im Gehäuse einsetzen und festschrauben.
    - Die Stromkabel des Netzteils mit dem Motherboard (24-Pin-ATX-Stecker und 8-Pin-EPS-Stecker für die CPU) verbinden.
    - Weitere Stromkabel bei Bedarf mit anderen Komponenten (z.B. SSD/HDD) verbinden. Ältere Netzteile haben möglicherweise Molex-Anschlüsse, die über Adapter für SATA-Geräte verwendet werden können.
8. **Gehäusekabel anschließen:**
    - Die Kabel für die Gehäusetasten (Power, Reset) und -LEDs mit den entsprechenden Anschlüssen auf dem Motherboard verbinden.
9. **Grafikkarte installieren:**
    - Die Grafikkarte in den PCIe-Slot auf dem Motherboard einsetzen, bis sie einrastet.
    - Die Grafikkarte am Gehäuse festschrauben.
10. **Gehäuse schließen:** Das Gehäuse schließen.
11. **[[Peripheriegeräte]] anschließen:**
    - Monitor, Tastatur und Maus an den Computer anschließen. In diesem Beispiel wird ein DisplayPort-Kabel für den Monitor verwendet.
12. **Testlauf:**
    - Den Computer einschalten. Die Lüfter sollten sich drehen und das System sollte hochfahren. Ein kurzer Piepton beim Start ist normal.
    - Wenn der Monitor kein Signal empfängt, die Verbindungen überprüfen.
    - Wenn der Computer nicht startet, die [[Stromversorgung]] und die Verbindungen überprüfen.

###### **Fehlerbehebung:**
Wenn der Computer nicht startet, können folgende Punkte überprüft werden:

- Ist das Netzteil richtig angeschlossen und eingeschaltet?
- Sind alle Kabel richtig verbunden?
- Haben alle Komponenten Strom?

Die Meldung "Non-System disk or disk error" bedeutet, dass kein [[Betriebssystem]] auf der Festplatte gefunden wurde. Die Installation des Betriebssystems wird in den nächsten Lektionen behandelt.

## References
1. 
