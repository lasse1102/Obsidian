
--- 
Erstellt: 2024-04-29    11:06 
Tags: 
Link Up: [[PHP]]
Link Down:

--- 
# Was sind Sessions
HTTP ist ein zustandsloses Protokoll, das bedeutet, Informationen werden zwischen den verschiedenen Aufrufen eines Besuchers nicht Zwischengespeichert. Dies ist natürlich unpraktisch wenn wir gewisse Informationen zu einem Besucher speichern müssen, beispielsweise mit welchen Benutzername sich dieser eingeloggt hat. Um dies zu lösen, kann man PHP-Sessions verwenden

Mit Sessions hat man die Möglichkeit, bestimmte Daten während einer Folge von Aufrufen eurer Website festzuhalten. Wenn der Web-Server eine Session verwendet erstellt er ein Cookie Namens "PHPSESSID". Jede Session bekommt eine einzigartige Session-ID z.B. "pg211qqj3i90jj5c09k36gtlfe". Diese Session-ID wird vom Browser des Besuchers bei jedem Seitenaufruf erneut an den Webserver gesendet, so dass der Webserver die Möglichkeit hat, den Besucher zu identifizieren und Werte von vorherigen Seitenaufrufen zu laden.

Bei jedem Seitenaufruf teilt der Browser dem Webserver mit, welche Session-ID dieser besitzt

# Sessions erstellen
Möchte man in einen Script auf eine Session zugreifen, müssen wir am Anfang der Datei den folgenden Befehl aufrufen
```php
<?php
session_start();
?>```
Diese Funktion sorgt dafür das die ganze Seite jetzt auf die Session zugreifen kann 


Möchten wir einen Wert / eine Variable über mehrere Seitenaufrufe hinweg in der Session speichern, dann geht dies wie folgt:
```php
<?php
$_SESSION['name'] = "wert";
?>```


Diesen Wert können wir später auch auf anderen Seiten ausgeben, vorausgesetzt wir verwenden den oben genannten Befehl am Anfang des Skriptes
```php
<?php
$name = $_SESSION['name'];
echo $name;
?>```


Ihr könnt dabei die Session-Variable wie jede andere Variable in PHP verwenden. Ihr könnt darin Zahlen, Zeichenketten oder sogar Arrays abspeichern.

# Sessions löschen
Um alle Session-Daten der Sitzung zu löschen verwendet man session_destroy();
```php
session_destroy();
```
Dieser Befehl löscht **alle** Daten der Session und kann nützlich sein wenn sich der Benutzer z.B. aus eurem System ausloggen möchte. Denkt dran, ihr müsst zuvor _session_start()_ ausführen bevor ihr _session_destroy()_ ausführen könnt.


Um eine einzelne Session-Variablen zu löschen könnt ihr _unset($variable)_ verwenden:
```php
unset($_SESSION['name']);
```

# Nachteile von PHP-Sessions
1. Sicherheit
	**Sicherheit**: Obwohl Session-Variablen sicherer sind als Cookies (da sie nicht auf dem Computer des Benutzers gespeichert werden), können sie immer noch anfällig für Angriffe sein. Insbesondere auf geteilten Hosting-Servern können andere Benutzer auf demselben Server möglicherweise auf PHP-Session-Daten zugreifen.
2. Performance
	Das Problem mit PHP-Sessions liegt in der Performance und im Caching. Heißt alle Informationen, die im Browser-Cookie gespeichert sind, müssen bei jeder PHP-Anfrage hin- und herspringen, damit der Server weiß, wer der Benutzer ist(Wenn man beispielsweise den Benutzer in einer Session speichert).

Alternativen zu PHP-Sessions sind Cookies, Datenbanken, Caching Technologien oder URL-basierte Sessions
## References
1. 

## Quellen
1. https://kinsta.com/de/blog/wordpress-cookies-php-sessions/