
--- 
Erstellt: 2024-04-11    08:37 
Tags: 
Link Up: [[Dashboard]]
Link Down:

--- 
Im Folgenden soll die grundsätzliche Projektstruktur unserer neuen Middleware dokumentiert werden. Dies soll als allgemeines Nachschlagewerk für Entwicklungen, Debugging und Bugfixing dienen. Spezielle Tools sind nicht Gegenstand dieser Dokumentation sondern vielmehr die Abstraktion des gesammten Projekts.

# Technologie Stack

Hier nehmen wir einmal auf was für die Middleware alles verwendet wird. Sehr häufig setzen wir nämlich auf bestehende Frameworks und Libraries die uns das Leben erleichtern und uns ermöglichen nicht alle grundlegenden Funktionen selbst implementieren zu müssen.  

Da wir hier kein ERP fahren ist das aber natürlich begrenzt.

## Framework

Als Framework kommt Silex zum Einsatz. Dieses wird mittlerweile nicht mehr maintained und supportet und wurde durch den neuen Microframework Ansatz vom dazugehörigen Symfony Projekt verdrängt. Es gibt auch keine richtige Doc mehr online, nur noch die aus dem [archivierten Github Repository](https://github.com/silexphp/Silex/tree/master/doc).

Da Symfony aber sehr auf Service Container und [[Dependency Injection|Dependency Injection]] aufbaut und sehr viel "Indirektion" hat (resultiert in schlecht lesbare StackTraces und Vendor Lock-in), haben wir uns beim Portal Projekt auf "Slim" eingestellt welches sehr ähnlich ist zu Silex. Bei Zeiten werden wir das mal migrieren.  

  

Alle Funktionen der Middleware werden über HTTP Routen ausgeführt. Das gilt nicht nur für Dinge im Frontend, sondern auch im Backend, wie z.B. Cron Tasks. Hierfür werden in Silex und anderen Microframeworks sogenannte **Controller** verwendet. Diese Controller definieren Routen, welche HTTP Pfade darstellen, welche über einen HTTP Request mit der geeigneten Method aufgerufen werden und den Code im Controller ausführen.

ALLE HTTP Requests werden hierbei von einer Datei, der _**/web/index.php,**_ entgegen genommen und dann an den korrekten Controller anhand des Pfades weitergegeben.

  

Die Controller werden in eigenen Klassen definiert, welche zumeist bestimmten Aspekten oder Tools zugeordnet werden. Diese Klassen nennen sich Controller Provider und halten eine zusammengehörende Menge einzelner Controller beisammen, welche sich einen Pfadstamm teilen. Genauerer erklären wir unter _**Controller Provider**_.

  

Neben diesen Controller Providern gibt es einige weitere Dateien, welche im Endeffekt Framework (in diesem Fall Silex) spezifisch sind.  

### src/app.php  

Die _**app.php**_ definiert wichtige Einstellungen und Klassen für die Funktionsweise des Frameworks. Hier befindet sich die Konfiguration aller wichtigen Teile, die nicht erst dynamisch zur Runtime geladen werden sollen.  

Dazu zählen: Laden der Konfigurationsdatei im Verzeichnis htdocs/okconfig, Registierung von Silex Extensions, wie der Twig Templating Engine zum Rendern von HTML Seiten, einen Email Service, den Logger, den Translation Provider, die Datenbanken sowie den Security Kernel und Einstellungen für LDAP und Session Handling.

Diese Datei muss eigentich nur selten angepasst werden. Solche Anpassungen sollten auch immer im Team besprochen werden.

### src/controller.php  

Hängt die Globale $app Variable vom Typ OKApplication an die Bootstrapklasse. Muss nicht angepasst werden.

### src/jobs.php

Diese Datei wird nur vom cron Daemon aufgerufen über die PHP CLI. Minütlich wird dieses Skript aufgerufen, welches dann entscheidet ob ein CRON Eintrag aus der Datei _**src/De/OKMedia/Middleware/Job/MiddlewareJobs.php**_ ausgeführt werden soll. Diese Datei wird dann die entsprechenden Einträge als HTTP Aufrufe ausführen und loggt deren Aufruf in einem speziellen _**cron.log**_.

Der Vorteil hierbei ist, dass alle CRONs die es für die Middleware gibt mit dem Projekt gepflegt werden und es nur noch einen Eintrag in der Host Cron bedarf. Weitere Informationen dazu unter _**Jobs**_.  

### web/index.php

Einstiegspunkt der ganzen Middleware welche durch HTTP erreichbar ist. Muss nicht angepasst werden.

### src/De/OKMedia/Middleware/Bootstrap.php  

Die zentrale Datei welche die Controller und Services "bootstrapt". Im Endeffekt wird der ganze Applikationsbaum über diese Datei aufgebaut. Vorteil: Sehr guter IDE Support, da alle Abhängigkeiten der Klassen als Konstruktorparameter daher kommen. Außerdem ist der Rest des Projekts völlig vom Silex Framework losgelöst. Nachteil: Etwas schlechtere Performance, da diese Struktur nicht gecached werden kann. Ein Fehler in der Bootstrap legt außerdem das ganze System lahm. Glücklicherweise haben wir ein Testsystem und eine gute IDE die dieses Problem minimiert. Mehr dazu im Artikel über das Arbeiten mit der IDE.

### src/De/OKMedia/Middleware/OKApplication.php

Die OKApplication ist eine Erweiterung der Silex / Symfony Application Klasse, welche Systemrelevante Dienste beinhaltet. In ihr werden durch eine Assoziaten-Array-Mechanik spezielle Silex Services gespeichert, die untereinander kommunizieren können. Dazu gehören hauptsächlich Framework-spezifische Dienste wie der Security Provider, der Cache, LDAP Anbindung, Datenbankreferenzen, Logger, Mailer und Übersetzungssystem.

Da dieses Objekt sehr mächtig und eher "Low Level" ist, benutzen wir es zumeist nicht direkt in Service-Klassen, sondern nutzen einige Werte in ihm als Parameter für andere Klassen. Damit haben wir auch eine bessere Kontrolle über die "Capabilities" einer Klasse, sodass der Umfang einer Klasse durch ihre Parameter schon sichtbar wird. Auch die Abstraktion wird besser wenn Klassen nicht "zu viel" können.

### composer.json

Nicht wirklich Framework spezifisch, aber trotzdem anders im Vergleich zu Flat-PHP Dateien. Wir nutzen die PHP Paketverwaltung Composer für unser externes Dependency Management. Alle externen Bibliotheken dieses Projekts (und das sind einige) kommen als Composer Depenedencies und werden vom Composer Programm automatisch heruntergeladen und ins _**/vendor**_ Verzeichnis kopiert.

Zusätzlich dazu kommen unsere Dateien alle ohne "require_once" oder "include" aus, da hier der PSR-4 Standard von PHP greift. Dieser nutzt eine autoloader Datei, welche diese "require" Befehle automatisch ausführt. Damit sind im gesamten Projekt über die korrekten Namespaces und Klassenimporte alle Dateien erreichbar. Ob Projekt- oder externe Dateien, alles.

Dies sorgt dafür das man eine sehr ähnliche Programmiererfahrung hat wie in Java.

## Datenbanken

Alle Datenbanken die wir verwenden, ob direkt zur Middleware zugehörig oder extern eingebundene wie die auf dem 1.38, werden in der okconfig YAML Datei definiert. Instanziert werden diese Datenbanken nicht über die übliche PDO Anbindung von PHP, sondern über eine Abstraktionsschicht (DBAL / Database abstraction layer) namens [[Doctrine DBAL]]. Diese gehört zum sehr großen Symfony Ökosystem und existiert schon seit Jahrzehnten und ist fantastisch dokumentiert. Die Schicht erlaubt neben den Ausführen von SQL Strings jeglicher Form auch automatische Sanitation von Eingaben die SQL Injections verhindern sollen. Darüber hinaus gibt es mit dem [[Query Builder]] auch ein sehr mächtiges Abstraktionswerkzeug das es erlaubt Basisqueries zu definieren und diese an anderer Stelle zu verändern (z.B. anpassbare "select", "where" oder "order by" clauses).

## Template Engine

Das Projekt / Framework ist nach dem MVC (Model - View - Controller) Prinzip aufgebaut. Das Model beschreibt die Datenhaltung in Dateien oder Datenbanken, die Controller und Services, was mit den Daten geschieht und die View ist das Interface mit den diese Daten sichtbar, oder über Formulare editierbar gemacht werden.  
Für jeden Frontend Controller gibt es hierbei passend einen eigenen Pfad mit den Templates drin, analog zu den locales.  
Die Templatesprache ist hierbei nicht PHP, sondern Twig die eine eigene Syntax besitzt. Weitere Informationen unter [Middleware - Templating](http://192.168.3.34/freescout/hc/3237372528/34/middleware-templating).

## Lokalisierung

Die Lokalisierung betrifft bei uns weitestgehend das Übersetzungssystem. Dies wird mit Funktionen in der Helpers Klasse gemacht, trans und transChoice, die jeweils eine String in der Form "controllerPrefix.kategorie1.kategorie2.wert" einnehmen. Die eigentlichen Werte sind in YAML Dateien gespeichert welche hierarchisch in einer Baumstruktur aufgebaut sind und nach der Locale (z.B: de, en) benannt sind.

Obwohl die Translations organisiert nach den ControllerProvidern sind, sind diese im ganzen Projekt verwendbar.  
Derzeit gibt es Dateien für **de** und **en**, da diese beiden Sprachen im Projekt aktiviert sind. Die englischen sind allerdings nicht gefüllt (außer bei den Übersetzungen für die Portale).

Dokumentation für die Übersetzung gibt es bei [Symfony](https://symfony.com/doc/4.1/components/translation/usage.html). Einen algemeinen [CheatSheet für YAML und seinen Syntax bei Quickref](https://quickref.me/yaml).  

# Grundsätzliche Struktur

Hier werden wir über die allgemeine Ordnerstruktur lesen. Wo finden wir was in den Projekten. Neben den "Einspringen" in Controller, durch diese wir vom HTTP Aufruf bis in die letzten Datenbankcalls gelangen können (Ctrl+Click auf Klassen und Funktionen), ist es auch hilfreich zu wissen, wo die Dateien überhaupt zu finden sind.

  

- **/abas**  
    ABAS spezifische Aufrufe. Das sind mehr altlasten und sollten noch einmal überdacht werden, wenn wir eine engere Integration mit dem ABAS eingehen.  
    **/components**  
    Interne Dateien für einige Tools. Nicht weiter wichtig.  
    
- **/locales**  
    Hier finden wir die Übersetzungsdateien im YAML Format. Die Ordner dadrin spiegeln die Aufrufpfade in HTTP wieder, bis zu den ControllerProvidern. In ihnen sind dann alle dort gesammelten Übersetzungen zugeordnet.  
    
- **/logs**  
    Das zentrale Loggingverzeichnis. Dies ist quasi nur das "lokale" Log und nicht gefüllt. Es dient dem Projekt als Template für die logs auf dem DEV und Scharf System. Dort gibt es dann verschiedene Logdateien. Mehr dazu im Artikel [Middleware - Logging](http://192.168.3.34/freescout/hc/3237372528/35/middleware-logging).
- **/res**  
    Intern vom Server genutzte Ressourcen, z.B. fonts, Frachtführerlogos oder Kundenlogos. Auch Lieferscheinlogos würden hier reinkommen.  
    
- **/src**  
    Hier sind alle PHP Quelldateien zu finden die nicht direkt zum Framework gehören, sondern zum Projekt an sich. Alle Dateien befinden sich im Namespace _**De\OKMedia\***_. Im nächsten Absatz gehen wir hier auf die Struktur unserer Codebasis  
    
- **/vendor**  
    Automatisch erzeugte Verzeichnis von composer, dem PHP Build- und Paketmanager. Hier landen unsere externen Dependencies, die wir in der composer.json Datei festlegen und die dann von Composer geupdated und installiert werden. Bei den manuellen Updates muss dieses Verzeichnis im ganzen auf DEV und Scharf deployed werden, ansonsten muss hier nix angerührt werden.  
    Interessant dabei ist auch das einige dieser Bibliotheken auch über das Web aufegerufen werden können, da wir composer auch für JS Libraries benutzen. Weiteres ist unter [Middleware - Arbeiten mit der IDE](http://192.168.3.34/freescout/hc/3237372528/31/middleware-arbeiten-mit-der-ide) beschrieben.  
    
- **/views**  
    Unsere Templatedateien in Twig. Wie weiter oben beschrieben.  
    
- **/web**  
    Das web Verzeichnis ist das was wirklich von außen sichtbar und per HTTP direkt abrufbar ist. Meistens sind hier keine Anpassungen notwendig, nur wenn es generell neue Anforderungen in der UI gibt. Weiteres in Folge.  
    
- **/web/index.php**  
    Der zentrale Einstiegspunkt in die Applikation. Alle Tools der Controller Provider werden quasi als Pfad dahintergehängt und sind somit über von außen erreichbar. Ob für HTTP Schnittstellen oder einfache Browser.  
    
- **/web/notifications.php**  
    Die Benachrichtigungen die oben rechts in der Ecke angezeigt werden, werden über diese Datei gesteuert. Diese lädt aus dem PHP Cache "Moust" aktuelle Benachrichtigungen für den eingeloggten User. Damit nicht der gesamte Bootstrap Mechanismus aktiviert werden muss, machen wir das über eine eigene Datei welche über JS in regelmäßigen Abständen gepollt wird. Dadurch ergibt sich der Effekt einer "Push-Benachrichtigung" durch Poll Mechanik, ohne den normalerweise hohen Performanceoverhead.  
    
- **/web/time.php**  
    Aufgrund regelmäßiger Diskrepanzen zwischen den Zeiten auf den Handgeräten und dem Server, nutzen wir einige eigene Datei für die Ausgabe des Timestamps auf dem Server. Dies brauchen wir für viele Ajax Apps im Zusammenhang mit der Aktionserfassung. Wir müssen bei der Arbeit den Startpunkt einer Aktion uns merken, bevor wir einen Eintrag erstellen können. Statt diesen wie gesagt auf dem Client zu verwenden, nehmen wir die Serverzeit und bekommen bei der Akionserfassung keine Diskrepanzen.
- **/web/css  
    **[[CSS]] Dateien für das Projekt. Auch einige Bootstrap Extensions. Dies sind meistens overrrides und kleinere Extensions für das Bootstrap CSS Framework welches wir benutzen.  
    
- **/web/fonts  
    **Fonts die vom Browser verwendet werden. Dies ist hierbei nur Glyphicons, welches eine font basierte Icon Library ist.  
    
- **/web/img  
    **Bilder die aus dem Web erreichbar sein müssen. Dies ist das OKL Logo oben links in der Ecke, sowie im Order "label" eine Menge an Screenshots die im Wareneingang verwendet werden.  
    
- **/web/js  
    **Ähnlich wie bei [[CSS]]. Hier haben wir noch einige eigene JS Ajax Tools die wir benutzen. Da wir derzeit keine JS Frameworks nutzen, ist das alles etwas chaotisch. Für kleinere JS Skripte und Ajax-Funktionen nutzen wir keine eigenen Dateien, sondern hängen diese meistens direkt in die Templatedateien ein.

# Source Dateien

Wie bereits erwähnt sind alle unsere Projektdateien im Ordner **/src**. Alle projektspezifischen Dateien sind im Namespace _**De\OKMedia\***_.

In unserer Middleware sind die Strukturen zunächst in 3 Teile unterteilt. Darüber hinaus haben wir die RestCurl Klasse, welche derzeit für die BoxLS und Habel API benutzt werden, aber bei Gelegenheit durch die Guzzle PHP Http Library ersetzt werden sollen. Und die Roles Klasse, welche alle vorhanden Rollen im System darstellt. Im Folgenden die 3 Hauptnamespaces im Projekt.  

## API  

Hier finden wir alle externen Schnittstelle, die die Middleware nutzt. Konfiguriert werden diese zum Teil über die okconfig.yml oder über unser Configsystem in der Datenbank. Für Kerndienste nehmen wir die Zentrale YAML Datei, für weniger häufig genutzte eher die aus der config Tabelle in der Middleware Datenbank. Prinzipiell könnte man hier auch alles zu der Datenbank migrieren, was nicht direkt Datenbankzugangsdaten betrifft, aber das ist geschmackssache.

Hier finden wir zum einen Schnittstellen zu Shops und Marketplaces, zum anderen aber auch in andere Systeme bei uns.  

### ClassicDB  

ClassicDB ist die "alte" Middleware auf dem 1.38. Dies ist hauptsächlich eine Datenbankabstraktionsschicht, sprich alle calls laufen über den mySQL Connector. Da wir hier aber sehr viel Modellklassen und auch "Prozesse" verwenden, wie die Middleware Flags, macht es Sinn das als eigene Dependency zu abstrahieren. Alle Services die mit dem 1.38 arbeiten sollen, sollten diese Klasse verwenden.

Im DEV System ist dies die MiddlewareTest Datenbank. Im Scharf System ist dies die Middleware Datenbank.  

### BoxLS

Schnittstelle ins Versandprogramm. Dabei sind sowohl die Nachrichten ins Versandprogramm umgesetzt, als auch die Rückkanäle, wenn dort Aktionen ausgeführt werden und diese die Middleware anrufen. Bei diesen Rückkanälen können dann Klassen registriert werden, welche bestimmte Aktionen hier ausführen, wie z.B. das Abmelden von GOUTs, das Generieren von Lieferscheinen und Labeln bis hin zum Senden von Notifications und eMails.  
Die BoxLS Schnittstelle sollte meistens nicht direkt, sondern über den nützlicheren ShippingOrderService erfolgen. Dieser bindet nämlich neben sinnvollen Prozessen auch die Datenbank des Versandprogramms ein, die wir häufig direkt ansprechen um bessere Performance zu erzielen, als z.B. mit dem getActiveOrders Aufruf.  

### MyWMS

Schnittstelle ins MyWMS. Dies betrifft alle Aufrufe über SOAP. Für alle Prozesse gibt es hier auch wie bei der BoxLS und ClassicDB Schnittstelle eine komplette Modellimplementierung. Auch hier sollte nicht direkt die MyWMS Schnittstelle genutzt werden, sondern lieber der WMSOrderService, welcher auch die Datenbank des MyWMS einbindet. Hierbei sei auch zu sagen, dass alle Systeme und Datenbanken entsprechend ihres Environment angesprochen werden, sprich im DEV sind dies die DEV MyWMS und BoxLS Systeme und Datenbanken, im Scharf sind dies entsprechend die Scharfen MyWMS und BoxLS Systeme und Datenbanken. Dies gilt eigentlich für alles, sofern es von allen Systemen DEV und Scharf Systeme gibt.

### Habel

Habel ist über Rest angebunden. Wir können Dokumente hinzufügen, auch automatisch mit Generierung von TIFFs, oder Dokumente abfragen über eine Suche. Wir nutzen Habel derzeit für das Versenken von Abliefernachweisen, Trackingtabellen und Frachtführer Rechnungen.

Da wir keine Habel Test Instanz haben, ist das Senden von Dokumenten im DEV deaktiviert.

### MiddlewareDB

Enthält Abstraktionen und die Datenbank Connections zur neuen Middleware auf dem 3.34 und 3.35. Es gibt dabei 2 Datenbanken. Eine in Postgres und eine in mySQL, da die Postgres Migration noch nicht abgeschlossen ist. Neue Tools und Tabellen sollen die Postgres Instanz verwenden.  

### WebIO

Das Webrelais zum Verhindern der Scharfschaltung der Alarmanlage. Kann die aktuelle Einstellung (An oder Aus) der beiden Ports lesen und schreiben.

  

## Middleware

Die Hauptdateien für das Middleware Projekt und seine Seiten. Im Gegensatz zu **API** und **Util** ist diese nicht portierbar geplant, sodass die darin enthaltenen Klassen streng zur Middleware zugehörig sind. Auch dieser Namespace ist unterteilt in viele Subbereiche. Zunächst haben wir aber ein paar allgemeine Klassen die im Top Level liegen:

  

- **OKControllerProvider  
    **Einen für uns angepassten SilexController Provider der über dessen eigenarten abstrahiert und die eigentlichen ControllerProvider portabel zu anderen Frameworks macht. Hier legen wir auch die allgemeine Struktur der Routen fest.
- **BackendControllerProvider  
    **Eine spezialisierung des OKControllerProvider. Dieser ist für Backend Routen zuständig (Präfix _**backend/**_) die für bestimmte Tools manuell von der IT aufgerufen werden. Die Berechtigung dieser Routen ist immer **Api** und muss mit einem entsprechenden User ausgeführt werden.  
    Fehler / Exceptions die hier geworfen werden, werden automatisch in unser Fehlersystem eingetragen. Die Fehler werden dann entweder entfernt das nächste mal wenn die Route ohne Fehler aufgerufen wurde, bzw. bleiben bestehen, wenn der Fehler "Sticky" markiert wurde.  
    Der Login dieser Routen läuft nicht über ein Formular, sondern über den HTTP BasicAuth Header. Zum Login kann der Middleware "admin" User aus dem Keepass verwendet werden, oder der "application" User aus dem LDAP (ebenfalls im KeePass zu finden).  
    Auch alle Cron Aufrufe laufen über solche Backend oder Client Controller.  
    
- **ClientControllerProvider**  
    Eine Spezialisierung des BackendControllerProvider. Dieser legt nur als Präfix _**client/{MANDANTENKÜRZEL}**_ fest. Die meisten unserer Mandanten haben einen solchen ClientControllerProvider. Und jeder existiert genau 1x im Projekt.  
    Des weiteren werden Fehler in diesem Controller automatisch einem Mandanten zugeordnet und im Fehlersystem etwas anders gerendert.
- **SupplierControllerProvider**  
    Analog zum ClientControllerProvider, nur das der Supplier für unsere Lieferanten ist, die spezielle Anforderungen haben.  
    Dazu zählen z.B. Amazon, MyToys, SmithToys, Talia etc.  
    
- **FrontendControllerProvider**  
    Eine Spezialisierung des OKControllerProvider für Frontends. Dieser enthält ein paar hilfreiche Funktionen zum ausgeben von Fehlermeldungen in der UI und Anderes. Außerdem werden alle FrontendController in der Übersichtsseite dargestellt. Dies werden wir vermutlich in naher Zukunft ändern, weil es etwas unübersichtlich geworden ist.
- **Bootstrap**  
    Die zentrale Datei, welche die ganze Applikation lädt und den Abhängigkeitsbaum aufspannt. Wenn man wissen will "was es so gibt", schaut man hier rein.

### Backend

Alle Routen die nicht direkt von Usern aus erreichbar sein sollen. Z.B. Cron Tasks oder kleinere Tools, Reperaturskripte oder Ähnliches. Wir versuchen meist keine direkte Logik hier zu verwenden, sondern vielmehr Aufrufe in entsprechenden zu Services machen, die dem Controllern als Dependency mitgegeben werden. Dadurch konzentrieren wir uns bei den Controllern auf die Extraktion von Parametern aus dem Request, dem Errorhandling dafür und das Aufbereiten der Antworten der Serviceklassen, sowie das Rendern der Ausgabe über Templates oder Json Responses.  

### Carrier

Dateien für unsere Frachtführerabstraktion. Besteht aus abstrakten Klassen für bestimmte Aufgaben. Managerklassen die über Frachtführer hinweg arbeiten müssen (z.B. Rechnungsservice aka. CarrierInvoiceService) und deren Modellklassen. In Unterordner finden wir dann Implementierungen zu den Frachtführern. Derzeit sind es meistens irgendwelche Rechnungsklassen welche im zentralen Manager registriert werden (siehe Bootstrap) und dann mit den Manager Funktionen (z.B. Importiere alle Rechnungen aka. importAllInvoices) ausgeführt werden.

Sie haben aber auch eigene Service Klassen, welche verwendet werden um z.B. Tracking Links zu generieren oder Nummern von einem Format in ein anderes umzuwandeln (siehe GLSService).

### Client

Hier ist all der Mandantenspezfische Code der Middleware. Dazu muss man sagen, dass wir gewisse Anforderungen, wie z.B. Schnittstellen und Labels zu Marketplaces, Shops und Lieferanten davon wegabstrahiert haben und dort maximal aufrufen und konfigurieren, aber nicht implementieren. Dadurch sind Anpassungen für Kunden häufig äußerst portabel.

Zu den wichtigen Services hier zählen die StatisticExporter für die Mandantenabrechnung. Diese wurden mandantenseitig getrennt weil hier jeder Sachbearbeiter seine festen Tabellenschemata braucht. Darüberhinaus sind hier auch die Portale definiert. Für die meisten Kunden sind das die Containeravisierung, im Falle von GIO jedoch sehr viel mehr. Und momentan werden ja viele alte Webshops und Auswertungsseiten für die Kunden dorthin migriert.

Auch Einstellungen und Konfigurationen für die Wareneingangs- und Retourenprozesse sind hier zu finden. Wie bereits bei den Frachtführern wird hier das Prinzip der zentralen Managerklasse umgesetzt, die mandantenspezifische Implementationsklassen registriert bekommen, und dann im Falle eines Vorgangs dieses Kunden dann die korrekte Implementierung wählt.

### Config

Ein Kernservice im System der hier etwas höher angesiedelt ist. Dieser wird verwendet um strukturierte Konfigurationsobjekte aus der Middlewaredatenbank zu ziehen, welche nach Namen dort angelegt sind. So haben wir hier z.B. Zugangsdaten für die Webshops von GIO und TPM hinterlegt, sowie die Zugangsdaten zu den Frachtführerrechnungsportalen oder FTP Server.  

### Frontend

Analog zum Backend, allerdings für alle ControllerProvider im Frontend, also der UI mit dem die Mitarbeiter hier arbeiten. Auch hier gilt das Prinzip der Trennung der Angelegenheiten (Seperation of concerns), sodass hier hauptsächlich Parameter-parsing sowie Rendering und Errorhandling betrieben wird.

Speziell sind hierbei die in dem Controllern vergebenen Berechtigungen, welche über die LDAP App* Gruppen auf Userebene umgesetzt werden. Der Security Manager von Silex verhindert hier den Zugriff auf Routen für die keine Berechtigung existiert.

Näheres zum Thema Rendering wird im Artikel [Middleware - Tempating](http://192.168.3.34/freescout/hc/3237372528/34/middleware-templating) beschrieben.

### Job

Hier befindet sich unser Cron Job System, für welches wir eine Cron Library in PHP benutzen, die sowohl die Cron Strings parsed, als auch entscheidet welche Einträge dazu nun passen und ausgeführt werden. In der Datei MiddlewareJobs.php sind alle im System verwendeten Cronjobs aufgelistet. Das Ziel ist das wirklich alles was irgendwie in der Firma bezüglich Crons gemacht werden muss, hier drin mal landet.

  

![](https://freescout.oklog.de/storage/uploads/YFS7UXZirtL2BHsIyf7tT2UKO.png)

  

Die Jobs bestehen aus einem Namen (der auch im Cron.log verwendet wird), dem Cron Schedule String, der Aufzurufenen Webseite, sowie dem Environment "PROD", "DEV" oder keinem Parameter, wenn er in jedem Environment ausgeführt werden soll. Alle Crons rufen im Endeffekt URLs auf, welche bei Aufruf auch ihr eigenes Errorhandling haben und ins Fehlersystem schreiben wenn was passiert ist. Dadurch garantieren wir das selbe Verhalten unabhängig davon, ob wir einen Backend Job per Hand oder per Cron aufrufen.

### LDAP

Ein Kernservice der die Anbindung an den LDAP Server übernimmt. In der okconfig YAML Datei sind Zugangsdaten für den LDAP Adminbenutzer "application" hinterlegt. Mit diesen können wir nicht nur Gruppen und Benutzerdaten herunterladen, sondern auch Änderungen am LDAP vornehmen. Z.B. das Setzen eines neuen Passworts oder die Anlage von neuen Benutzern für z.B. Zeitarbeiter.

Dieser Service wird auch vom Security System von Silex zum Login benutzt.  

### Service

Hier befinden sich alle nicht-speziellen Services der Middleware die die tatsächliche Anwendungslogik enthalten.

### Supplier

Analog zu Carriers, haben wir hier spezielle Klassen für Lieferanten. Das betrifft zumeist Generierung spezieller Label fürs Versandprogramm.  

  

## Util

Funktionen die man mal gebrauchen kann, die aber nicht speziell andere Abhängigkeiten und Konfigurationen haben und einfach so mit dem Konstruktor aufgerufen weden können. Dazu zählen eine auf tFPDF basierende PDF Library, Tabellen und Formulargenerierung, sowie Tiff, Excel und CSV Generierung. Einfach mal durchstöbern.



## References
1. 

## Quellen
1. [Doctrine DBAL](https://www.doctrine-project.org/projects/doctrine-dbal/en/2.13/reference/introduction.html#introduction)