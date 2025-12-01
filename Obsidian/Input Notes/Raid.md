
--- 
Erstellt: 2025-01-31    13:13 
Tags: 
Link Up: 
Link Down:

--- 
## RAID 0

- Keine Datenredundanz
- Beim Ausfall einer Festplatte sind die Daten unbrauchbar
- Parallele Schreib- und Lesezugriffe => Hohe Transferrate
- Nettokapazität = 100%
- Hohe Verfügbarkeit

![RAID 0 Image](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil1/systemintegration/raid/RAID_0.svg)  
[Wikipedia Commons](https://commons.wikimedia.org/wiki/File:RAID_0.svg)

## RAID 1

- Volle Redundanz
- Daten werden gespiegelt gespeichert
- Parallele Lesezugriffe => Lesegeschwindigkeit hoch
- Nettokapazität = 50%
- Die Anzahl der Festplatten, die Ausfallen dürfen, hängt von der Anzahl der Festplatten und der Position dieser ab
- Der Anteil des nutzbaren Speicherplatzes sinkt stark

![RAID 1 Image](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil1/systemintegration/raid/RAID_1.svg)  
[Wikipedia Commons](https://commons.wikimedia.org/wiki/File:RAID_1.svg)

## RAID 5

- Striping Verfahren
- Parity Verfahren
- Datenredundanz
- Lesegeschwindigkeit sehr hoch (Ermöglicht durch das Striping Verfahren)
- Schreibgeschwindigkeit leicht verringert (Durch die Berechnung der Parity-Parts)
- Minimum drei Festplatten
- Die Nettokapazität verringert sich immer um eine Festplatte => Je mehr Festplatten desto besser die Effizienz
- Hohe Verfügbarkeit
- Relativ großer Nettospeicherplatz

![RAID 5 Image](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil1/systemintegration/raid/RAID_5.svg)  
[Wikipedia Commons](https://commons.wikimedia.org/wiki/File:RAID_5.svg)

## RAID 6

- Minimum vier Festplatten
- Ähnlich zu RAID 5
- Besitzt zwei Parity-Parts
- Es können zwei Festplatten ausfallen

![RAID 6 Image](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil1/systemintegration/raid/RAID_6.svg)  
[Wikipedia Commons](https://commons.wikimedia.org/wiki/File:RAID_6.svg)

## RAID 10

- Kombination aus RAID 1 und RAID 0
- Versuch die Stärken der beiden Systeme zu vereinen

![RAID 10 Image](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil1/systemintegration/raid/RAID_10.svg)
## Erklärungsvideos

### RAID einfach erklärt
https://youtu.be/WzWUChLeGBc
### RAID 6 erklärt
https://youtu.be/0H2nvtuY8cg
### RAID 10 erklärt
https://youtu.be/Lw76leQOUdg

## References
1. 
