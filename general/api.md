# Allgemeine API-Informationen

***
# aktuelle API-Listings abrufen

![Einlesen unter 'Listings'](https://data.csv4you.com/media/image/guide/api/api-zuruecklesen-listings.png ':zoom :size=30%')
![Einlesen unter 'Mein Konto->Grundeinstellungen'](https://data.csv4you.com/media/image/guide/api/api-zuruecklesen-meinkonto.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen nur zum Vergleichen.
Es werden immer die API-Listings-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder mit einem Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite `Listings` schreibt nur die Daten für die gerade benutzte Datenquelle.
Es werden trotzdem im Hintergrund ALLE Listings zurückgegeben.

Das Zurücklesen auf der Seite `Mein Konto->Grundeinstellungen` unter der Auswahl `Cronjob: Daten von [APINAME] einlesen`, schreibt die Daten für ALLE Datenquellen.
Sie müssen also nicht für jede Datenquelle das Zurücklesen durchführen. Dieses ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Mit dem Zurücklesen wird auch gewährleistet, das bei einem Update nur die Produkte gesendet werden, welche eine Änderung benötigen.

> Ein Abgleich erfolgt fast immer mit der SKU beim Shop/Marktplatz und der Artikelnummer im CSV4YOU. Bei einigen System kann ein Abgleich nur über die zurückgegebene API-ID erfolgen.

> Sollten Sie Listings direkt auf dem Shop/Marktplatz gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen.
Es werden KEINE Daten im Shop/Marktplatz geändert. Danach können Sie erneut zurücklesen.


### Unterscheidung der Listingstypen im Export

- **nur neue Produkte**<br>
	Es werden alle Produkte übertragen, welche noch nicht im externen System gelistet ist.
	Sollten Produkte bereits vorhanden sein, aber es wurde nicht zurückgelesen, kann es in einigen externen Systemen zu doppelten Listings kommen.

- **gelistete Produkte**<br>
    Es werden alle Produkte übertragen, welche bereits im externen System gelistet sind.

***
# Kategoriezuordnung

Eine Übersicht der Einstellungen finden Sie [hier](export/categories).

Einige Marktplätze benutzen eigene Kategoriezuordnungen, welche Sie über `Datenpool->Interne Kategorien` oder `Datenpool->Produkte` erreichen.


***
# Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).


***
# Exportprofil

Wir empfehlen die nachfolgende Exportprofile einzurichten.
Allgemeine Informationen zu den verschiedenen Funktionen der Exportprofile, finden Sie [hier](export/interface).

### Neuanlage

Richten Sie ein Exportprofil zur Neuanlage mit nachfolgenden Einstellungen im Abschnitt [Sonstiges](export/interface?id=sonstiges) ein:

**Was möchten Sie zu xxxxx übertragen?**
- 1. Auswahl 'Produkte'
- 2. Auswahl 'nur neue Produkte'

> Nach dem Export einer Produktneuanlage schauen Sie sich die Ihnen angebotenen Statusberichte an. In diesen finden Sie Informationen, ob die Produkte übertragen und angelegt wurden.
Wenn das geschehen ist, sollten Sie aktuelle OTTO-Daten in unser System zurücklesen. Dies erfolgt im Bereich Listings und der Auswahl des jeweiligen Shops oder Marktplatz.
Sie können dafür auch einen Cronjob benutzen, welchen Sie unter den jeweilgen Verbindungseinstellungen Ihres Systems mit CSV4YOU finden.

### Bestandsänderung

Richten Sie ein weiteres Exportprofil zum Bestandsabgleich mit nachfolgenden Einstellungen ein:

**Was möchten Sie zu xxxxx übertragen?**
- 1. Auswahl 'Bestand'
- 2. Auswahl 'Gelistete Produkte'

!> Standardmäßig werden nur Artikel übertragen, welche eine Änderung des Bestandes benötigen.

### Preisänderung

Sie können optional ein weiteres Exportprofil für den Preisabgleich mit nachfolgenden Einstellungen einrichten:

**Was möchten Sie zu xxxxx übertragen?**
- 1. Auswahl 'Preis'
- 2. Auswahl 'Gelistete Produkte'

> Ein Preisupdate steht nicht bei allen API-Schnittstellen zur Verfügung

!> Standardmäßig werden nur Artikel übertragen, welche eine Änderung des Preises benötigen.


***
# Produkte für den Export sperren

![Produkte für Marktplätze sperren/freischalten](https://data.csv4you.com/media/image/guide/api/api-product-sperren.png ':zoom :size=30%')
![Ansicht gesperrte Artikel](https://data.csv4you.com/media/image/guide/api/api-product-sperren-2.png ':zoom :size=30%')

Sie können im Abschnitt 'API' der Einstellungen des Produktes angeben, ob ein Produkt für den Export gesperrt werden soll. Dieses Produkte werden dann nicht übermittelt.