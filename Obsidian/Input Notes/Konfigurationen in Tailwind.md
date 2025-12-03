
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
	- Definiert die **Design-Tokens** für alle Utility-Klassen. Es ist die zentrale Stelle, um Basis-Farben, Abstände, Schriftarten usw. als CSS-Variable zu registrieren.
	- Zum Beispiel: Durch die Definition von `--color-primary: #aab9ff;` innerhalb eines `@theme`-Blocks wird automatisch eine Utility-Klasse wie `text-primary` oder `bg-primary` generiert, die den Wert dieser Variable verwendet.
	- Die Variablen folgen einer Namenskonvention (Namespaces) wie `--color-*`, `--font-*`, `--spacing-*`, etc., um Tailwind mitzuteilen, für welche Art von Utility-Klasse sie gelten.
- CSS-Variablen (Custom Properies)
	- Die tatsächlichen Werte(z.B. Hex-Codes für Farben) werden in nativen CSS-Variablen (`--var-name`) gespeichert.
	- Der große Vorteil: Diese Variablen sind **zur Laufzeit** (Runtime) im Browser verfügbar und können einfach mit reinem CSS überschrieben oder geändert werden, um Themes zu wechseln.

**Wann verwendet man @themes**
- **Multi-Theme-Strategien** (Z.B. Dark Mode): Das ist der häufigste Anwendungsfall. Man definiert Standardwerte in der `:root` Ebene (oder im @theme-Block) und überschreibt diese Variablen dann in einem spezifischen Selektor, z.B. `.dark`. 
- **Marken- oder Kunden-Theming:** Wenn Sie eine Anwendung für verschiedene Kunden mit unterschiedlichen Branding-Farben erstellen. Jeder Kunde bekommt seine eigene Klasse (z.B. `.theme-kunde-a`), die die Theme-Variablen überschreibt.
- **Run-Time-Anpassungen:** Da die Werte als CSS-Variablen vorliegen, können sie leicht über JavaScript zur Laufzeit ausgelesen oder geändert werden, was bei traditionellen statischen Utility-Klassen nicht ohne Weiteres möglich ist.

**Verwendung**
1. Definition der Tokens
	Verwende `@theme` in der Globalen CSS Datei, um die Basiswerte der Design-Tokens als CSS-Variable festzulegen.
	![[Pasted image 20251203160937.png]]







## References
1. [Themes in Tailwind](https://tailwindcss.com/docs/theme)
