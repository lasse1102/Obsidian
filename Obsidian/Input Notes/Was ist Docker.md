
--- 
Erstellt: 2025-04-03    07:16 
Tags: #Programming/Docker 
Link Up: [[Docker]]
Link Down:

--- 
# Was ist Docker 
Stell dir vor, du hast eine Anwendung, die auf deinem Computer perfekt läuft. Aber wenn du sie auf dem Computer eines Freundes oder auf einem Server installierst, funktioniert sie nicht mehr richtig. Das liegt daran, dass verschiedene Computer unterschiedliche Umgebungen haben (z.B verschieden Betriebssysteme, Bibliotheken usw.).
Hier kommt Docker ins Spiel:

**Was Docker macht (einfach erklärt)**
1. **Verpacken:**
	- Docker nimmt deine Anwendung und alle ihre Abhängigkeiten (alles, was sie zum Laufen braucht) und packt sie in eine Art „Box“ namens Container.
	- Diese Box enthält alles, was die Anwendung benötigt, um überall gleich zu funktionieren.
2. Transportieren:
	- Diese Container sind sehr leicht und portabel. Du kannst sie einfach von einem Computer zum anderen transportieren
3. Ausführen:
	- Egel auf welchem Computer du den Container öffnest, die Anwendung darin läuft immer gleich, weil sei alles hat, was sie braucht.

**Warum das gut ist:**
- **Immer gleich:**
    - Deine Anwendung läuft immer gleich, egal wo du sie ausführst.
- **Einfach zu transportieren:**
    - Du kannst deine Anwendung einfach von einem Computer zum anderen verschieben.
- **Spart Ressourcen:**
    - Docker-Container sind sehr leicht und verbrauchen weniger Ressourcen als [[Entwicklungssysteme#Virtuelle Maschinen (VMs)|virtuelle Maschinen]].
- **Schnell:**
    - Docker container lassen sich sehr schnell starten.

### Docker Images
##### Grundlagen
- Docker-Images sind wie Vorlagen, aus denen Container erstellt werden. Sie enthalten alle Anweisungen, die zum Ausführen einer Anwendung erforderlich sind.
- Images bestehen aus Schichten(Layer), was sie sehr effizient macht. Wenn du ein Image änderst, werden nur die geänderten Schichten neu erstellt.
##### Dockerfiles
- Dockerfiles sind Textdateien, die Anweisungen zum Erstellen eines Docker-Images enthalten. Sie beschreiben, welche Betriebssystembasis verwendet wird, welche [[Software]] installiert werden muss und wie die Anwendung konfiguriert wird.
- Das Erstellen von Dockerfiles ist ein Kernbestandteil der Docker-Nutzung.
##### Docker Hub
- Docker Hub ist ein öffentliche Registry, in der Docker-Images gespeichert und geteilt werden. Du kannst Images von dort herunterladen und deine eigenen hochladen.

![[1_3ds-PdxGGMN-ZzJH95_lsA.png]]
## Unterschiede und Vorteile von Docker vs. VMs

| Merkmal                           | Docker-Container                              | Virtuelle Maschinen (VMs)                      |
| --------------------------------- | --------------------------------------------- | ---------------------------------------------- |
| **Speicherbedarf**                | Gering (MB)                                   | Hoch (GB)                                      |
| **Boot-Zeit**                     | Sehr schnell                                  | Langsam                                        |
| **[[Betriebssystem]]**            | Teilt Host-OS                                 | Eigenes OS pro VM                              |
| **Ressourcennutzung**             | Effizient                                     | Mehr Overhead                                  |
| **Anzahl ausführbarer Instanzen** | Viele Container möglich                       | Begrenzte Anzahl wegen Ressourcenverbrauch     |
| **Einsatz auf Edge-Devices**      | Ja, möglich (z. B. Raspberry Pi)              | Meist nicht praktikabel                        |
| **Isolation**                     | Prozess-Isolation                             | Volle Isolation (stärker gesichert)            |
| **Flexibilität**                  | Portabel und leicht                           | Weniger flexibel                               |
| **Verwendungsszenario**           | Ideal für Microservices, schnelle Deployments | Gut für monolithische Apps und Legacy-Software |
|                                   |                                               |                                                |

## References
1. 
