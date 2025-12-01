
--- 
Erstellt: 2025-03-04    13:49 
Tags: 
Link Up: 
Link Down:

--- 
## Prozessmanagement
### Grundlagen
- **Prozessdefinition:** Ein Prozess ist ein laufendes Programm.
- **Programmdefinition:** Ein Programm ist eine ausführbare Anwendung.
- **Unterschied:** Ein Programm kann mehrere gleichzeitig laufende Prozesse haben (z.B. mehrere Browserfenster).
- **Ressourcenverwaltung:** Prozesse benötigen Computerressourcen wie [[RAM]] und [[CPU]].
- **Kernel-Rolle:** Der [[Komponenten eines Betriebssystem#Kernel-Funktionen|Kernel]] verwaltet Ressourcen, um mehrere Prozesse gleichzeitig auszuführen.

### Prozessplanung
- **Multitasking:** Der [[Komponenten eines Betriebssystem#Kernel-Funktionen|Kernel]] muss mehrere Prozesse gleichzeitig verwalten.
- **Zeitscheiben (Time Slices):**
    - Die CPU führt Prozesse nacheinander in kurzen Zeitintervallen aus.
    - Diese Intervalle sind so kurz, dass sie für den Benutzer als gleichzeitige Ausführung erscheinen.
    - Der Kernel verwaltet diese Time Slices und bestimmte welcher Prozess als nächstes von der CPU ausgeführt wird
- **CPU-Auslastung:**
    - Hohe CPU-Auslastung kann durch übermäßige Zeitscheibenbelegung eines Prozesses oder durch zu viele Prozesse verursacht werden.
    - Wenn ein Prozess zu viele Zeitscheiben bekommt, werden andere Prozesse vernachlässigt.
- **Manuelle Eingriffe:** In manchen Fällen ist ein manuelles Eingreifen erforderlich, um Prozesse zu verwalten.

### Prozesslebenszyklus
- **Prozesserstellung:** Der [[Komponenten eines Betriebssystem#Kernel-Funktionen|Kernel]] erstellt Prozesse, wenn Programme ausgeführt werden.
- **Prozessplanung:** Der Kernel plant die Ausführung von Prozessen.
- **Prozessbeendigung:** Der Kernel verwaltet die Beendigung von Prozessen und gibt Ressourcen frei.
    - Freigabe von Ressourcen: Beendete Prozesse geben ihre Ressourcen wieder frei, damit diese anderen Prozessen zugewiesen werden können.

## References
1. 
