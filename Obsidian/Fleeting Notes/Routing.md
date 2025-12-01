
--- 
Erstellt: 2024-04-12    12:06 
Tags: #inProcess 
Link Up: [[PHP]]
Link Down:

--- 
# Routing
Slim bietet eine einfache Methode zum Routing von HTTP-Anfragen an bestimmte Funktionen oder Methoden Ihrer Anwendung

## GET Route
Die `GET`-Route in einem Web-Framework wie Slim wird verwendet, um Daten von einem Server abzurufen. Sie ist eine der häufigsten HTTP-Methoden und wird oft verwendet, um Seiteninhalte oder Daten aus einer Datenbank abzurufen.

```php
$app->get('/books/{id}', function ($request, $response, array $args) {
    // Show book identified by $args['id']
});
```
wird die `GET`-Route verwendet, um Informationen über ein bestimmtes Buch abzurufen, das durch `{id}` identifiziert wird. Wenn ein Benutzer beispielsweise eine Anfrage an `www.example.com/books/123` sendet, würde die `GET`-Route aktiviert und die Anwendung sollte Informationen über das Buch mit der ID 123 zurückgeben.

### POST Route
Die `POST`-Route in einem Web-Framework wie Slim wird verwendet, um neue Daten an den Server zu senden und dort zu speichern. Sie ist eine der grundlegenden HTTP-Methoden und wird oft verwendet, um neue Einträge in einer Datenbank zu erstellen.

```php
$app->post('/books', function ($request, $response, array $args) {
    // Create new book
});
```
wird die `POST`-Route verwendet, um ein neues Buch zu erstellen. Wenn ein Benutzer beispielsweise eine Anfrage an `www.example.com/books` mit den notwendigen Daten für ein neues Buch sendet, würde die `POST`-Route aktiviert und die Anwendung sollte ein neues Buch mit den bereitgestellten Daten erstellen.

# Optimale Parameter bei Routen
