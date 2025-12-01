
--- 
Erstellt: 2025-03-17    20:40 
Tags: #Programming/versionskontrolle
Link Up: [[Programming]]
Link Down:

--- 
# Versionsverwaltung mit Git
**Git** ist eine **Versionsverwaltungssoftware**, die es erlaubt, Änderungen in Dateien zu **verfolgen und aufzuzeichnen**. Es ermöglicht, **alte** Versionen des Projekts **wiederherzustellen**, verschiedene Versionen zu **vergleichen** und Änderungen zwischen mehreren Entwicklern **zusammenzuführen**. Dies wird auch als **Versionskontrolle** bezeichnet.

Auch wenn man Git alleine nutzt bietet es einige wichtige Vorteile:
- Jede Änderung am code nachvollziehbar gespeichert
- jederzeit zu einer früheren Version zurückkehren
- Code ist sicher gespeichert
- uvm.

## Speicherung von Code in Repositories
Der Kern von Git ist die Arbeit mit Repositories. In einem Repository liegt immer eine aktuelle Version des Softwarecodes sowie die Historie der Veränderungen. In der Praxis wird auch häufig abgekürzt von einem Repo gesprochen.

Es gibt 2 Arten von Repositories:
1. Ein lokales Repository liegt nur auf deinem Computer. Es ist nur für dich zugänglich
2. Ein remote Repository ist ein Online-Speicher, auf den du und deine Teamkollegen Zugriff haben. Es ist eine Kopie deines lokalen Repositories.

Du kannst dich **entscheiden**, ob du **nur ein lokales** oder **beide Arten** von Repositories verwenden willst. Das **lokale Repository** eignet sich nur, wenn du **alleine an einem [[Projekt]]** arbeitest. Sobald du mit **anderen Leuten zusammen arbeitest** oder du **dein Projekt vor einer Löschung sichern willst**, solltest du **sowohl ein lokales als auch ein remote Repository** wählen.

Nach der Installation von Git kann man man ein lokales Repository erstellen. Wenn man ein remote Repository erstellen will, dann muss man sich bei einem Dienstleister registrieren, welcher den Online-Speicher zur Verfügung stellt. Gängige Anbieter sind GitHub, GitLab.

## Änderungen in Repositories festhalten
Die vorgenommenen Änderungen sind noch in **keinem Repository** sichtbar. Sie sind zunächst einmal in deinem **Working Directory** gespeichert. Du musst aktiv entscheiden, welche Änderungen in das lokale Repository aufgenommen werden sollen.

Sobald du die Änderungen **ausgewählt** hast, überführst du sie in das lokale Repository. Die Überführung wird als **(lokaler) Commit**  bezeichnet.

Verwendest du auch ein **remote Repository**, kannst du deine **lokalen Commits** in dieses überführen. Der Vorgang wird als **Push** bezeichnet.

## Branches mit Git
Implementiert ein Entwickler **ein neues Feature**, ist es üblich, dass er dafür **einen neuen Branch** erstellt (Entwicklungszweige). All deine **Commits werden auf diesem Branch** durchgeführt, **bis du dich dafür entscheidest**, alle **Änderungen auf einmal** in den **Hauptentwicklungszweig** zu implementieren.

Der Hauptbranch eines Repos wird als **master-Branch** bezeichnet. Er wird automatisch **zusammen mit dem Repository** erstellt, d.h. sowohl das lokale als auch das remote Repository haben einen master-Branch. Der Branch, den du eigens für die Implementierung eines Features erstellst, wird als **Feature Branch** bezeichnet.

## Einfaches Zusammenarbeiten
Es kann mal passieren dass 2 Entwickler an der gleichen Datei arbeiten und beide dann ihre Commits machen, dann kann es zu Konflikten führen. Git erkennt solche Konflikte direkt und hilft einem dabei diese relativ einfach zu lösen.


# Die Grundlagen der Git Bash Kommandozeile

![[Pasted image 20250318113357.png]]
- vorm @ steht der Benutzername von Windows
- nach dem @ steht der Name des Systems (Computer)
- MINGW64 -> so heißt die Bash 
- ~ -> sagt aus das wir uns gerade im Benutzerverzeichnis befinden

**pwd** (print working directory)
- gibt den Ordner aus in dem wir uns aktuell befinden
---
**cd** (change directory)
- man schreibt das Verzeichnis hin in das man navigieren will
	- man muss nicht das komplette Verzeichnis angeboten, es reicht wenn man dies von den Punkt man an dem man gerade in der Bash ist 
- mit nur cd kommt man wieder ins Benutzerverzeichnis 
---
**cd ..**
- nutzt man wenn man ein Verzeichnis zurück gehen will
- also in das übergeordnete Verzeichnis
---
**clear**
- löscht den Inhalt der Konsole
---
**ls**
- können wir den Inhalt des aktuellen Ordners ausgeben lassen
---
**mv** (move)
- mit mv kann man Elemente verschieben oder umbenennen  ![[Pasted image 20250318114808.png]]
In den Beispiel wird Einkaufsliste.txt in das unter Verzeichnis "Weiterer Ordner" verschoben
- **Wichtig:** der \ sagt aus, dass es nach "Weiterer" noch mehr kommt. Ohne das \ würde er das in den Ordner "Weiterer" packen und nicht in "Weiterer Ordner". Der Backslash muss immer verwendet werden unabhängig von den Verwendung

**Beispiel 2** (hoch verschieben)
![[Pasted image 20250318115408.png]]
- verschiebt die Datei wieder ins über Verzeichnis

**Beispiel 3** (umbenennen)
![[Pasted image 20250318115608.png]]
- Hier wurde die Einkaufsliste.txt umbenannt zu Shoppinglist.txt
---
**rm** (remove)
- entfernt elemente
- **Vorsichtig sein mit diesem Befehl**
---
**mkdir** (make directory)
- hiermit kann man einen neuen Ordner erstellen
---


# Repository erstellen
Hierzu gehen wir in die git Bash.
1. Wir navigieren in das Verzeichnis, aus dem wir ein Repository machen wollen
2. sind wir in den Verzeichnis angekommen führen wir den Befehle "git init" aus
---
**Status prüfen**
![[Pasted image 20250318121151.png]]

## References
1. https://simpleclub.com/lessons/fachinformatikerin-versionsverwaltung-mit-git
