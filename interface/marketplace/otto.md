# OTTO Marketplace

## Konto verknüpfen

![Verbindung mit der OTTO-API herstellen](https://data.csv4you.com/media/image/guide/interface/otto/otto-api-zugangsdaten-hinterlegen.png ':zoom :size=30%')

Verbinden Sie mit dem korrekten Shopnamen unter `Mein Konto->Grundeinstellungen->API` Ihren Hood-Shop. Sie werden danach zu Hood weitergeleitet, wo Sie der Verbindung von CSV4YOU und Hood zustimmen müssen.
Wenn das erfolgreich abgeschlossen wurde, werden Sie automatisch weitergeleitet.
Nach dem Anlegen können Sie im Menü des Zugangs auf `Informationen` klicken. Werden Ihnen dort Shopdaten angezeigt, wurde Ihr API-Zugang erfolgreich angelegt.


## Kategorie zuweisen

![Kategorie Übersicht](https://data.csv4you.com/media/image/guide/interface/otto/otto-kategorie-uebersicht.png ':zoom :size=30%')
![OTTO Market-Kategorie zuweisen](https://data.csv4you.com/media/image/guide/interface/otto/otto-kategorie-ottokategorie.png ':zoom :size=30%')
![OTTO Market-Kategorie wurde bereits zugeweisen](https://data.csv4you.com/media/image/guide/interface/otto/otto-kategorie-ottokategorie-vorhanden.png ':zoom :size=30%')

Sie müssen zuerst den internen Kategorien eine OTTO Market-Kategorie zuordnen. Wenn Sie keine internen Kategorien benutzen, können Sie diese auch dem Produkt selbst zuweisen.
Geben Sie dazu einfach eine Suchbegriff in das Kategoriefeld. Es werden Ihnen sofort die möglichen OTTO-Kategorien angezeigt. Speichern Sie die gewünschte Kategorie und Sie können im Anschluss die benötigten Artikelmerkmale ausfüllen.

> Wir empfehlen die OTTO Market-Kategorie zuerst einer internen Kategorie zuzuweisen. Nur mit einer hinterlegten OTTO Market-Kategorie können Sie Artikelmerkmale zuweisen.


## Artikelmerkmale

![Kategorie Übersicht mit OTTO Market-Kategorie-ID](https://data.csv4you.com/media/image/guide/interface/otto/otto-kategorie-artikelmerkmale-uebersicht.png ':zoom :size=30%')
![Artikelmerkmale zuweisen](https://data.csv4you.com/media/image/guide/interface/otto/otto-kategorie-artikelmerkmale-eintragen.png ':zoom :size=30%')

Sie müssen zuerst den internen Kategorien Artikelmerkmale zuordnen. Wenn Sie keine internen Kategorien benutzen, können Sie diese auch dem Produkt selbst zuweisen.

> Rote Artikelmerkmale sind Pflichfelder!!

Sollte ein Artikelmerkmal mehrere Werte zulassen, so trennen Sie diese mit einer Doppel-Pipe(||).

> Wir empfehlen die Artikelmerkmale zuerst den internen Kategorien zuzuweisen. Eine Zuweisung bei den Artikeln ist nur bei speziellen Merkmalen nötig, welche zum Beispiel nicht in den Produktdaten vorkommen.


## bestehende Listings abrufen

![Einlesen unter 'Listings->Sonstige'](https://data.csv4you.com/media/image/guide/api/api-zuruecklesen-listings.png ':zoom :size=30%')
![Einlesen unter 'Mein Konto->Grundeinstellungen->API'](https://data.csv4you.com/media/image/guide/api/api-zuruecklesen-meinkonto.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen nur zum Vergleichen.
Es werden immer die OTTO-Listings-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder mit einem Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite `Listings->Sonstiges->OTTO`mit dem Button `Daten vom Shop einlesen` schreibt nur die Daten für die gerade benutzte Datenquelle.
Es werden trotzdem im Hintergrund ALLE Listings von OTTO zurückgegeben.

Das Zurücklesen auf der Seite `Mein Konto->Grundeinstellungen->API` unter der Auswahl `Cronjob: Daten von OTTO einlesen`, schreibt die Daten für ALLE Datenquellen.
Sie müssen also nicht für jede Datenquelle das Zurücklesen durchführen. Dieses ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt fast immer mit der SKU bei OTTO und der Artikelnummer im CSV4YOU.

> Sollten Sie Listings direkt auf dem OTTO gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen.
Es werden KEINE Daten in OTTO geändert. Danach können Sie erneut zurücklesen.


## Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).


## Statusbericht des letzten Exportes

![Ansicht 1: gesendete Produkte](https://data.csv4you.com/media/image/guide/api/otto/status/otto-export-status.png ':zoom :size=30%')
![Ansicht 2: nähere Statusangaben zu einem einzelnen Produkt](https://data.csv4you.com/media/image/guide/api/otto/status/otto-export-status-2.png ':zoom :size=30%')

Mit einem Klick auf den Button 'Letzter Statusbericht' kommen Sie zu den Responsedaten des letzten Exportes zu Otto. Hier werden Ihnen alle fehlenden oder falschen Daten angezeigt.


#### Sie erhalten die Statusfehlermeldung 'unchanged'

Wenn Sie Daten zu OTTO exportieren, welche bereits vorhanden sind oder Sie nacheinander mehrmals die selben Daten senden, kommt die Statusmeldung 'unchanged'.
OTTO hat dann nichts angelegt oder geändert. Versuchen Sie daher, die zu sendenen Daten abzuändern.
Lassen Sie bei der Übertragung zum Beispiel einen Wert weg, indem Sie unter 'eigene Spaltenzuordnung' des Exportprofiles nur die Werte auswählen, welche Sie senden möchten.
Sie können auch einfach einen Artikelwert umschreiben.


## Produkte für den Export sperren

![Produkte für Marktplätze sperren/freischalten](https://data.csv4you.com/media/image/guide/api/otto/product/otto-product-sperren.png ':zoom :size=30%')
![Ansicht gesperrte Artikel](https://data.csv4you.com/media/image/guide/api/otto/product/otto-product-sperren-2.png ':zoom :size=30%')

Sie können im Abschnitt 'OTTO' der Einstellungen des Produktes angeben, ob ein Produkt auf bestimmten Marktplätzen gesperrt werden soll. Diese Produkte werden dann bei der Übertragung zu OTTO nicht übermittelt.