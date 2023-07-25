# Hood


***
# Konto verknüpfen

![Verbindung mit der Hood-API herstellen](https://data.csv4you.com/media/image/guide/interface/hood/hood-api-zugangsdaten-hinterlegen.png ':zoom :size=30%')

Verbinden Sie mit dem korrekten Shopnamen unter `Mein Konto->Grundeinstellungen->API` Ihren Hood-Shop. Sie werden danach zu Hood weitergeleitet, wo Sie der Verbindung von CSV4YOU und Hood zustimmen müssen.
Wenn das erfolgreich abgeschlossen wurde, werden Sie automatisch weitergeleitet.
Nach dem Anlegen können Sie im Menü des Zugangs auf `Informationen` klicken. Werden Ihnen dort Shopdaten angezeigt, wurde Ihr API-Zugang erfolgreich angelegt.


***
# aktuelle Hood-Listings abrufen

![Einlesen unter 'Listings->Sonstige'](https://data.csv4you.com/media/image/guide/api/api-zuruecklesen-listings.png ':zoom :size=30%')
![Einlesen unter 'Mein Konto->Grundeinstellungen->API'](https://data.csv4you.com/media/image/guide/api/api-zuruecklesen-meinkonto.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen nur zum Vergleichen.
Es werden immer die Hood-Listings-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder mit einem Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite `Listings->Sonstiges->Hood`mit dem Button `Daten vom Shop einlesen` schreibt nur die Daten für die gerade benutzte Datenquelle.
Es werden trotzdem im Hintergrund ALLE Listings von Hood zurückgegeben.

Das Zurücklesen auf der Seite `Mein Konto->Grundeinstellungen->API` unter der Auswahl `Cronjob: Daten von Hood einlesen`, schreibt die Daten für ALLE Datenquellen.
Sie müssen also nicht für jede Datenquelle das Zurücklesen durchführen. Dieses ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt fast immer mit der SKU bei Hood und der Artikelnummer im CSV4YOU.

> Sollten Sie Listings direkt auf dem Hood gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen.
Es werden KEINE Daten in Hood geändert. Danach können Sie erneut zurücklesen.


***
# Kategoriezuordnung

Eine Übersicht der Einstellungen finden Sie [hier](export/categories).


***
# Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).