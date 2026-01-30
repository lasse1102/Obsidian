
--- 
Erstellt: 2026-01-26    17:58 
Tags: 
Link Up: 
Link Down:

--- 
# AI-Powered Code Auditor
- Ein Tool, welches sich automatisch in den ein GitLab Projekt einklinkt, um entsprechendes Feedback zu geben (wie ein Senior Entwickler).
- Es soll nicht nur prüfen ob im Code Syntax Fehler vorkommen (wie ESLint), sondern soll die Logik/Architektur und Sicherheit prüfen

##### Tools die verwendet werden.
1. **Ein Listener:** Also ein NodeJS Server, der via Webhook benachrichtig, ob ein neuer Request eingetroffen ist.
2. **Ein Analyzer**: Anstatt direkt mehrere Tausend Zeilen Code an beispielsweise ChatGPT zu schicken, wird mittels eines AST (Abstracted Syntax Tree) der Code in mehrere teile extrahiert.
3. **AI-Engine** Ein Modul, dass den Code und den Kontext an ein LLM sendet und strukturierte Verbesserungsvorschläge zurücksendet.

---









## References
1. 
