# Gambio

***
# Konto verknüpfen

![Verbindung mit der Gambio-API herstellen](https://data.csv4you.com/media/image/guide/interface/gambio/gambio-api-zugangsdaten-hinterlegen.png ':zoom :size=30%')

### Folgende Daten werden dazu aus Ihrem Gambio-Account benötigt:

- URL der API in folgendem Format: https://www.myshop.com<br>

- E-Mail

- Passwort

- oder nur einen API-Token

Nach dem Anlegen können Sie im Menü des Zugangs auf 'Informationen' klicken. Werden Ihnen dort Shopdaten angezeigt, wurde Ihr API-Zugang erfolgreich angelegt.


***
# bestehende Listings abrufen

![Cronjob für das Zurücklesen](https://data.csv4you.com/media/image/guide/interface/gambio/gambio-einrichtung-cronjob-zuruecklesen.png ':zoom :size=30%')
![Manuelles Starten des Zurücklesens](https://data.csv4you.com/media/image/guide/interface/gambio/gambio-listings-uebersicht.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer bestehenden Gambio-Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen Abgleich von CSV4YOU. Es werden immer die API-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder per Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite 'Listings->Sonstige' mit der Schaltfläche 'Daten vom Shop einlesen' schreibt nur die Daten für die gerade benutzte Datenquelle. Im Hintergrund werden jedoch ALLE Listings Ihres Gambio-Shops zurückgegeben und ausgewertet.

Das Zurücklesen auf der Seite 'Mein Konto->Grundeinstellungen->API' unter der Auswahl 'Cronjob: Daten vom Shop einlesen', schreibt die Daten für ALLE Datenquellen. Sie müssen also nicht für jede Datenquelle einzeln das Zurücklesen durchführen. Das ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt mit der SKU in Ihrem Shop und der Artikelnummer in CSV4YOU. Ein späterer Abgleich kann nur über die zurückgegebene API-ID erfolgen.

!> Sollten Sie Listings direkt im Gambio gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen. Es werden dabei KEINE Daten im Gambio geändert. Danach können Sie erneut Ihre Shop-Daten zurücklesen.


***
# Kategoriezuordnung

Eine Übersicht der Einstellungen finden Sie [hier](export/categories).


***
# Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).


***
# Export

> Allgemeine Informationen zu den verschiedenen Funktionen der Exportprofile, finden Sie [hier](export/interface).

## Exportprofil Neuanlage einrichten

![Exportprofil->Grundeinstellungen](https://data.csv4you.com/media/image/guide/interface/gambio/gambio-exportprofil-neuanlage-grundeinstellungen.png ':zoom :size=30%')
![Exportprofil->Sonstiges](https://data.csv4you.com/media/image/guide/interface/gambio/gambio-exportprofil-neuanlage-sonstiges.png ':zoom :size=30%')

**Richten Sie ein Exportprofil zur Neuanlage mit folgenden Einstellungen ein:**

- Was möchten Sie zu Gambio übertragen?<br>
	1. Auswahl 'Produkte'<br>
	2. Auswahl 'nur neue Produkte'

Nach dem Export einer Produktneuanlage schauen Sie sich die Ihnen angebotenen Statusberichte an. In diesen finden Sie Informationen, ob die Produkte übertragen und angelegt wurden. Wenn das erledigt ist, sollten Sie Ihre aktuellen Shop-Daten in unser System zurücklesen. Das erfolgt im Bereich Listings und der Auswahl des jeweiligen Shops.
Sie können dafür auch einen Cronjob benutzen, den Sie unter den jeweiligen Verbindungseinstellungen Ihres Systems mit CSV4YOU finden.


## Exportprofil Bestandsupdate einrichten

![Exportprofil->Grundeinstellungen](https://data.csv4you.com/media/image/guide/interface/gambio/gambio-exportprofil-update-bestand-grundeinstellungen.png ':zoom :size=30%')
![Exportprofil->Sonstiges](https://data.csv4you.com/media/image/guide/interface/gambio/gambio-exportprofil-update-bestand-sonstiges.png ':zoom :size=30%')

**Richten Sie ein weiteres Exportprofil zum Bestandsabgleich mit folgenden Einstellungen ein:**

- Was möchten Sie zu Gambio übertragen?<br>
	1. Auswahl 'Bestand'<br>
	2. Auswahl 'Gelistete Produkte'

Durch das Zurücklesen der Gambio-Daten erkennt unser System, welche Produkte einen Bestandsabgleich benötigen. Diese werden durch dieses Exportprofil in Ihrem Gambio-Shop geändert.

!> Mit diesem Bestandsupdate können **keine** Varianten geändert werden.


***
# Varianten zu einem Produkt zusammenlegen

!> Alle Auswahlmöglichkeiten für das Arbeiten mit Varianten unter dem Punkt `Was möchten Sie zu Gambio übertragen?` erscheinen nur, wenn der Punkt `Export mit Parents` im Bereich [Exportprofil->Sonstiges](export/interface?id=sonstiges) ausgewählt ist.
Voraussetzung für das Arbeiten mit Varianten ist die ordentliche Einrichtung aller benötigten Daten in Ihrem [Datenpool](datapool/product?id=parents).


### Optionen
Sie benötigen dazu zuallererst die passenden Optionen. Sollten diese in Ihrem Shop noch nicht vorhanden sein, können Sie Optionen mit der Auswahl `Optionen anlegen` unter `Was möchten Sie zu Gambio übertragen?` senden.


### Hauptartikel(Parent)
Mit der Auswahl `Produkte` unter `Was möchten Sie zu Gambio übertragen?` übertragen Sie die Parents der jeweiligen Variationen als eigenständige Artikel.

***
> Die nachfolgenden Punkte können nur gesendet werden, wenn die Shop-ID´s der Produkte/Varianten durch vorheriges Zurücklesen in unserem System vorhanden sind.


### Varianten
Der nächste Schritt ist das Übertragen der Varianten für die vorhandenen Hauptartikel(Parent). Dazu wählen Sie den Punkt `Varianten` unter `Was möchten Sie zu Gambio übertragen?` aus und senden diese Auswahl.


### Bestand Varianten
Um den Bestand der Varianten zu übertragen, wählen Sie den Punkt `Bestand Varianten` unter `Was möchten Sie zu Gambio übertragen?` aus und senden diese Auswahl.

!> Mit diesem Bestandsupdate können **keine** Einzelartikel geändert werden.


### Preis Varianten
Um Preise der Varianten zu übertragen, wählen Sie den Punkt `Preis Varianten` unter `Was möchten Sie zu Gambio übertragen?` aus und senden diese Auswahl.