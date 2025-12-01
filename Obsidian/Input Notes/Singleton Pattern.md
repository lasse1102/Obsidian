
--- 
Erstellt: 2025-10-09    11:51 
Tags: 
Link Up: [[Design Patterns]]
Link Down:

--- 
## Das Singleton Design Pattern in der Softwareentwicklung

Das Singleton Design Pattern ist ein bewährtes Konzept in der Softwareentwicklung, das beispielsweise in JavaScript verwendet werden kann, um sicherzustellen, dass nur eine Instanz einer Klasse existiert und auf diese zugegriffen werden kann. Dieses Muster ist besonders nützlich in Situationen, in denen Sie sicherstellen müssen, dass eine Ressource oder ein Dienst global und nur einmal verfügbar ist.

## Wie funktioniert das Singleton Pattern?

Im Singleton Pattern wird sichergestellt, dass nur eine Instanz einer Klasse erstellt wird, und alle weiteren Anforderungen nach einer Instanz verweisen auf die bereits vorhandene Instanz. Dies ist nützlich, um Ressourcen zu teilen und sicherzustellen, dass Zustände und Daten konsistent bleiben.

## Praxisbeispiel
![[Pasted image 20251009120354.png]]
Zusammenfassung:
- **Einmalige Initialisierung:** Die Konsolenausgabe "Konfigurationsmanager initalisiert (Nur einmal) erscheint nur beim allerersten Aufruf von `getInstance()`
- Alle Teile der Anwendung greifen über `ConfigManger.getInstance()` auf **dieselbe, konsistente Konfiguration zu.
- **Kontrollierter Zugriff:** Der private Konstruktor verhindert, dass Entwickler versehentlich neue Konfigurationsobjekte erstellen, was zu widersprüchlichen Anwendungseinstellungen führen würde

## References
1. 
