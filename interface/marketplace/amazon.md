# Amazon

***
# Konto verknüpfen

![Verbindung mit Amazon herstellen](https://data.csv4you.com/media/image/guide/meinkonto/grundeinstellungen/meinkonto-grundeinstellungen-amazon-verbinden.png ':zoom :size=30%')

Für die Verbindung unseres Systems mit Ihrem Amazon-Account benötigen Sie einen eigenen Entwicklerzugang. Weitere Informationen zur Einrichtung finden Sie hier: https://jesseevers.com/selling-partner-api-access/


***
# Kategorie und Artikelmerkmale

### Amazon Kategorie zuweisen

![Kategorie Übersicht](https://data.csv4you.com/media/image/guide/amazon/amazon-kategorie-uebersicht.png ':zoom :size=30%')
![Amazon-Kategorie zuweisen](https://data.csv4you.com/media/image/guide/amazon/amazon-kategorie-amazonkategorie.png ':zoom :size=30%')
![Amazon-Kategorie wurde bereits zugeweisen](https://data.csv4you.com/media/image/guide/amazon/amazon-kategorie-amazonkategorie-vorhanden.png ':zoom :size=30%')

Sie müssen zuerst den internen Kategorien eine Amazon-Kategorie zuordnen. Wenn Sie keine internen Kategorien benutzen, können Sie diese auch dem Produkt selbst zuweisen.

> Wir empfehlen die Amazon-Kategorie zuerst einer internen Kategorie zuzuweisen. Nur mit einer hinterlegten Amazon-Kategorie können Sie Artikelmerkmale zuweisen.


### Artikelmerkmale zuweisen

![Kategorie Übersicht mit Amazon-Kategorie-ID](https://data.csv4you.com/media/image/guide/amazon/amazon-kategorie-artikelmerkmale-uebersicht.png ':zoom :size=30%')
![Artikelmerkmale zuweisen](https://data.csv4you.com/media/image/guide/amazon/amazon-kategorie-artikelmerkmale-eintragen.png ':zoom :size=30%')

Sie müssen zuerst den internen Kategorien Artikelmerkmale zuordnen. Wenn Sie keine internen Kategorien benutzen, können Sie diese auch dem Produkt selbst zuweisen.

> Rote Artikelmerkmale sind Pflichfelder!!

> Wir empfehlen die Artikelmerkmale zuerst den internen Kategorie zuzuweisen. Eine Zuweisung bei den Artikel ist nur bei speziellen Merkmalen nötig, welche zum Beispiel nicht in den Produktdaten vorkommen.


### Artikelmerkmale Im- und Exportieren

![Amazon Artikelmerkmale exportieren](https://data.csv4you.com/media/image/guide/amazon/amazon-kategorie-artikelmerkmale-exportieren.png ':zoom :size=30%')
![Amazon Artikelmerkmale importieren](https://data.csv4you.com/media/image/guide/amazon/amazon-kategorie-artikelmerkmale-importieren.png ':zoom :size=30%')

Sie finden den Menüpunkt 'Import/Export' auf der Seite der Artikelmerkmale. Dort können Sie die Artikelmerkmale exportieren, in einem Texteditor oder ähnlichem bearbeiten und danach wieder importieren.


#### Auswahlmöglichkeiten für den Export

- **passenden Kategorien**<br>
	Es werden alle interne Kategorien mit exportiert, welche der selben Amazon Kategorie zugeordnet sind.

- **passende Produkte**<br>
	Es werden alle Produkte mit exportiert, welche der selben Amazon Kategorie zugeordnet sind.

- **Download als ZIP-Archiv**<br>
	Export als ZIP-Datei


#### Wichtiger Hinweis zum Aufbau der Ex-/Importdatei

Sie können jederzeit manuell Einträge beim Bearbeiten der Exportdatei hinzufügen. Wichtig sind dabei die ersten beiden Spalten.

- **itemno**<br>
	Hier steht die interne Kategorie-ID oder die ID/SKU des Artikels

- **typeof**<br>
	'category' oder 'product', abhängig von der Art des Eintrages


***
# aktuelle Amazon-Listings abrufen

![Einlesen unter 'Listings->Amazon'](https://data.csv4you.com/media/image/guide/amazon/amazon-zuruecklesen-listings.png ':zoom :size=30%')
![Einlesen unter 'Mein Konto->Grundeinstellungen->Amazon'](https://data.csv4you.com/media/image/guide/amazon/amazon-zuruecklesen-meinkonto.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen nur zum Vergleichen.
Es werden immer die Amazon-ASIN sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder mit einem Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite `Listings->Amazon`mit dem Button `Daten von Amazon einlesen` schreibt nur die Daten für die gerade benutzte Datenquelle.
Es werden trotzdem im Hintergrund ALLE Listings von Amazon zurückgegeben.

Das Zurücklesen auf der Seite `Mein Konto->Grundeinstellungen->Amazon` unter der Auswahl `Cronjob: Daten von Amazon einlesen`, schreibt die Daten für ALLE Datenquellen.
Sie müssen also nicht für jede Datenquelle das Zurücklesen durchführen. Dieses ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt immer mit der SKU bei Amazon und der ausgewählten Artikelnummer im CSV4YOU.

> Sollten Sie Listings direkt bei Amazon oder mit anderen Systemen gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen.
Es werden KEINE Daten bei Amazon geändert. Danach können Sie erneut zurücklesen.


***
# Produkte an Amazon übermitteln - Export

Dieser Abschnitt betrifft spezielle Einstellungen für Amazon im Bereich [Sonstiges](http://guide.csv4you.com/#/export/interface?id=sonstiges) des Exportprofiles.


### Amazon-Marktplatz auswählen

![Amazon-Marktplatz auswählen](https://data.csv4you.com/media/image/guide/amazon/exportprofil/amazon-exportprofil-einstellungen.png ':zoom :size=30%')

Sie müssen zuerst einen Amazon-Marktplatz auswählen, in den Sie Ihre Produkte einstellen möchten. Weitere Einstellmöglichkeiten erscheinen nach dem Speichern des Marktplatzes.


### Einstellungen vornehmen

![Amazon-Marktplatz auswählen](https://data.csv4you.com/media/image/guide/amazon/exportprofil/amazon-exportprofil-einstellungen-2.png ':zoom :size=30%')

> Die nachfolgenden Punkte müssen ausgefüllt werden, bevor Sie Produktdaten an Amazon senden.

- **Amazon Land**<br>
	Auswahl des Amazon-Marktplatzes, wo Sie Ihre Produkte einstellen möchten

- **Art der Übertragung**<br>
	- **Update/PartialUpdate**<br>
        Produktdaten werden übertragen. Artikelmerkmale und Kategoriezuweisungen sind zwingend notwendig.
	- **EasyProduct **<br>
		Produkte werden übertragen und setzen sich dabei auf bereits vorhandene Produkte im Amazon.
		Zuweisung erfolgt standardmäßig über die EAN/ISBN. Es werden keine Artikelmerkmale oder Kategoriezuweisungen für Amazon benötigt.
	- **Delete **<br>
		Produkte werden gelöscht

> Preiskalkulation und Produkttemplate, wenn benötigt, sollten auf der Seite Grundeinstellungen bereits ausgewählt sein.
Amazon-Kategoriezuordnung und Zuweisung der passenden Artikelmerkmale haben Sie auch bereits durchgeführt.


***
# Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).


***
# Produkte für den Export sperren

![Produkte für Marktplätze sperren/freischalten](https://data.csv4you.com/media/image/guide/amazon/product/amazon-product-sperren.png ':zoom :size=30%')
![Ansicht gesperrte Artikel](https://data.csv4you.com/media/image/guide/amazon/product/amazon-product-sperren-2.png ':zoom :size=30%')

Sie können im Abschnitt `Amazon` der Einstellungen des Produktes angeben, ob ein Produkt auf bestimmten Marktplätzen gesperrt werden soll.
Diese Produkte werden dann bei der Übertragung zu Amazon nicht übermittelt.