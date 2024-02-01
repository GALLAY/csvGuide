# OTTO Marketplace

***
# Konto verknüpfen

![Verbindung mit der OTTO-API herstellen](https://data.csv4you.com/media/image/guide/interface/otto/otto-api-zugangsdaten-hinterlegen.png ':zoom :size=30%')

Verbinden Sie unter `Mein Konto->Grundeinstellungen->API` mit den korrekten Zugangsdaten Ihren OTTO-Shop.
Nach dem Anlegen können Sie im Menü des Zugangs auf `Informationen` klicken. Werden Ihnen dort Shopdaten angezeigt, wurde Ihr API-Zugang erfolgreich angelegt.


***
# Kategorie zuweisen

![Kategorie Übersicht](https://data.csv4you.com/media/image/guide/interface/otto/otto-kategorie-uebersicht.png ':zoom :size=30%')
![OTTO Market-Kategorie zuweisen](https://data.csv4you.com/media/image/guide/interface/otto/otto-kategorie-ottokategorie.png ':zoom :size=30%')
![OTTO Market-Kategorie wurde bereits zugeweisen](https://data.csv4you.com/media/image/guide/interface/otto/otto-kategorie-ottokategorie-vorhanden.png ':zoom :size=30%')

Sie müssen zuerst den internen Kategorien eine OTTO Market-Kategorie zuordnen. Wenn Sie keine internen Kategorien benutzen, können Sie diese auch dem Produkt selbst zuweisen.
Geben Sie dazu einfach eine Suchbegriff in das Kategoriefeld. Es werden Ihnen sofort die möglichen OTTO-Kategorien angezeigt. Speichern Sie die gewünschte Kategorie und Sie können im Anschluss die benötigten Artikelmerkmale ausfüllen.

> Wir empfehlen die OTTO Market-Kategorie zuerst einer internen Kategorie zuzuweisen. Nur mit einer hinterlegten OTTO Market-Kategorie können Sie Artikelmerkmale zuweisen.


***
# Artikelmerkmale

![Kategorie Übersicht mit OTTO Market-Kategorie-ID](https://data.csv4you.com/media/image/guide/interface/otto/otto-kategorie-artikelmerkmale-uebersicht.png ':zoom :size=30%')
![Artikelmerkmale zuweisen](https://data.csv4you.com/media/image/guide/interface/otto/otto-kategorie-artikelmerkmale-eintragen.png ':zoom :size=30%')

Sie müssen zuerst den internen Kategorien Artikelmerkmale zuordnen. Wenn Sie keine internen Kategorien benutzen, können Sie diese auch dem Produkt selbst zuweisen.

!> Rote Artikelmerkmale sind Pflichtfelder!!

Sollte ein Artikelmerkmal mehrere Werte zulassen, so trennen Sie diese mit einer Doppel-Pipe(||).

> Wir empfehlen die Artikelmerkmale zuerst den internen Kategorien zuzuweisen. Eine Zuweisung bei den Artikeln ist nur bei speziellen Merkmalen nötig, welche zum Beispiel nicht in den Produktdaten vorkommen.


***
# bestehende Listings abrufen

![Einlesen unter 'Listings->Sonstige'](https://data.csv4you.com/media/image/guide/interface/otto/otto-zuruecklesen-listings.png ':zoom :size=30%')
![Einlesen unter 'Mein Konto->Grundeinstellungen->API'](https://data.csv4you.com/media/image/guide/interface/otto/otto-zuruecklesen-meinkonto.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen nur zum Vergleichen.
Es werden immer die OTTO-Listings-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder mit einem Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite `Listings->Sonstiges->OTTO`mit dem Button `Daten vom Shop einlesen` schreibt nur die Daten für die gerade benutzte Datenquelle.
Es werden trotzdem im Hintergrund ALLE Listings von OTTO zurückgegeben.

Das Zurücklesen auf der Seite `Mein Konto->Grundeinstellungen->API` unter der Auswahl `Cronjob: Daten von OTTO einlesen`, schreibt die Daten für ALLE Datenquellen.
Sie müssen also nicht für jede Datenquelle das Zurücklesen durchführen. Dieses ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt fast immer mit der SKU bei OTTO und der Artikelnummer im CSV4YOU.

> Sollten Sie Listings direkt auf dem OTTO gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen.
Es werden KEINE Daten in OTTO geändert. Danach können Sie erneut zurücklesen.


***
# Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).


***
# Export

> Allgemeine Informationen zu den verschiedenen Funktionen der Exportprofile, finden Sie [hier](export/interface).

!> Bestände werden getrennt von den Produktdaten übertragen.

### Wichtige Hinweise

- **Bilder** müssen eine Auflösung von mindesten 960x480 Pixel aufweisen. Maximale Kantenlänge darf 4500 Pixel nicht überschreiten.<br>
- Die Spalte **brandId** unter eigene Spaltenzuordnung muss ausgefüllt sein.<br>
- Größenangaben sollten immer in Dezimalform übertragen werden. Bsp: statt `40cm` muss es nur `40` lauten.


## Exportprofil Neuanlage einrichten

![Exportprofil->Grundeinstellungen](https://data.csv4you.com/media/image/guide/interface/otto/otto-exportprofil-neuanlage-grundeinstellungen.png ':zoom :size=30%')
![Exportprofil->Sonstiges](https://data.csv4you.com/media/image/guide/interface/otto/otto-exportprofil-neuanlage-sonstiges.png ':zoom :size=30%')

**Richten Sie ein Exportprofil zur Neuanlage mit folgenden Einstellungen ein:**

- Was möchten Sie zu Otto übertragen?<br>
	1. Auswahl 'Produkte'<br>
	2. Auswahl 'nur neue Produkte'

Nach dem Export einer Produktneuanlage schauen Sie sich die Ihnen angebotenen Statusberichte an. In diesen finden Sie Informationen, ob die Produkte übertragen und angelegt wurden. Wenn das erledigt ist, sollten Sie Ihre aktuellen Shop-Daten in unser System zurücklesen. Das erfolgt im Bereich Listings und der Auswahl des jeweiligen Shops.
Sie können dafür auch einen Cronjob benutzen, den Sie unter den jeweiligen Verbindungseinstellungen Ihres Systems mit CSV4YOU finden.


## Exportprofil Bestandsupdate einrichten

![Exportprofil->Grundeinstellungen](https://data.csv4you.com/media/image/guide/interface/otto/otto-exportprofil-update-bestand-grundeinstellungen.png ':zoom :size=30%')
![Exportprofil->Sonstiges](https://data.csv4you.com/media/image/guide/interface/otto/otto-exportprofil-update-bestand-sonstiges.png ':zoom :size=30%')

**Richten Sie ein weiteres Exportprofil zum Bestandsabgleich mit folgenden Einstellungen ein:**

- Was möchten Sie zu Otto übertragen?<br>
	1. Auswahl 'Bestand'<br>
	2. Auswahl 'Gelistete Produkte'

Durch das Zurücklesen der Otto-Daten erkennt unser System, welche Produkte einen Bestandsabgleich benötigen. Diese werden durch dieses Exportprofil in Ihrem Otto-Account geändert.


***
# Statusbericht des letzten Exportes

![Ansicht 1: gesendete Produkte](https://data.csv4you.com/media/image/guide/api/otto/status/otto-export-status.png ':zoom :size=30%')
![Ansicht 2: nähere Statusangaben zu einem einzelnen Produkt](https://data.csv4you.com/media/image/guide/api/otto/status/otto-export-status-2.png ':zoom :size=30%')

Mit einem Klick auf den Button 'Letzter Statusbericht' kommen Sie zu den Responsedaten des letzten Exportes zu Otto. Hier werden Ihnen alle fehlenden oder falschen Daten angezeigt.


#### Sie erhalten die Statusfehlermeldung 'unchanged'

Wenn Sie Daten zu OTTO exportieren, welche bereits vorhanden sind oder Sie nacheinander mehrmals die selben Daten senden, kommt die Statusmeldung 'unchanged'.
OTTO hat dann nichts angelegt oder geändert. Versuchen Sie daher, die zu sendenen Daten abzuändern.
Lassen Sie bei der Übertragung zum Beispiel einen Wert weg, indem Sie unter 'eigene Spaltenzuordnung' des Exportprofiles nur die Werte auswählen, welche Sie senden möchten.
Sie können auch einfach einen Artikelwert umschreiben.


***
# Produkte für den Export sperren

![Produkte für Marktplätze sperren/freischalten](https://data.csv4you.com/media/image/guide/api/otto/product/otto-product-sperren.png ':zoom :size=30%')
![Ansicht gesperrte Artikel](https://data.csv4you.com/media/image/guide/api/otto/product/otto-product-sperren-2.png ':zoom :size=30%')

Sie können im Abschnitt 'OTTO' der Einstellungen des Produktes angeben, ob ein Produkt für den Export gesperrt werden soll. Diese Produkte werden dann bei der Übertragung zu OTTO nicht übermittelt.