# Shopify

***
# Konto verknüpfen

![Verbindung mit der Shopify-API herstellen](https://data.csv4you.com/media/image/guide/interface/shopify/shopify-api-zugangsdaten-hinterlegen.png ':zoom :size=30%')

Hinterlegen Sie unter 'Mein Konto->Grundeinstellungen->API' die passenden API-Zugangsdaten für Ihren Shopify-Shop.


### Zugangsdaten im Shopify per benutzerdefinierte App anlegen

Informationen zum Anlegen einer `Benutzerdefinierte App` finden Sie [hier](https://help.shopify.com/de/manual/apps/app-types/custom-apps)

> Sollten Sie Probleme beim Anlegen haben, wenden Sie sich bitte an der Shopify-Support.

### Folgende Daten werden dazu aus Ihrem Shopify-Account benötigt:

- Shop-Url in folgendem Format: https://SHOPNAME.myshopify.com<br>
    Domain bitte EXAKT so übernehmen und nur SHOPNAME durch Ihren Shop-Namen ersetzen!
	Diesen finden Sie meistens in der URL Ihres Shopify-Adminzugangs. (admin.shopify.com/store/SHOPNAME)

- API-Schlüssel

- API-Password

- Admin-API-Zugriffstoken

Nach dem Anlegen können Sie im Menü des Zugangs auf 'Informationen' klicken. Werden Ihnen dort Shopdaten angezeigt, wurde Ihr API-Zugang erfolgreich angelegt.


***
# bestehende Listings abrufen

![Cronjob für das Zurücklesen](https://data.csv4you.com/media/image/guide/interface/shopify/shopify-einrichtung-cronjob-zuruecklesen.png ':zoom :size=30%')
![Manuelles Starten des Zurücklesens](https://data.csv4you.com/media/image/guide/interface/shopify/shopify-listings-uebersicht.png ':zoom :size=30%')

CSV4YOU muss immer den aktuellen Stand Ihrer Shopify-Listings kennen. Dafür müssen Ihre Shop-Daten in unser System zurückgelesen werden. Dieser Vorgang dient dem Abgleich von CSV4YOU mit Ihrem System. Es werden immer die API-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder per Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite 'Listings->Sonstige' mit der Schaltfläche 'Daten vom Shop einlesen' schreibt nur die Daten für die gerade benutzte Datenquelle. Im Hintergrund werden jedoch ALLE Listings Ihres Shopify-Shops zurückgegeben und ausgewertet.

Das Zurücklesen auf der Seite 'Mein Konto->Grundeinstellungen->API' unter der Auswahl 'Cronjob: Daten vom Shop einlesen', schreibt die Daten für ALLE Datenquellen. Sie müssen also nicht für jede Datenquelle einzeln das Zurücklesen durchführen. Das ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt mit der SKU in Ihrem Shop und der Artikelnummer in CSV4YOU. Ein späterer Abgleich kann nur über die zurückgegebene API-ID erfolgen.

!> Sollten Sie Listings direkt im Shopify gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen. Es werden dabei KEINE Daten im Shopify geändert. Danach können Sie erneut Ihre Shop-Daten zurücklesen.


***
# Kategoriezuordnung

Eine Übersicht der Einstellungen finden Sie [hier](export/categories).

Die Kategoriezuordnungen werden mit einem eigenständigen Exportprofil gesendet. 
Sie müssen dazu bei 'Was möchten Sie zu Shopify übertragen?' die Auswahl auf 'Gelistete Produkte' und 'Collection' setzen.
Kategoriezuordnungen können nur für bereits [gelistete Produkte](/interface/shops/shopify?id=bestehende-listings-abrufen) gesendet werden.


***
# Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).


***
# Export

> Allgemeine Informationen zu den verschiedenen Funktionen der Exportprofile, finden Sie [hier](export/interface).

> Sobald Sie im Shopify mit Lager arbeiten, müssen Sie die Location-ID/Lager-ID angeben. Nur so kann der Bestand geändert werden.

## Exportprofil Neuanlage einrichten

![Exportprofil->Grundeinstellungen](https://data.csv4you.com/media/image/guide/interface/shopify/shopify-exportprofil-neuanlage-grundeinstellungen.png ':zoom :size=30%')
![Exportprofil->Sonstiges](https://data.csv4you.com/media/image/guide/interface/shopify/shopify-exportprofil-neuanlage-sonstiges.png ':zoom :size=30%')

**Richten Sie ein Exportprofil zur Neuanlage mit folgenden Einstellungen ein:**

- Was möchten Sie zu Shopify übertragen?<br>
	1. Auswahl 'Produkte'<br>
	2. Auswahl 'nur neue Produkte'

Nach dem Export einer Produktneuanlage schauen Sie sich die Ihnen angebotenen Statusberichte an. In diesen finden Sie Informationen, ob die Produkte übertragen und angelegt wurden. Wenn das erledigt ist, sollten Sie Ihre aktuellen Shop-Daten in unser System zurücklesen. Das erfolgt im Bereich Listings und der Auswahl des jeweiligen Shops.
Sie können dafür auch einen Cronjob benutzen, den Sie unter den jeweiligen Verbindungseinstellungen Ihres Systems mit CSV4YOU finden.

!> Die Neuanlage ist standardmaßig auf 5000 Produkte begrenzt. Sollten Sie bereits mehr als 50000 Artikel in Ihrem Shopify-Shop haben, reduziert sich dieser Wert auf 1000 Produkte. Desweiteren hat Shopify weitere unterschiedliche Limits für Ihre API-Calls.


## Exportprofil Bestandsupdate einrichten

![Exportprofil->Grundeinstellungen](https://data.csv4you.com/media/image/guide/interface/shopify/shopify-exportprofil-update-bestand-grundeinstellungen.png ':zoom :size=30%')
![Exportprofil->Sonstiges](https://data.csv4you.com/media/image/guide/interface/shopify/shopify-exportprofil-update-bestand-sonstiges.png ':zoom :size=30%')

**Richten Sie ein weiteres Exportprofil zum Bestandsabgleich mit folgenden Einstellungen ein:**

- Was möchten Sie zu Shopify übertragen?<br>
	1. Auswahl 'Bestand'<br>
	2. Auswahl 'Gelistete Produkte'

Durch das Zurücklesen der Shopify-Daten erkennt unser System, welche Produkte einen Bestandsabgleich benötigen. Diese werden durch das Exportprofil in Ihrem Shopify-Shop geändert.

