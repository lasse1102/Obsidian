
--- 
Erstellt: 2024-04-05    11:35 
Tags: 
Link Up: [[PHP]] [[JavaScript]]
Link Down:

--- 
# Gemeinsamkeiten von PHP und JS
1. [[#Sprachtyp]]
2. [[#Typisierung von Variablen]] 
3. Klassen und Objekte
4. [[#Marknachfrage]]
5. [[#Dokumentation]]

## Sprachtyp
Es sind beides Skriptsprachen und keine reinen Programmiersprachen wie Java oder C#. Skriptsprachen werden in der Regel interpretiert und nicht kompiliert. Das bedeutet, dass sie nicht direkt, sondern über einen Drittanbieter in Maschinencode übersetzt wird, dies hat den Grund, weil der PC nur nullen und Einsen versteht und mittels des Interpreter übersetzt er unseren Code in den Maschinencode (der Maschinensprache). Das hat Auswirkungen auf ihre Laufzeit.

Das ist der Grund, warum kompilierte Sprachen tendenziell schneller sind als interpretierte Sprachen

## Typisierung von Variablen
Eine weitere Gemeinsamkeit ist, dass PHP und JavaScript schwach typisiert sind.

Das bedeutet, wenn du eine Variable in einer der beiden Sprachen erstellst musst du ihren Datentyp nicht zuweisen. Er wird angenommen

```php
$x = 'Hello world';

$y = 'Bonjour le monde';
```

```js
var x = 'Coding is fun';

let y = 'No, honestly';
```

## Marknachfrage
Eine weitere Gemeinsamkeit von PHP und JS ist, dass Entwickler für beide Sprachen sehr gefragt sind

## Dokumentation
Die Dokumentation der beiden Scriptsprachen ist nicht sehr benutzerfreundlich, was es Einsteigern deutlich schwieriger macht, da es eher für erfahrene Entwickler geschrieben ist

Dokumentation beider Sprachen:
- [PHP-Dokumentation](https://www.php.net/docs.php)
- [ECMAScript 2020 Sprachspezifikation](https://www.ecma-international.org/ecma-262/)

# Was sind die Unterschiede zwischen PHP und JavaScript

1. [[#Serverseitiges vs. Clientseitiges Scripting]]
2. [[#Frontend vs Backend]]
3. [[#Kombination mit anderen Sprachen]]
4. [[#Case Sensitivity]]
5. [[#Definition von Variablen und Konstanten]]
6. [[#Arrays]]
7. [[#Datenbank Integration]]

## Serverseitiges vs. Clientseitiges Scripting
PHP ist eine Serverseitige Skriptsprache. Das bedeutet, dass es auf dem Webserver läuft, im Gegensatz zu einen Client-Rechner. 

Serverseitige Programmierung ist nützlich, um Benutzern dynamische Inhalte (typischerweise aus einer Datenbank zu liefern, wie z.B. eine Willkommensnachricht („Hi, Claire!“), wenn sich ein Benutzer anmeldet.

JavaScript ist eine **clientseitige** Sprache, also läuft es auf dem Laptop, dem Telefon oder dem Tablet des Nutzers. JavaScript kann das DOM manipulieren

## Frontend vs Backend
PHP läuft im Backend einer Webseite – dem Teil, den Besucher nicht sehen! Dies bedeutet das PHP seine ganze Arbeit auf dem Webserver macht

JavaScript lief traditionell im Frontend, aber das änderte sich 2009, als Node.js, eine Backend-Runtime, eingeführt wurde. Heute ist JavaScript wirklich eine **Full-Stack**-Sprache.

## Kombination mit anderen Sprachen
Man kann PHP beispielsweise mit HTML verschmelzen, das würde so aussehen:
```php
<header class="archive-header has-text-align-center header-footer-group">

<div class="archive-header-inner section-inner medium">

<?php if ( $archive_title ) { ?>

<h1 class="archive-title"><?php echo wp_kses_post( $archive_title ); ?></h1>

<?php } ?>
<?php if ( $archive_subtitle ) { ?>
<div class="archive-subtitle section-inner thin max-percentage intro-text"><?php echo wp_kses_post( wpautop( $archive_subtitle ) ); ?></div>
<?php } ?>

</div>

</header>
```
Wenn man PHP jedoch mit anderen Backend-Sprachen vermischt, ist es schwierig, sie zu warten.

JS-Entwickler haben ein bisschen mehr Freiheit beim Schreiben ihres codes. Sie können die Sprache mit HTML, XML und Ajax verwenden

## Arrays
Arrays sind Variablen, die mehr als eine Sache speichern können

In PHP sind gibt es neben numerischen Arrays auch [[Assoziative Array]], die für den die Values einen dazugehörigen Key haben.
Der Einfachheit halber kannst du PHP-Objekte in Arrays und Arrays in Objekte konvertieren

Allerdings kann JS nur Arrays haben, die nummerierte Indizes haben Zum Beispiel:
```js
var mountains = [
"Everest",
"Kilimanjaro",
"Fuji"
];
```
Um einen Wert abzurufen, musst du den Array-Index referenzieren, der bei 0 beginnt.

```js
var mountain = mountains[1];
```

Assoziative Arrays mit ihren **benannten** Indizes werden in JavaScript nicht unterstützt.

# Datenbank Integration
Eine Sache, die PHP hervorragend kann, ist die Anbindung an Datenbanken. Es gibt ebenfalls eine Reihe von PHP-Frameworks die eine Datenbankintegration ermöglichen

Die Verwendung einer Datenbank ist nützlich, um Informationen zu suchen, zu sortieren und zu filtern, um sie dem Benutzer zu präsentieren, wie z.B. Produkte in einem Online-Shop.

Historisch gesehen ist JavaScript nicht mit Datenbanken kompatibel, aber das beginnt sich zu ändern.


## References
1. [[Kann JavaScript mit PHP verwendet werden]]

## Quellen
1. https://kinsta.com/de/blog/php-vs-javascript/