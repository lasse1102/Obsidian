
--- 
Erstellt: 2025-01-06    10:25 
Tags: #School/LF07/Linux #aufgabe 
Link Up: [[Linux]] 
Link Down:

--- 
# Basic Linux Befehle
1.      Mit welcher Tastenkombination kann man einen Prozess abbrechen?
	- STRG + C

2.      Was macht Strg+D?
	- Es beendet das Programm und schließt das Terminal

3.      Ich möchte mehr über den Befehl "cowsay" erfahren.
	1. Was kann ich dafür in der Kommandozeile eingeben?
		- man cowsay -> um das Benutzerhandbuch zu öffnen
		- cowsay - -help -> zeigt eine komplette Ansicht der verfügbaren Optionen an
		- 
	2. Wie kann ich das Manual wieder verlassen?
		- Mit „q“ verlässt man es

4. Finden Sie die entsprechenden Tastenkürzel und notieren Sie sich diese
	1. kopieren und einfüfen (ohne Maus)
		- Strg + Umschalt + C  = kopieren
		- Strg + Umschalt + V = einfügen
	2. leert den Bildschirm
		- Strg + L
	3.  Autocompletion
		- Tab
	4. zuletzt Benutze Befehle
		- Pfeil nach oben
5.  Wie sieht die Struktur eines Kommandos aus? Unterscheiden Sie in diesem Zusammenhang die Fachbegriffe -option und -argument!
		Kommando -option -argument
	- Option: kann das Verhalten eines Befehls ändern
	- Argument: sind Daten oder Ziele die auf einen Befehl angewendet werden

6. Was passiert, wenn ich ls -IShR eingebe?
	- l : lange Listenansicht
	- s : sortiert die Dateien nach Größe
	- h : zeigt es in menschenlesbaren Format
	- r : Inhalte werden rekursiv aufgelistet

7. Es sollen alle Dateien im aktuellen Verzeichnis, inklusive versteckter Dateien, sortiert nach letztem Änderungszeitpunkt ausgegeben werden. Welcher Befehlt tut dies nicht?
	1. ls -t -a -all
	2. ls -a --sort=time = falsch
	3. ls --sort=TIME --a = falsch
	4. ls --all --sort=time = falsch
	5. ls -t --all

8. Beim Aufruf von ls wurden u.a. folgende Dateien angezeigt:
	- text.txt
	- .bild.png
	- .dokument.txt
	- foto.png
	
	Mit welcher Option muss ls hier aufgerufen worden sein?
	-  mit ls -a


## References
1. 
