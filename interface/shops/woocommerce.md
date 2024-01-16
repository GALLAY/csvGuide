# WooCommerce

***
# Konto verknüpfen

![Verbindung mit der WooCommerce-API herstellen](https://data.csv4you.com/media/image/guide/interface/woocommerce/woocommerce-api-zugangsdaten-hinterlegen.png ':zoom :size=30%')

Hinterlegen Sie unter 'Mein Konto->Grundeinstellungen->API' die passenden Zugangsdaten für Ihren WooCommerce-Shop. Diese erhalten Sie aus Ihrem WooCommerce-Konto.
Sollten Ihnen die Daten nicht vorliegen, wenden Sie sich bitte an der WooCommerce-Support.

Nach dem Anlegen können Sie im Menü des Zugangs auf 'Informationen' klicken. Werden Ihnen dort Shopdaten angezeigt, wurde Ihr API-Zugang erfolgreich angelegt.


***
# bestehende Listings abrufen

![Cronjob für das Zurücklesen](https://data.csv4you.com/media/image/guide/interface/woocommerce/woocommerce-einrichtung-cronjob-zuruecklesen.png ':zoom :size=30%')
![Manuelles Starten des Zurücklesens](https://data.csv4you.com/media/image/guide/interface/woocommerce/woocommerce-listings-uebersicht.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer bestehenden WooCommerce-Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen nur zum Vergleichen. Es werden immer die API-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder mit einem Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite 'Listings->Sonstige' mit dem Button 'Daten vom Shop einlesen' schreibt nur die Daten für die gerade benutzte Datenquelle. Es werden trotzdem im Hintergrund ALLE Listings von Ihrem WooCommerce-Shop zurückgegeben.

Das Zurücklesen auf der Seite 'Mein Konto->Grundeinstellungen->API' unter der Auswahl 'Cronjob: Daten vom Shop einlesen', schreibt die Daten für ALLE Datenquellen. Sie müssen also nicht für jede Datenquelle das Zurücklesen durchführen. Dieses ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt mit der SKU in Ihrem Shop und der Artikelnummer in CSV4YOU. Ein späterer Abgleich kann nur über die zurückgegebene API-ID erfolgen.

!> Sollten Sie Listings direkt im WooCommerce gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen. Es werden dabei KEINE Daten im WooCommerce geändert. Danach können Sie erneut Ihre Shop-Daten zurücklesen.


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

![Exportprofil->Grundeinstellungen](https://data.csv4you.com/media/image/guide/interface/woocommerce/woocommerce-exportprofil-neuanlage-grundeinstellungen.png ':zoom :size=30%')
![Exportprofil->Sonstiges](https://data.csv4you.com/media/image/guide/interface/woocommerce/woocommerce-exportprofil-neuanlage-sonstiges.png ':zoom :size=30%')

**Richten Sie ein Exportprofil zur Neuanlage mit folgenden Einstellungen ein:**

- Was möchten Sie zu WooCommerce  übertragen?<br>
	1. Auswahl 'Produkte'<br>
	2. Auswahl 'nur neue Produkte'

Nach dem Export einer Produktneuanlage schauen Sie sich die Ihnen angebotenen Statusberichte an. In diesen finden Sie Informationen, ob die Produkte übertragen und angelegt wurden. Wenn das erledigt ist, sollten Sie Ihre aktuellen Shop-Daten in unser System zurücklesen. Das erfolgt im Bereich Listings und der Auswahl des jeweiligen Shops.
Sie können dafür auch einen Cronjob benutzen, den Sie unter den jeweiligen Verbindungseinstellungen Ihres Systems mit CSV4YOU finden.


## Exportprofil Bestandsupdate einrichten

![Exportprofil->Grundeinstellungen](https://data.csv4you.com/media/image/guide/interface/woocommerce/woocommerce-exportprofil-update-bestand-grundeinstellungen.png ':zoom :size=30%')
![Exportprofil->Sonstiges](https://data.csv4you.com/media/image/guide/interface/woocommerce/woocommerce-exportprofil-update-bestand-sonstiges.png ':zoom :size=30%')

**Richten Sie ein weiteres Exportprofil zum Bestandsabgleich mit folgenden Einstellungen ein:**

- Was möchten Sie zu WooCommerce übertragen?<br>
	1. Auswahl 'Bestand'<br>
	2. Auswahl 'Gelistete Produkte'

Durch das Zurücklesen der WooCommerce-Daten erkennt unser System, welche Produkte einen Bestandsabgleich benötigen. Diese werden durch dieses Exportprofil in Ihrem WooCommerce-Shop geändert.


## Exportprofil Bilderupdate einrichten

![Exportprofil->Grundeinstellungen](https://data.csv4you.com/media/image/guide/interface/woocommerce/woocommerce-exportprofil-update-bilder-grundeinstellungen.png ':zoom :size=30%')
![Exportprofil->Sonstiges](https://data.csv4you.com/media/image/guide/interface/woocommerce/woocommerce-exportprofil-update-bilder-sonstiges.png ':zoom :size=30%')

**Richten Sie ein weiteres Exportprofil zum Bestandsabgleich mit folgenden Einstellungen ein:**

- Was möchten Sie zu WooCommerce übertragen?<br>
	1. Auswahl 'Bilder'<br>
	2. Auswahl 'Gelistete Produkte'

Durch das Zurücklesen der WooCommerce-Daten erkennt unser System, welche Produkte einen Bestandsabgleich benötigen. Diese werden durch dieses Exportprofil in Ihrem WooCommerce-Shop geändert.