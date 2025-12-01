
--- 
Erstellt: 2024-06-27    13:54 
Tags: #Programming/Scala/Allgemeines
Link Up: [[Scala]]
Link Down:

--- 
sbt steht für "Scala Build Tool" oder auch "Simple Build Tool". Es ist ein open Source Build Tool, welches für Java und besonders für Scala entwickelt wurde. 
- sbt ist vergleichbar mit dem composer in [[PHP]]

# Hauptfunktionen
**Es ermöglicht dir, deine Abhängigkeiten zu verwalten, die Scala oder Java Datein zu kompilieren, auszuführen und zu verteilen**

- Verwaltung von Abhängigkeiten
	Es gibt eine Konfigurationsdatei, in der alle alle Abhängigkeiten enthalten sind. Hier kann man die Abhängigkeiten verwalten und die Versionen angeben. 
	Die Abhängigkeiten werden von einem Online-Bibliotheksrepository wie [Maven Central](https://central.sonatype.com/?smo=true) heruntergeladen
	
- Kompilieren
	Als erstes lädt SBT die Informationen aus der Konfigurationsdatei herunter
	Dann verwendet es das Compiler-System von Scala, um dein Programm in **Bytecode-Dateien** zu kompilieren


- Ausführen von Tests
	**SBT** bietet eine Lösung, um deinen Code mit dem Befehl `sbt test` zu testen, der alle Tests des Projekts ausführt. Mit `sbt testOnly` kannst du eine bestimmte Klasse testen oder auch die Tests einer Datei. Vergiss nicht, dass du mit Unit-Tests viel Zeit sparen kannst.

Genauere Informationen hier: [SBT in Scala](https://datascientest.com/de/sbt-in-scala)



## References
1. 
