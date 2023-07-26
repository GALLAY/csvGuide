# Etsy

The term 'Etsy' is a trademark of Etsy, Inc. This application uses the Etsy API but is not endorsed or certified by Etsy, Inc.


***
# Konto verknüpfen

![Verbindung mit der Etsy-API herstellen](https://data.csv4you.com/media/image/guide/interface/etsy/etsy-api-zugangsdaten-hinterlegen.png ':zoom :size=30%')

Verbinden Sie mit dem korrekten Shopnamen unter `Mein Konto->Grundeinstellungen->API` Ihren Etsy-Shop. Sie werden danach zu Etsy weitergeleitet, wo Sie der Verbindung von CSV4YOU und Etsy zustimmen müssen.
Wenn das erfolgreich abgeschlossen wurde, werden Sie automatisch weitergeleitet.
Nach dem Anlegen können Sie im Menü des Zugangs auf `Informationen` klicken. Werden Ihnen dort Shopdaten angezeigt, wurde Ihr API-Zugang erfolgreich angelegt.


***
# aktuelle Etsy-Listings abrufen

![Einlesen unter 'Listings->Sonstige'](https://data.csv4you.com/media/image/guide/api/api-zuruecklesen-listings.png ':zoom :size=30%')
![Einlesen unter 'Mein Konto->Grundeinstellungen->API'](https://data.csv4you.com/media/image/guide/api/api-zuruecklesen-meinkonto.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen nur zum Vergleichen.
Es werden immer die Etsy-Listings-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder mit einem Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite `Listings->Sonstiges->Etsy`mit dem Button `Daten vom Shop einlesen` schreibt nur die Daten für die gerade benutzte Datenquelle.
Es werden trotzdem im Hintergrund ALLE Listings von Etsy zurückgegeben.

Das Zurücklesen auf der Seite `Mein Konto->Grundeinstellungen->API` unter der Auswahl `Cronjob: Daten von Etsy einlesen`, schreibt die Daten für ALLE Datenquellen.
Sie müssen also nicht für jede Datenquelle das Zurücklesen durchführen. Dieses ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt fast immer mit der SKU beim Marktplatz und der Artikelnummer im CSV4YOU. Bei einigen System kann ein Abgleich nur über die zurückgegebene API-ID erfolgen.

> Sollten Sie Listings direkt auf dem Marktplatz gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen.
Es werden KEINE Daten im Marktplatz geändert. Danach können Sie erneut zurücklesen.


***
# Kategoriezuordnung

Eine Übersicht der Einstellungen finden Sie [hier](export/categories).


***
# Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).