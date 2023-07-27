# eBay

***
# Konto verknüpfen

![Verbindung mit eBay herstellen](https://data.csv4you.com/media/image/guide/meinkonto/grundeinstellungen/meinkonto-grundeinstellungen-ebay-verbinden.png ':zoom :size=30%')

Die Einrichtung der eBay-Verbindung ist notwendig, um Daten zwischen eBay und CSV4YOU austauschen zu können. Dabei wird eine sichere OAUTH-Verbindung erstellt, welche bei Erfolg einen gültigen TOKEN zurück gibt.


***
# Kategorie und Artikelmerkmale

### eBay Kategorie zuweisen

![Kategorie Übersicht](https://data.csv4you.com/media/image/guide/ebay/ebay-kategorie-uebersicht.png ':zoom :size=30%')
![eBay-Kategorie zuweisen](https://data.csv4you.com/media/image/guide/ebay/ebay-kategorie-ebaykategorie.png ':zoom :size=30%')
![eBay-Kategorie wurde bereits zugeweisen](https://data.csv4you.com/media/image/guide/ebay/ebay-kategorie-ebaykategorie-vorhanden.png ':zoom :size=30%')

Sie müssen zuerst den internen Kategorien eine eBay-Kategorie zuordnen. Wenn Sie keine internen Kategorien benutzen, können Sie diese auch dem Produkt selbst zuweisen.

> Wir empfehlen die eBay-Kategorie-ID zuerst einer internen Kategorie zuzuweisen. Nur mit einer hinterlegten eBay-Kategorie können Sie Artikelmerkmale zuweisen.


### Artikelmerkmale zuweisen

![Kategorie Übersicht mit eBay-Kategorie-ID](https://data.csv4you.com/media/image/guide/ebay/ebay-kategorie-artikelmerkmale-uebersicht.png ':zoom :size=30%')
![Artikelmerkmale zuweisen](https://data.csv4you.com/media/image/guide/ebay/ebay-kategorie-artikelmerkmale-eintragen.png ':zoom :size=30%')

Sie müssen zuerst den internen Kategorien Artikelmerkmale zuordnen. Wenn Sie keine internen Kategorien benutzen, können Sie diese auch dem Produkt selbst zuweisen.

> Rote Artikelmerkmale sind Pflichfelder!!

> Wir empfehlen die Artikelmerkmale zuerst den internen Kategorie zuzuweisen. Eine Zuweisung bei den Artikel ist nur bei speziellen Merkmalen nötig, welche zum Beispiel nicht in den Produktdaten vorkommen.

> Sollten Sie mit dem CSV-Manager und Variantenartikel arbeiten, benötigen die Parents eigenständige Artikelmerkmale.


### Artikelmerkmale Im- und Exportieren

![eBay Artikelmerkmale exportieren](https://data.csv4you.com/media/image/guide/ebay/ebay-kategorie-artikelmerkmale-exportieren.png ':zoom :size=30%')
![eBay Artikelmerkmale importieren](https://data.csv4you.com/media/image/guide/ebay/ebay-kategorie-artikelmerkmale-importieren.png ':zoom :size=30%')

Sie finden den Menüpunkt 'Import/Export' auf der Seite der Artikelmerkmale. Dort können Sie die Artikelmerkmale exportieren, in einem Texteditor oder ähnlichem bearbeiten und danach wieder importieren.

#### Auswahlmöglichkeiten für den Export

- **passenden Kategorien**<br>
	Es werden alle interne Kategorien mit exportiert, welche der selben eBay Kategorie zugeordnet sind.

- **passende Produkte**<br>
	Es werden alle Produkte mit exportiert, welche der selben eBay Kategorie zugeordnet sind.

- **Download als ZIP-Archiv**<br>
	Export als ZIP-Datei


#### Wichtiger Hinweis zum Aufbau der Ex-/Importdatei

Sie können jederzeit manuell Einträge beim Bearbeiten der Exportdatei hinzufügen. Wichtig sind dabei die ersten beiden Spalten.

- **itemno**<br>
	Hier steht die interne Kategorie-ID oder die ID/SKU des Artikels

- **typeof**<br>
	'category' oder 'product', abhängig von der Art des Eintrages


***
# aktuelle eBay-Listings abrufen

![Einlesen unter 'Listings->eBay'](https://data.csv4you.com/media/image/guide/ebay/ebay-zuruecklesen-listings.png ':zoom :size=30%')
![Einlesen unter 'Mein Konto->Grundeinstellungen->eBay'](https://data.csv4you.com/media/image/guide/ebay/ebay-zuruecklesen-meinkonto.png ':zoom :size=30%')

Um immer einen aktuellen Stand Ihrer Listings zu haben, müssen diese Daten in unser System zurückgelesen werden. Diese Daten dienen nur zum Vergleichen.
Es werden immer die eBay-Listings-ID sowie Preis und Bestand benötigt. Sie können das Zurücklesen manuell durchführen oder mit einem Cronjob erledigen lassen.

Ein Zurücklesen auf der Seite `Listings->eBay`mit dem Button `Daten von eBay einlesen` schreibt nur die Daten für die gerade benutzte Datenquelle.
Es werden trotzdem im Hintergrund ALLE Listings von eBay zurückgegeben.

Das Zurücklesen auf der Seite `Mein Konto->Grundeinstellungen->eBay` unter der Auswahl `Cronjob: Daten von eBay einlesen`, schreibt die Daten für ALLE Datenquellen.
Sie müssen also nicht für jede Datenquelle das Zurücklesen durchführen. Dieses ist aber nur möglich, wenn Sie einen Cronjob hierfür eingerichtet haben.

> Ein Abgleich erfolgt immer mit der SKU(Bestandseinheit) bei eBay und der ausgewählten Artikelnummer im CSV4YOU.

> Sollten Sie Listings direkt bei eBay oder mit anderen Systemen gelöscht haben, empfehlen wir die vorhandenen Zuweisungen in unserem System zu entfernen.
Es werden KEINE Daten bei eBay geändert. Danach können Sie erneut zurücklesen.


### Möglichkeiten des Zurücklesens

- **Inventoryfile**<br>
	Es werden alle aktiven Listings in einer Datei von eBay zur Verfügung gestellt. Die Erstellung dieser Datei auf den eBay-Servern kann unter Umständen etwas länger dauern.
	Es kann bei der Erstellung zu Abbrüchen auf Seiten von eBay kommen, welche uns nicht mitgeteilt werden. Das Einlesen wird dann nicht ausgeführt. Eine Unterscheidung der Listings auf unterschiedliche Marktplätze erfolgt nicht, da diese Datei keine Informationen dazu beinhaltet.

- **Sofort - Sofortiges Einlesen**<br>
	Schnelle Abarbeitung, je nach Anzahl der Listings, da eBay die Daten sofort zurück gibt.

- **Sofort(nur Vorbereitete) - Sofortiges Einlesen nur der vorbereiteten Produkte**<br>
	Wenn Sie Produkte neu an eBay übertragen haben, können Sie diese damit zurücklesen. Diese Auswahl steht Ihnen nur unter `Listings->eBay` zur Verfügung.


***
# Produkte an eBay übermitteln - Export

Dieser Abschnitt betrifft spezielle Einstellungen für eBay im Bereich [Sonstiges](http://guide.csv4you.com/#/export/interface?id=sonstiges) des Exportprofiles.


### eBay-Marktplatz auswählen

![eBay-Marktplatz auswählen](https://data.csv4you.com/media/image/guide/ebay/exportprofil/ebay-exportprofil-einstellungen.png ':zoom :size=30%')

Sie müssen zuerst einen eBay-Marktplatz auswählen, in den Sie Ihre Produkte einstellen möchten. Weitere Einstellmöglichkeiten erscheinen nach dem Speichern des Marktplatzes.


### Einstellungen vornehmen

![eBay-Marktplatz auswählen](https://data.csv4you.com/media/image/guide/ebay/exportprofil/ebay-exportprofil-einstellungen-2.png ':zoom :size=30%')

> Die nachfolgenden Punkte müssen ausgefüllt werden, bevor Sie Produktdaten an eBay senden.

- **eBay Land**<br>
	Auswahl des eBay-Marktplatzes, wo Sie Ihre Produkte einstellen möchten

- **Format/Dauer der Listings**<br>
	Auswahl des Angebotformates und deren Laufzeit

- **Art des Listings**<br>
	Wollen Sie Listings neu anlegen, Updaten oder Beenden?

- **Was möchten Sie zu eBay übertragen?**<br>
	Auswahl der zu übertragenden Produktinformationen

- **Übertragungsart**<br>
	- **Single**<br>Produkte werden einzeln übertragen und sofort von eBay verarbeitet. Dadurch kann der Export länger dauern. Empfehlung nur bis 1000 Produkte
	- **Multi**<br>alle Produktdaten werden gesammelt und am Ende in einem Schritt an eBay übermittelt

- **Rahmenbedingungen für Zahlungen, Rücksendungen, Versand**<br>
	Diese werden zuerst in Ihrem eBay-Konto gespeichert und können im Anschluss hier, mit einem Klick auf die Lupe, ausgewählt werden.

> Preiskalkulation und Produkttemplate, wenn benötigt, sollten auf der Seite Grundeinstellungen bereits ausgewählt sein. eBay-Kategoriezuordnung und Zuweisung der passenden Artikelmerkmale haben Sie auch bereits durchgeführt.


***
# Preiskalkulation

Eine Übersicht der Einstellungen finden Sie [hier](export/pricecalculation).


***
# Produkte für den Export sperren

![Produkte für Marktplätze sperren/freischalten](https://data.csv4you.com/media/image/guide/ebay/product/ebay-product-sperren.png ':zoom :size=30%')
![Ansicht gesperrte Artikel](https://data.csv4you.com/media/image/guide/ebay/product/ebay-product-sperren-2.png ':zoom :size=30%')

Sie können im Abschnitt `eBay` der Einstellungen des Produktes angeben, ob ein Produkt auf bestimmten Marktplätzen gesperrt werden soll. Diese Produkte werden dann bei der Übertragung zu eBay nicht übermittelt.