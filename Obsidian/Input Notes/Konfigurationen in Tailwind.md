
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









## References
1. [Themes in Tailwind](https://tailwindcss.com/docs/theme)
