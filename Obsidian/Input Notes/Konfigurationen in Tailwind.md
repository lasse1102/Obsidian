
--- 
Erstellt: 2025-12-03    14:05 
Tags: 
Link Up: 
Link Down:

--- 
In früheren Versionen (älter als Version 4 ) wurden die Tailwind Konfigurationen in der `tailwind.config.ts` erstellt. Mit der Version 4.0 wurde die tailwind.config abgeschafft und man schreibt alles in eine **globale Klassen, meist die index.css**.

##### Plugins
Wenn man Plugins in Tailwind importieren will, um neue Funktionen zu nutzen, macht man dies durch das Keyword `@plugin ...` und dann das jeweilige Plugin. Dies fügt man am Anfang der globalen Klasse ein.

Beliebte Plugins sind zum Beispiel:
- **daisyUI**: Eine beliebte Komponenten-Bibliothek, die auf Tailwind CSS aufbaut und viele vorgefertigte UI-Komponenten hinzufügt.
- **tailwindcss-animate**: Ermöglicht die Nutzung von Animations-Klassen.
- **tailwind-scrollbar-hide**: Fügt Utility-Klassen hinzu, um Scrollbalken auszublenden.
- **tailwindcss-opentype**: Aktiviert OpenType-Funktionen für Tailwind CSS.

---
##### Prefix
Um ein Prefix zu setzten für seine Utility Klassen, setzt man am Anfang der Globalen Klasse hinter den Tailwind Import den Prefix fest:
- ``@import "tailwindcss" prefix(tw-)``

**Wann verwendet man ein Prefix**
Es wird genutzt um Konflikte aus anderen CSS-Klassen zu vermeiden:
- alte Klassen könnten zufällig gleich heißen wie in Tailwind-Klassen
- Themes/Plugins nutzen teils ähnliche Utility-Klassen

---
##### Themes
Themes sind sinnvoll, wenn man **Design-Tokens** (z.B. Primärfarben, Sekundärfarben, Schriftarten) in einem Projekt definieren will und diese über verschieden Zustände hinweg **dynamisch ändern** möchte.
Die Design Tokens werden für die Generierung von Utility-Klassen verwendet. Sie werden direkt in  CSS mithilfe von CSS-Variablen und der @theme defininiert.
- `@theme`-Direktive
	- Du nutzt `@theme`, um dein Design-System zu definieren — Tailwind generiert daraus automatisch Utility-Klassen, die dein UI konsistent und leicht wartbar machen.
	- Zum Beispiel: Durch die Definition von `--color-primary: #aab9ff;` innerhalb eines `@theme`-Blocks wird automatisch eine Utility-Klasse wie `text-primary` oder `bg-primary` generiert, die den Wert dieser Variable verwendet.
	- Eine CSS Variable ist wie folgt aufgebaut: `–KATEGORIE-NAME-WERT`. 
	

**Wann verwendet man @themes**
- **Multi-Theme-Strategien** (Z.B. Dark Mode): Das ist der häufigste Anwendungsfall. Man definiert Standardwerte in der `:root` Ebene (oder im @theme-Block) und überschreibt diese Variablen dann in einem spezifischen Selektor, z.B. `.dark`. 
- **Marken- oder Kunden-Theming:** Wenn Sie eine Anwendung für verschiedene Kunden mit unterschiedlichen Branding-Farben erstellen. Jeder Kunde bekommt seine eigene Klasse (z.B. `.theme-kunde-a`), die die Theme-Variablen überschreibt.
- **Run-Time-Anpassungen:** Da die Werte als CSS-Variablen vorliegen, können sie leicht über JavaScript zur Laufzeit ausgelesen oder geändert werden, was bei traditionellen statischen Utility-Klassen nicht ohne Weiteres möglich ist.


**Verwendung Beispiele**
	![[Pasted image 20251204085757.png]]

###### Erklärung 
Die Variablen innerhalb des `@theme`-Blocks sind **CSS-Variablen** (Custom Properties), die Tailwind in Utility-Klassen umwandelt. Das Namensschema ist hier entscheidend.

| Tailwind CSS Variable   | Was es tut                                                                                    | Generierte Utility-Klassen                                                              |
| ----------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| **`--color-NAME-WERT`** | Fügt/Ändert die Farbe `NAME` mit dem Helligkeitswert `WERT` hinzu (z.B. `--color-brand-500`). | `bg-brand-500`, `text-brand-500`, `border-brand-500`                                    |
| **`--font-NAME`**       | Fügt die Schriftart `NAME` hinzu oder überschreibt eine Standard-Schriftart.                  | `font-NAME` (z.B. `font-display`)                                                       |
| **`--spacing`**         | Überschreibt die **Basis-Einheit** für alle Abstands-Utilities (`m-`, `p-`, `space-` etc.).   | Beeinflusst alle Spacing Utilities (z.B. `m-4`, `p-2`).                                 |
| **`--breakpoint-SM`**   | Überschreibt den Wert für einen bestimmten **Breakpoint** (z.B. `SM`, `MD`, `LG`).            | Beeinflusst alle Responsive-Utilities (z.B. `sm:text-center`).                          |
| **`--*: initial`**      | Überschreibt **alle** Standardwerte in einer Kategorie (hier für alle Color-Utilities).       | Löscht die gesamte Standard-Farbpalette, sodass nur deine eigenen Farben übrig bleiben. |

**Warum @themes anstatt :root**
Mit @themes erstellen wird automatisch Utility-Klassen für die CSS-Eigenschaften. Wodurch wir diese dann wie ganz normales Tailwind in HTML einbinden können. Das ist der größte Vorteil.
Mit :root könnten wir nur CSS-Variablen definieren, welche wir dann in Tailwind Funktionen oder CSS-Klassen verwenden können oder halt explizit das Design vom Root ändern.
**Mehr dazu aber unten im Abschnitt Root**

---
##### @layer base, components, utilities
Hiermit können wir eigene CSS-Regeln in die richtige Tailwind Schicht (Layer) einordnen. Dadurch stellen wir sicher das Styles korrekt priorisiert werden und nicht "zufällig" überschrieben werden.

**Reihenfolge der Layer**
1. **base**: dies ist die niedrigste Ebene (body, Überschriften, Formular-Defaults)
2. **components**: Wiederverwendbare Komponenten (Buttons, Cards etc.)
3. **utilities**: hat die höchste Priorität und wird nach components und base geladen

Tailwind sorgt dafür dass:
- eigene CSS Regeln richtig einsortiert werden
- sie in der richtigen Reihenfolge geladen werden
- @apply korrekt funktioniert

**Utilities**
Diese können ebenfalls mit dem @utilities definiert werden. Alle benutzerdefinierten Utilities werden automatisch im @layer utilities eingebaut.

---
##### @apply
Dies ist sinnvoll wenn wir Code haben bzw. Design welches sich mehrfach wiederholt. Zum Beispiel. eine Liste von Projekten über Cards, welche alle das gleiche Design haben.
Dann können wir mit @apply Tailwind Utilities direkt in CSS verwenden und sie beispielsweise in einer Klasse einfügen:
![[Pasted image 20251205001637.png]]
Nun können wir einfach für jedes Card die Klasse `btn-primary` verwenden.

> Bei Nutzung von React, kommt @apply eher weniger zum Einsatz, da React schon darauf basiert Komponenten zu bauen die sich mehrfach wiederholen. Da erstellen wir in der Regel von Grund auf nur ein "Bauplan" der Komponente mit deren Design.


---
##### Keyframes
Mit keyframes kann man kurz gesagt Animationen definieren in CSS.
Man sagt den Browser damit, wie sich ein Element über die Zeit verändern wird (z.B. Farbe, Position, Größe, Rotation ...)
**Beispiel:**
- Bei 0% → Element ist transparent
- Bei 50% → Element ist halb sichtbar  
- Bei 100% → Element ist vollständig sichtbar
![[Pasted image 20251205103905.png]]
Animation verwenden
![[Pasted image 20251205103928.png]]
-> Die .box Klasse wird in einer Sekunde von unsichtbar zu sichbar


**Aufbau**
Ein Keyframe besteht aus den folgenden 3 Blöcken.
- einen Namen (z.B. `fadeIn`, `spin`, `slideUp`)
- Schritten, die durch Prozenteingaben markiert sind (0% bis 100%)
- CSS-Eigenschaft, die sich am jeweiligen Schritt ändert.
Man kann beliebig viele Schritte definieren

---
##### Theme Inline


----
##### :root 
:root ist der oberste Knoten im CSS, also der ganz oben stehende Eltern-Selector, der für die gesamte Webseite gilt.
- Im :root kann ich CSS Variablen definieren, welche ich dann in anderen CSS Klassen oder Tailwind Funktionen verwenden kann
- Im :root kann ich auch direkt Styles setzten und explizit das Root Verzeichnis ansprechen (z.B. Schriftart, Hintergrund Padding ...)

Variablen definieren**
![[Pasted image 20251205135331.png]]
-> Hier wird nicht direkt das Design verändert
-> hier werden nur variablen definiert die später verwendet werden

**Design direkt ändern**
![[Pasted image 20251205135432.png]]
-> das macht die komplette Hintergrundfarbe schwarz
-> Und der Text der Seite wird weiß


---







## References
1. [Themes in Tailwind](https://tailwindcss.com/docs/theme)
