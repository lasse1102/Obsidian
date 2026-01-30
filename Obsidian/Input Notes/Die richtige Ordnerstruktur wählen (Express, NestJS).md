
--- 
Erstellt: 2026-01-30    11:37 
Tags: 
Link Up: [[TypeScript]]
Link Down:

--- 
> Vorab ich muss mich auf 1-2 Konzepte festlegen die ich durchziehe, um mit den Strukturen Vertraut zu werden.

In diesen Beitrag geht es darum, was alles beachtet werden muss bei der Wahl der richtigen Ordnerstruktur und was für welche Anwendungen sinnvoller ist.

Vorab lässt sich sagen das es keine "richtige" Ordnerstruktur gibt, da die Wahl stark von **der Größe des Projektes** und den verwendeten Frameworks (wie Express oder NestJS) abhängt.

### Die gängigsten Ordnerstrukturen
1. **Schichtenarchitektur (MVC/Layered):** Dies ist das klassische Modell, das besonders für **kleine bis mittelgroße Projekte** empfohlen wird. Hierbei sortierst du deinen Code nach technischen Aufgaben in Ordner wie `controllers/`, `services/`, `models/` und `routes/`. Ein Vorteil ist die schnelle Auffindbarkeit: Du weißt sofort, dass alle Datenbank-Schemata im Ordner `models/` liegen.

2. **Feature-basierte Struktur (Modular):** Dieser Ansatz wird für **große und komplexe Anwendungen** empfohlen. Anstatt nach technischer Funktion zu trennen, schneidest du die Anwendung nach Geschäftsbereichen (z. B. `auth/`, `users/`, `products/`). In jedem dieser Ordner befinden sich dann alle zugehörigen Controller, Services und Modelle, was die kognitive Belastung verringert, da logisch zusammengehöriger Code physisch nah beieinander liegt.

Zwischen diesen beiden Ansätzen lässt sich im großen und ganzen unterscheiden. Und nach dem werde ich auch immer meine Projekte aufbauen.

---

### Wann entscheide ich mich für welchen Ansatz
Kriterien:
1. **Projektgröße und Komplexität:** Für einen einfachen Prototyp oder eine kleine CRUD-App reicht eine flache oder einfache Schichtenarchitektur aus. Wenn die Anwendung jedoch viele Geschäftsregeln und hunderte Endpunkte umfasst, ist eine modulare Struktur besser geeignet, um die Wartbarkeit zu gewährleisten
2. **Wahl des Frameworks:** **Express** bietet maximale Flexibilität, was für Anfänger Freiheit bedeutet, aber auch das Risiko einer inkonsistenten Codebasis birgt. **NestJS** hingegen ist „voreingenommen“ (opinionated) und erzwingt eine modulare, strukturierte Architektur durch eingebaute Konzepte wie Module und Dependency Injection

---
### Best Practices für Einsteiger
**Unabhängig vom Muster gibt es wichtige Grundregeln:**
- **Trennung von Belangen:** Packe deine Geschäftslogik niemals direkt in die API-Routen. Nutze stattdessen einen **Service-Layer**, der die eigentliche Logik enthält, während der Controller nur die Anfrage entgegennimmt und die Antwort formatiert.
- **Konfiguration isolieren:** Speichere sensible Daten wie API-Keys oder Datenbank-Zugangsdaten niemals hartkodiert im Code, sondern in einer `.env`-Datei und bündele den Zugriff darauf in einem zentralen `config/`-Ordner.
- **Vermeidung technischer Fallstricke:**
	- **Tiefe der Ordner:** Begrenze die Verschachtelung deiner Ordner auf drei bis vier Ebenen, um die Übersichtlichkeit zu behalten.
	- **Explizite Benennung:** Verwende aussagekräftige Namen für Dateien und Variablen (z. B. `user.controller.ts`), um die Lesbarkeit zu erhöhen.

---
# Beispiel Aufbau für Featured-Based Folder Structure
src/
├── components/         # Global shared components (Button, Input)
├── config/             # Global configurations
├── hooks/              # Global hooks
├── lib/                # Shared utilities/third-party setup
├── types/              # Global TypeScript types
│
├── features/           # <--- Feature-Based Modules
│   ├── auth/
│   │   ├── api/        # Auth-specific API requests
│   │   ├── components/ # Auth-specific components (LoginForm)
│   │   ├── hooks/      # useAuth hook
│   │   ├── types/      # auth.types.ts
│   │   └── index.ts    # Public API for the feature
│   └── posts/
│       ├── api/
│       ├── components/
│       └── ...
│
└── pages/              # Routes/Pages assembling features











## References
1. https://alexkondov.com/tao-of-node/#structure-coding-practices
