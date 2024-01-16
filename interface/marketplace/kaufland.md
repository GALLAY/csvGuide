# Kaufland

***
# Konto verknüpfen

![Verbindung mit der Kaufland-API herstellen](https://data.csv4you.com/media/image/guide/interface/kaufland/kaufland-api-zugangsdaten-hinterlegen.png ':zoom :size=30%')

Verbinden Sie unter `Mein Konto->Grundeinstellungen->API` mit den korrekten Zuganfsdaten Ihren Kaufland-Shop.
Nach dem Anlegen können Sie im Menü des Zugangs auf `Informationen` klicken. Werden Ihnen dort Shopdaten angezeigt, wurde Ihr API-Zugang erfolgreich angelegt.


***
# aktuelle Kaufland-Listings abrufen

![Einlesen unter 'Listings->Sonstige'](https://data.csv4you.com/media/image/guide/api/api-zuruecklesen-listings.png ':zoom :size=30%')
![Einlesen unter 'Mein Konto->Grundeinstellungen->API'](https://data.csv4you.com/media/image/guide/api/api-zuruecklesen-meinkonto.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen nur zum Vergleichen.
Es werden immer die Kaufland-Listings-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder mit einem Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite `Listings->Sonstiges->Kaufland`mit dem Button `Daten vom Shop einlesen` schreibt nur die Daten für die gerade benutzte Datenquelle.
Es werden trotzdem im Hintergrund ALLE Listings von Kaufland zurückgegeben.

Das Zurücklesen auf der Seite `Mein Konto->Grundeinstellungen->API` unter der Auswahl `Cronjob: Daten von Kaufland einlesen`, schreibt die Daten für ALLE Datenquellen.
Sie müssen also nicht für jede Datenquelle das Zurücklesen durchführen. Dieses ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt fast immer mit der EAN oder SKU beim Marktplatz und der Artikelnummer im CSV4YOU. Bei einigen System kann ein Abgleich nur über die zurückgegebene API-ID erfolgen.

> Sollten Sie Listings direkt auf dem Marktplatz gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen.
Es werden KEINE Daten im Marktplatz geändert. Danach können Sie erneut zurücklesen.


***
# Kategoriezuordnung

Eine Übersicht der Einstellungen finden Sie [hier](export/categories).


***
# Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).


***
# Export

Auf kaufland.de wird zwischen Produktdaten und Angebotsdaten unterschieden. Welche Daten Sie übertragen, wählen Sie im Bereich 'Sonstiges' aus.

!> Pflichtangaben: Im Abschnitt 'eigene Spaltenzuordnung' müssen die Felder 'condition' und ('delivery_time' oder 'delivery_time_min + delivery_time_max') ausgefüllt sein. Ohne diese Angaben ist das Einstellen nicht möglich.


## Produktdaten

Jedes Produkt hat Produktdaten ("product data"), die unabhängig vom Händler für ein Produkt bestehen. Dazu gehören z.B. EAN, Produktbild, Produkttitel, Hersteller, Farbe, Größe oder Zielgruppe.
Wenn ein Produkt noch nicht in der Kaufland-Produktdatenbank vorhanden ist, müssen diese Daten(product data) einmalig dorthin gesendet werden. Damit werden diese dort angelegt. Dieser Vorgang kann aber bis zu 24 Stunden dauern.


## Angebotsdaten

Jeder Händler hat für ein Produkt Angebotsdaten ("inventory data"), die nur für einen Händler und für ein bestimmtes Produkt gelten. Dazu gehören z.B. Preis, Zustand, Anzahl der beim Händler verfügbaren Einheiten oder Kommentar zum Zustand des Artikels. Bei Änderung der Angebotsdaten müssen die Produktdaten nicht erneut übertragen werden.
Ist ein Produkt bereits in der Kaufland-Produktdatenbank vorhanden, reicht es aus, nur die Angebotsdaten nach Kaufland zu senden. Schauen Sie nach jedem Senden in den zurückgelieferten Statusbericht. Im Anschluss können Sie die erfolgreich angelegten Produkte in unser System zurücklesen. Damit erfolgt eine Unterscheidung, welche Produkte bereits gelistet sind und welche nicht.

!> Es werden nur Artikel gesendet, welche eine Änderung im Bestand oder Preis benötigen. Wenn Sie alle Produkte senden möchten, aktivieren Sie im Bereich `Sonstiges` die Option `Alle Produkte senden`.