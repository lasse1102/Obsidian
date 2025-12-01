
--- 
Erstellt: 2024-05-07    14:41 
Tags: #School/LF02/Verkabelung
Link Up: [[Verkabelung]]
Link Down:

--- 
Unter einer Netzwerk-Topologie versteht man die typische Anordnung und physikalische Verbindung von Geräten in einem Netzwerk. Geräte sind Hosts, wie Clients und Server, die das Netzwerk aktiv nutzen. Dazu zählen auch Netzwerk-Komponenten, wie Switche und Router, die eine Verteilfunktion haben und dafür sorgen, dass alle Netzwerk-Teilnehmer miteinander eine logische Verbindung eingehen können.

# Point to Point
- Besteht nur zwischen 2 Hosts eine einfache und direkt Verbindung
- Beide Geräte können diese Verbindung für die gegenseitige Kommunikation verwenden

# Bus Topologie
- Alle Geräte sind an ein zentrales Kabel, den Bus angeschlossen. 
- Nachrichten werden über den Bus gesendet und von allen Geräten empfangen aber nur das vorgesehene Gerät verarbeitet die Daten
- Bei Ausfall eines Gerätes kann es zum Ausfall des Netztwerkes kommen

# Ring Topologie
- Jedes Gerät hat genau 2 Nachbarn zum Senden und Empfangen von Nachrichten
- Bei jeden Gerät kommt somit ein Kabel an und geht somit auch eins ab

# Stern Topologie
- Alle Geräte sind direkt mit einem zentralen Knotenpunkt, häufig einen Switch oder Hub, verbunden
- Der Hub oder Switch übernimmt die Verteilerfunktion für die Datenpakete
- Host können jederzeit hinzugefügt und entfernt werden
- Relativ teure und aufwendige Topologie

# Baum Topologie
- Diese Variante ist eine Variation der Stern-Topologie und wird für größere Netzwerke verwendet


| Topologie                                   | Beschreibung                                                                                                                                                                                                                                                                                                                 | Schaubild                                          |
| ------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------- |
| **Stern (Star)**                            | Von einem Sternmittelpunkt aus gehen sternförmig die Leitungen zu den Endpunkten. Zugriffssteuerung CSMA/CD.                                                                                                                                                                                                                 | ![Stern Bild](stern.png)                         |
| **Erweiterter Stern (Extended Star)**       | Der Endpunkt eines Sterns ist wiederum Mittelpunkt eines weiteren Sterns. Üblich sind bei LANs drei Ebenen. Standard in heutigen Verkabelungen.                                                                                                                                                                              | ![Erweiterter Stern Bild](stern_erweitert.png)   |
| **Vollständige Masche (Complete Mesh)**     | Jede Station ist mit jeder anderen verbunden. Sehr hohe Ausfallsicherheit durch sehr hohe Redundanz, aber sehr aufwendig.                                                                                                                                                                                                    | ![Vollständige Masche Bild](masche_voll.png)     |
| **Unvollständige Masche (Incomplete Mesh)** | Alle wichtigen Stationen sind mehrfach mit anderen Stationen verbunden. Ausfallsichere Netze durch Redundanz. Ein erweiterter Stern mit Querverbindungen ergibt eine unvollständige Masche.                                                                                                                                  | ![Unvollständige Masche Bild](masche_unvoll.png) |
| **Zelle (Cell)**                            | Funkzellen decken bestimmte Bereiche mit Funkwellen ab, z.B. WLAN, Bluetooth oder Mobilfunk. Zugriffssteuerung CSMA/CA.                                                                                                                                                                                                      | ![Zelle Bild](zelle.png)                         |
| **Punkt-zu-Punkt (Point-to-Point, P2P)**    | Verbindung zwischen zwei Stationen.                                                                                                                                                                                                                                                                                          | ![Punkt-zu-Punkt Bild](p2p.png)                  |
| **Bus**                                     | Alle Stationen sind parallel auf einer gemeinsamen Leitung. Heute nicht mehr üblich in LANs. Zugriffssteuerung CSMA/CD.                                                                                                                                                                                                      | ![Bus Bild](bus.png)                             |
| **Ring**                                    | Jede Station hat eine Vorgängerstation und eine Nachfolgerstation. Daten werden nur in eine Richtung verschickt. Vorteile sind sichere Datenübertragung und berechenbare Wartezeit, bis gesendet werden darf. Nachteile sind ein schwieriger Aufbau und eine komplizierte Fehlersuche. Zugriffssteuerung über Token Passing. | ![Ring Bild](ring.png)                           |


## References
1. 

## Quellen
1. [Wikipedia](<https://de.wikipedia.org/wiki/Topologie_(Rechnernetz)>)