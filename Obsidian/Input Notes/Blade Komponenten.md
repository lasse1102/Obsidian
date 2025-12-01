
--- 
Erstellt: 2025-04-17    10:30 
Tags: #Programming/PHP/Frameworks/Laravel 
Link Up: [[Laravel]] 
Link Down:

--- 
## 🧩 Was sind Blade-Komponenten?

Blade-Komponenten sind **wiederverwendbare Bausteine**, die dir helfen, HTML-Strukturen (z. B. Buttons, Karten, Navigationen) einmal zu definieren und dann **mehrfach sauber** einzusetzen.

Statt HTML + Tailwind-Klassen jedes Mal neu zu schreiben, machst du dir eine Komponente und nutzt sie immer wieder – mit **Variablen (Props)** und **flexiblen Inhalten (Slots)**.

---

## 📌 Beispiel für eine Blade-Komponente: `NavLink`
```PHP
<!-- resources/views/components/nav-link.blade.php -->
@props(['active' => false])

<a 
  class="{{ $active ? 'bg-gray-900 text-white' : 'text-gray-300 hover:bg-gray-700 hover:text-white' }} rounded-md px-3 py-2 text-sm font-medium"
  {{ $attributes }}
>
  {{ $slot }}
</a>
```

# 📦 Erklärung der einzelnen Teile
✅ `@props([...])`
```PHP
@props(['active' => false])
```
**Was macht das?**
- Definiert **"Eigenschaften" (Props)**, die du der Komponente mitgeben kannst – ähnlich wie Funktionsparameter.
- `active` ist hier eine Variable mit dem Standardwert `false`.
- Du kannst später beim Verwenden der Komponente `:active="true"` setzen oder es weglassen.

**Wofür ist das gut?**
Damit du in der Komponente bestimmte Dinge anpassen kannst – zum Beispiel:
- Style ändern
- Verhalten definieren (z. B. aktiv / inaktiv)
- Icons anzeigen oder nicht
- usw.

### ✅ `{{ $attributes }}`

```PHP
<a ... {{ $attributes }}>
```
**Was macht das?**
- Das ist ein **Platzhalter für alle zusätzlichen HTML-Attribute**, die du beim Verwenden der Komponente übergibst.
    
- Wenn du `href="/"` oder `target="_blank"` beim Aufruf der Komponente angibst, wird das hier automatisch eingefügt.

**Beispiel:**
```PHP
<x-nav-link href="/" target="_blank">Home</x-nav-link>
```
→ wird zu:
```PHP
<a href="/" target="_blank" class="...">Home</a>
```

### ✅ `{{ $slot }}`
```PHP
{{ $slot }}
```
**Was macht das?**

- Gibt den **Inhalt zwischen den Komponenten-Tags** wieder.

**Beispiel:**
```PHP
<x-nav-link href="/">Home</x-nav-link>
```
→ `Home` ist der Inhalt, und das landet als `{{ $slot }}` in der Komponente → also zwischen dem `<a>`-Tag.

## 🧠 Zusammenspiel

Wenn du das Ganze verwendest wie:
```PHP
<x-nav-link href="/" :active="request()->is('/')">Home</x-nav-link>
```

passiert Folgendes:

| `href="/"`      | Geht über `{{ $attributes }}` direkt ins `<a>`-Tag                     |
| --------------- | ---------------------------------------------------------------------- |
| `:active="..."` | Wird als **Prop** gesetzt, also `@props(['active' => false])` → `true` |
| `Home`          | Wird als **Slot** genutzt, kommt also in `{{ $slot }}`                 |















## References
1. 
