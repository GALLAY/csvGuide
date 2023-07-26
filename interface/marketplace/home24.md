# Home24 Marketplace

***
# Konto verknüpfen

![Verbindung mit der Home24-API herstellen](https://data.csv4you.com/media/image/guide/interface/home24/home24-api-zugangsdaten-hinterlegen.png ':zoom :size=30%')

Verbinden Sie unter `Mein Konto->Grundeinstellungen->API` mit den korrekten Zugangsdaten Ihren Home24-Shop.
Nach dem Anlegen können Sie im Menü des Zugangs auf `Informationen` klicken. Werden Ihnen dort Shopdaten angezeigt, wurde Ihr API-Zugang erfolgreich angelegt.


***
# Kategorie zuweisen

![Kategorie Übersicht](https://data.csv4you.com/media/image/guide/interface/home24/home24-kategorie-uebersicht.png ':zoom :size=30%')
![Home24-Kategorie zuweisen](https://data.csv4you.com/media/image/guide/interface/home24/home24-kategorie-home24kategorie.png ':zoom :size=30%')

Sie müssen zuerst den internen Kategorien eine Home24-Kategorie zuordnen. Wenn Sie keine internen Kategorien benutzen, können Sie diese auch dem Produkt selbst zuweisen.
Wählen Sie dazu die passende Kategorie aus dem Kategoriefeld. Speichern Sie die gewünschte Kategorie und Sie können im Anschluss die benötigten Artikelmerkmale ausfüllen.

> Wir empfehlen die Home24-Kategorie zuerst einer internen Kategorie zuzuweisen. Nur mit einer hinterlegten Home24-Kategorie können Sie Artikelmerkmale zuweisen.


***
# Artikelmerkmale

![Kategorie Übersicht mit Home24-Kategorie-ID](https://data.csv4you.com/media/image/guide/interface/home24/home24-kategorie-artikelmerkmale-uebersicht.png ':zoom :size=30%')
![Artikelmerkmale zuweisen](https://data.csv4you.com/media/image/guide/interface/home24/home24-kategorie-artikelmerkmale-eintragen.png ':zoom :size=30%')

Sie müssen zuerst den internen Kategorien Artikelmerkmale zuordnen. Wenn Sie keine internen Kategorien benutzen, können Sie diese auch dem Produkt selbst zuweisen.

> Rote Artikelmerkmale sind Pflichfelder!!

Sollte ein Artikelmerkmal mehrere Werte zulassen, so trennen Sie diese mit einer Doppel-Pipe(||).

> Wir empfehlen die Artikelmerkmale zuerst den internen Kategorien zuzuweisen. Eine Zuweisung bei den Artikeln ist nur bei speziellen Merkmalen nötig, welche zum Beispiel nicht in den Produktdaten vorkommen.


***
# bestehende Listings abrufen

![Einlesen unter 'Listings->Sonstige'](https://data.csv4you.com/media/image/guide/interface/home24/home24-zuruecklesen-listings.png ':zoom :size=30%')
![Einlesen unter 'Mein Konto->Grundeinstellungen->API'](https://data.csv4you.com/media/image/guide/interface/home24/home24-zuruecklesen-meinkonto.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen nur zum Vergleichen.
Es werden immer die Home24-Listings-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder mit einem Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite `Listings->Sonstiges->Home24`mit dem Button `Daten vom Shop einlesen` schreibt nur die Daten für die gerade benutzte Datenquelle.
Es werden trotzdem im Hintergrund ALLE Listings von Home24 zurückgegeben.

Das Zurücklesen auf der Seite `Mein Konto->Grundeinstellungen->API` unter der Auswahl `Cronjob: Daten von Home24 einlesen`, schreibt die Daten für ALLE Datenquellen.
Sie müssen also nicht für jede Datenquelle das Zurücklesen durchführen. Dieses ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt fast immer mit der SKU bei Home24 und der Artikelnummer im CSV4YOU.

> Sollten Sie Listings direkt auf Home24 gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen.
Es werden KEINE Daten in Home24 geändert. Danach können Sie erneut zurücklesen.


***
# Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).



***
# Produkte für den Export sperren

![Produkte für Marktplätze sperren/freischalten](https://data.csv4you.com/media/image/guide/interface/home24/home24-product-sperren.png ':zoom :size=30%')
![Ansicht gesperrte Artikel](https://data.csv4you.com/media/image/guide/interface/home24/home24-product-sperren-2.png ':zoom :size=30%')

Sie können im Abschnitt 'Home24' der Einstellungen des Produktes angeben, ob ein Produkt für den Export gesperrt werden soll. Diese Produkte werden dann bei der Übertragung zu Home24 nicht übermittelt.