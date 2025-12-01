
--- 
Erstellt: 2024-04-11    09:05 
Tags: 
Link Up: [[Dashboard]]
Link Down:

--- 
Anders als bei PHP Frameworks üblich haben wir uns gegen die zentralen Servicecontainer entschieden. Das Problem damit ist, dass dann alle Klassen (von denen es hunderte gibt) gewisse Abhängigkeiten zum Framework und dessen Art der Abarbeitung haben. Möchte man das Framework wechseln (oder muss wie im Falle von Silex welches nicht mehr supportet wird), so müsste ein Großteil der Codebasis umgeschrieben werden.

Bei uns ist das nicht notwendig. Alle unsere Service und Modellklassen sind POPOs (Plain Old PHP Objects) oder POPIs (Plain Old PHP Interfaces)....ja ich weiß :-)

Der IDE Support ist daher perfekt und Migration aus anderen Systemen einfacher.

Alle Service Klassen werden in der Bootstrap.php definiert und bilden dort einen Abhängigkeitsbaum mit den wichtigsten und essentiellsten Services oben, und den darauf Aufbauenden weiter unten.

# Basis Services & Utility Klassen

Hier ein Auszug über wichtige Basis Services und Utitlity Klassen im Projekt. Diese werden recht häufig verwendet und erleichtern einem sehr die Arbeit.

## Helpers

Die Helpers-Klasse ist die am meisten verwendete Klasse im Projekt. Sie beinhaltet sinnvolle Funktionen im System die wir häufig benötigen. Ganz allgemein aber auch relevant für Datenbankabfragen oder Logistikspezifische Dinge.

Sie ist selbst in mehrere Dateien über Traits gesplittet, welche eigene Aufgaben haben.

  

### Parser

Ist für das Parsen von ungetypten Werten oder Strings in getypte Werte zuständig. Dabei können Werte als Nullable geparsed werden ( TYP|null ) oder forciert werden (werfen eine Exception wenn das Parsen nicht klappt). Neben unbestimmten Eingangstypen gibt es auch Versionen für [[Assoziative Array]] (speziell hilfreich bei Datenbankabfragen mit FetchType:Named oder der Silex Requestklasse, bei denen POST und GET Parameter aus dem HTTP Request per Name extrahiert werden können. Der zusätzliche Vorteil dabei: Es werden nette übersetzte Fehlermeldungen generiert.

  

Folgende Typen unterstützt der Parser:
- Strings
- Int's
- Floats
- Boolean (mit "yes/no", "1/0", "true/false", "on/off" String Interpretationen)  
    
- DateTime (mit und ohne Uhrzeit oder auch nur Uhrzeit, auch unter Angabe eines speziellen Formats)
- UUIDs (Mit UUIDInterface der Ramsey Bibliothek. Werden bei all unseren neuen Datenbankfeldern benutzt statt AutoIncrement)
- JsonArrays (bei entsprechenden Postgres Columns nützlich)

### Country

Eine Länderdatenbank die wir sehr häufig für Logistikprozesse verwenden. Die beinhaltet auch Funktionen zur Bestimmung ob es sich bei einem Land um ein EU oder Drittland handelt. Des weiteren gibt es einen Parser für "Countries.*" des Versandprogramms, Umrechnungen in verschiedene ISO Standards und Mapping von englischen Namen der Länder in die entsprechenden ISO2 Codes.  

### Translator

Beinhaltet die trans und transChoice Funktionen aus Silex / Symfony. Siehe [https://symfony.com/doc/4.1/components/translation/usage.html](https://symfony.com/doc/4.1/components/translation/usage.html)  

Mehr dazu unter _**Übersetzungen.**_

### Logger

Beinhaltet Funktionen zum Loggen in der Hauptlog Datei. Weitere Nutzung und verschiedene Logarten sind unter _**Logging**_ erklärt  

### Database

Einige Funktionen zum einfachen Updaten, Inserten und Upserten in Datenbanken vom Typ Postgres und MySQL. Soll irgendwann mal durch eine spezielle Connection ersetzt werden, die das automatisch kann, sodass man nicht versehentlich die falsche Funktion verwendet. Bei Postgres werden die Bezeichner dabei automatisch gequotet (da Postgres standardmäßig alles lower-case macht). Des weiteren gibt es eine Errorhandler Funktion die fehlerhafte Statements in Exceptions umwandelt.

### Media

Übersetzt Dateiendungen in Media Types (Mime Types) und umgekehrt. Sehr hilfreich bei Ausgabe von Dateien über HTTP (Downloads).

### Weiteres

Die Helpersklasse enthält auch noch weitere Funktionen direkt in den Helpers. Eine davon ist die isDev() / isProd() Abfrage. Diese sind Zentral um bestimmte Funktionen für ein Environment auszuschalten. Beispielweise können keine Dokumente ins Habel über den DEV geschickt werden, weil die Funktion mit isProd() überprüft, ob sich der Aufruf im Scharf System ereignet.  

## OKCrypto

Nutzt die Defacto Standard Defuse/Crypto Library zum generieren von API Token und ver- und entschlüsseln von Daten. Wird derzeit für die Middleware <-> Portal Kommunikation eingesetzt, welche neben der Transportverschlüsselung bis zum Relais (api.okmedia.de) alle Nachrichten und Token zusätzlich Public-Private-Key verschlüsselt.

Die Token die dort generiert werden, werden von Nutzern zur Authentifizierung für das Portal (Mandanten und Lieferanten), sowie auch Endkunden unserer Mandanten (Retouren Portal) als Ersatz für [[Sessions]] genutzt. Im Retourenportal werden die Daten allerdings gecached um einen DDoS Schutz zu implementieren. Mehr dazu in der Dokumentation des Retourenportals.  

Diese Library könnte auch einmal für unsere eingehenden REST und SOAP Schnittstellen genutzt werden. Außerdem wäre eine Umstellung des Security Providers denkbar, sodass wir auch hier eher so etwas wie JWTs (Json Web Token) benutzen anstatt lakale [[Sessions]] zu verwenden.

# Übersicht der Services

Neben den Kernservices haben wir eine Menge Services die wir hier für Logistik und das Drum Herum brauchen. Diese sollen hier alle mal kurz vorgestellt werden. Bei Bedarf muss diese Sektion dann erweitert oder umfangreicherere Dokumentation ausgelagert werden.  

  

## ActionLog

  

## Address

  

## ClientBilling

  

## ClientPortal

  

## DataRemoval

  

## DeviceManager

  

## EmailImport

## References
1. 

## Quellen
1. 