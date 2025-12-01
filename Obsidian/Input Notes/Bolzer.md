
--- 
Erstellt: 2025-05-13    11:30 
Tags: 
Link Up: 
Link Down:

--- 
# Ideen / Features

1. Tailwind CSS
	Unsere Idee war eine **einfache UI** mit einem **dunklen Design**.. Ja unser Fokus lag auch mehr auf der Funktionalität, deswegen wollten wir nicht ewig an der UI programmieren. Deswegen haben wir uns für klassisches **HTML** und das CSS-Framework **Tailwind CSS** entschieden. Das hat uns echt viel Arbeit abgenommen und das Designen super beschleunigt!
	
	Kurz einmal zu Tailwind CSS. Es ist wie gesagt ein CSS Framework, welches mit vordefinierten Klassen arbeitet, die direkt im HTML Code eingebunden sind. Das spart uns die Zeit eigene CSS Klassen zu schreiben und wir können direkt die von Tailwind nutzen. Auch das einbinden vom Responsive Design ist deutlich leichter als über klassiches CSS dazu komme ich aber gleich nochmal.
	Ich habe hier mal ein CodeSnippet aus unserem Projekt hinzugefügt an dem wir gut erkennen können wir Tailwind funktioniert. Der Code hier ist dafür zuständig die Bundesliga Tabelle zu erstellen.
2. Navigation
	- Ein weiterer Punkt worauf ich kurz eingehen will ist die Navigation. Wir arbeiten auf der Seite mit einer Sidebar um zwischen den Seiten zu wechseln und einer NavigationsBar wo wir zum Beispiel das Profil verwalten können. Beispielsweise in die einstellungen gehen oder das ausloggen. Ja ähm ich habe hier mal die Funktion eingefügt um zu demonstrieren wie das DropDown in der Navigationsleiste funktioniert. Das ganze läuft über JavaScript. Wir holen uns am 
3. Responsive Design
	 Ja wir wollten auch das dass ganze auch auf dem Handy/Tablet usw funktionieren würde, deswegen haben wir uns von anfang an Gedanken gemacht zum Responsive Design, also dass wenn der Bildschirm sich verkleinert dass die Seite sich automatisch anpasst. Und das geht tatsächlich sehr leicht mit Tailwind CSS. Tailwind hat 3 Klassen sm, md und lg, die 3 verschiedene Größen darstellen. Somit konnten wir recht einfach das Responsive Design einbinden.
	Als beispiel sehen wir hier dass standartmäßig flex und flex-col ausgeführt wird. Das heißt das die Elemente untereinander angezeigt werden, wie man hier auch sieht. Und wenn der Bildschirm die größe von md erreicht dann soll er die elemente nebeneinander anordnen, dass sehen wir hier rechts auf dem Bild. 
	Und so ist das eigentlich in der ganzen UI der Fall, überall wo Elemente anders formatiert werden soll, haben wir das so geändert.



Folie 1:
- Einfache UI mit dunklen Design
- Fokus lag mehr auf die Funktionalität, wollten nicht so viel Zeit in die UI stecken vorerst -> Deshalb einfaches HTML und Tailwind CSS
- Tailwind ist ein CSS Framework, vordefinierte Klasse, wird direkt in HTML eingebunden
- CodeSnippet, welches die Bundesliga Tabelle lädt (kurze Erklärung woher das geladen wird), dann auf paar Tailwind Klassen eingehen

Folie 2:
- Wir arbeiten mit einer Sidebar, zum wechseln zwischen den Seiten 
- Und einer NavBar wo wir zum Beispiel unser Profil verwalten können
- CodeSnippet, der demonstriert wie das DropDown Menü funktioniert


Folie 3:
- Sollte auf Handy/Tablet auch laufen, deswegen von anfang an der Gedanke die Seite Responsive zu machen
- Wenn Bildschirm sich verkleinert passen sich die Elemente automatisch an
- Tailwind hat dafür 3 Klassen (sm,md,lg) die dieses sehr einfach machen
- CodeSnippet, standartmäßig flex und flex-col, welches die Elemente untereinander anordnet wie auf dem linken Bild zu sehen. 
	- Wenn größe md erreicht ist, dann flex:row, welches die elemente nebeneinander anordnet
- Diese Tailwind klassen findet man im ganzen HTML code


## References
1. 
