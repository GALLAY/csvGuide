# Shopware 6

***
# Konto verknüpfen

![Verbindung mit der Shopware.6-API herstellen](https://data.csv4you.com/media/image/guide/interface/shopware6/shopware6-api-zugangsdaten-hinterlegen.png ':zoom :size=30%')

### Folgende Daten werden dazu aus Ihrem Shopware.6-Account benötigt:

- URL der API in folgendem Format: https://www.myshop.com<br>

- Zugangsschlüssel-ID

- Sicherheitsschlüssel

Nach dem Anlegen können Sie im Menü des Zugangs auf 'Informationen' klicken. Werden Ihnen dort Shopdaten angezeigt, wurde Ihr API-Zugang erfolgreich angelegt.


***
# bestehende Listings abrufen

![Cronjob für das Zurücklesen](https://data.csv4you.com/media/image/guide/interface/shopware6/shopware6-einrichtung-cronjob-zuruecklesen.png ':zoom :size=30%')
![Manuelles Starten des Zurücklesens](https://data.csv4you.com/media/image/guide/interface/shopware6/shopware6-listings-uebersicht.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer bestehenden Shopware.6-Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen Abgleich von CSV4YOU. Es werden immer die API-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder per Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite 'Listings->Sonstige' mit der Schaltfläche 'Daten vom Shop einlesen' schreibt nur die Daten für die gerade benutzte Datenquelle. Im Hintergrund werden jedoch ALLE Listings Ihres Shopware.6-Shops zurückgegeben und ausgewertet.

Das Zurücklesen auf der Seite 'Mein Konto->Grundeinstellungen->API' unter der Auswahl 'Cronjob: Daten vom Shop einlesen', schreibt die Daten für ALLE Datenquellen. Sie müssen also nicht für jede Datenquelle einzeln das Zurücklesen durchführen. Das ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt mit der SKU in Ihrem Shop und der Artikelnummer in CSV4YOU. Ein späterer Abgleich kann nur über die zurückgegebene API-ID erfolgen.

!> Sollten Sie Listings direkt im Shopware.6 gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen. Es werden dabei KEINE Daten im Shopware.6 geändert. Danach können Sie erneut Ihre Shop-Daten zurücklesen.


***
# Kategoriezuordnung

Eine Übersicht der Einstellungen finden Sie [hier](export/categories).


***
# Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).


***
# Export

> Allgemeine Informationen zu den verschiedenen Funktionen der Exportprofile, finden Sie [hier](export/interface).

> Es erscheinen unter `Was möchten Sie zu Shopware übertragen?` unterschiedliche Auswahlmöglichkeiten für die Neuanlage und das Update. 

## Exportprofil Neuanlage einrichten

**Richten Sie ein Exportprofil zur Neuanlage mit folgenden Einstellungen ein:**

- Was möchten Sie zu Shopware übertragen?<br>
	1. Auswahl 'nur neue Produkte'<br>
	2. Auswahl 'Produkte'

Nach dem Export einer Produktneuanlage schauen Sie sich die Ihnen angebotenen Statusberichte an. In diesen finden Sie Informationen, ob die Produkte übertragen und angelegt wurden. Wenn das erledigt ist, sollten Sie Ihre aktuellen Shop-Daten in unser System zurücklesen. Das erfolgt im Bereich Listings und der Auswahl des jeweiligen Shops.
Sie können dafür auch einen Cronjob benutzen, den Sie unter den jeweiligen Verbindungseinstellungen Ihres Systems mit CSV4YOU finden.

!> Im Bereich 'eigene Spaltenzuordnung' muss die Spalte 'taxId' ausgefüllt werden.


## Exportprofil Bestandsupdate einrichten

**Richten Sie ein weiteres Exportprofil zum Bestandsabgleich mit folgenden Einstellungen ein:**

- Was möchten Sie zu Shopware übertragen?<br>
	1. Auswahl 'Gelistete Produkte'<br>
	2. Auswahl 'Bestand'

Durch das Zurücklesen der Shopware.6-Daten erkennt unser System, welche Produkte einen Bestandsabgleich benötigen. Diese werden durch dieses Exportprofil in Ihrem Shopware.6-Shop geändert.


## Exportprofil für die Bilder einrichten

**Richten Sie ein weiteres Exportprofil zum Bildupload mit folgenden Einstellungen ein:**

- Was möchten Sie zu Shopware übertragen?<br>
	1. Auswahl 'Gelistete Produkte'<br>
	2. Auswahl 'Bilder'

!> Bilder können nur für Produkte übertragen werden, die durch das Zurücklesen Ihrer Shopware.6-Daten in CSV4YOU hinterlegt sind.

***
# Varianten zu einem Produkt zusammenlegen

!> Alle Auswahlmöglichkeiten für das Arbeiten mit Varianten unter dem Punkt `Was möchten Sie zu Shopware übertragen?` erscheinen nur, wenn der Punkt `Export mit Parents` im Bereich [Exportprofil->Sonstiges](export/interface?id=sonstiges) ausgewählt ist.
Voraussetzung für das Arbeiten mit Varianten ist die ordentliche Einrichtung aller benötigten Daten in Ihrem [Datenpool](datapool/product?id=parents).


### Eigenschaften
Sie benötigen dafür zuerst die passenden Eigenschaften. Sollten diese in Ihrem Shop noch nicht vorhanden sein, können Sie Eigenschaften mit der Auswahl `Eigenschaften anlegen` unter `Was möchten Sie zu Shopware übertragen?` senden.


### Hauptartikel(Parent)
Mit der Auswahl `Parents (Es werden keine Bilddaten gesendet)` unter `Was möchten Sie zu Shopware übertragen?` übertragen Sie die Parents der jeweiligen Variationen.


### Hauptartikel(Parent) mit den Produkten(Varianten) verbinden
Der nächste Schritt ist das Zusammenführen der Varianten mit dem Parent. Dazu wählen Sie den Punkt `Parent und Varianten verknüpfen` unter `Was möchten Sie zu Shopware übertragen?` aus und senden diese Auswahl.
