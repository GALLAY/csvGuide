# Data Import

The data import offers you the possibility to take over any product data from CSV, XML or other files as master data into the datapool or to import data from different sources.
Import data can be read in from different sources. Select one of the options.

> Stocks are imported in a separate import, not with the product import. Products must already exist in the datapool.

***
# Step 1: Import Options

Select a file and - if already available - a suitable template. Import templates allow you to save the assignments between the fields in your import file and the fields in the datapool. This means that the individual field assignments do not have to be set up again for each import. Importing data can thus be repeated very quickly and as often as you like. If you change existing assignments during the import, the import template used will also be changed.

> If you are importing an XML file, a tick must be set in the XML data field.

> MS Excel files should not contain macros or calculations. Otherwise errors may occur during import.

> File names must not contain any special characters or umlauts!

## Option A: Select file for upload

Load an import file from your local computer.

![Option A - Select a file from PC](https://data.csv4you.com/media/image/guide/datenimport-produkte/datenpool-datenimport-variante-a-update.png ':zoom :size=30%')

## Option B: Upload file from URL

Enter an HTTP or FTP address. For importing from an FTP server, you must enter the necessary information under My Account ->Base Settings ->FTP data.

![Option B - Upload File from URL](https://data.csv4you.com/media/image/guide/datenimport-produkte/datenpool-datenimport-variante-b-update.png ':zoom :size=30%')

## Option C: Load Internal Supplier Data

If data of a supplier has already been released for you on csv4you, you can import the corresponding product data as a new data source here.

![Option C: Load Internal Supplier Data (optional)](https://data.csv4you.com/media/image/guide/datenimport-produkte/datenpool-datenimport-variante-c-update.png ':zoom :size=30%')


***
# Schritt 2: Datei wurde geladen

Legen Sie die Eigenschaften für die zu importierende Datei fest. Je nach Datei können die angezeigten Eigenschaften variieren. Es wird Ihnen auch der Dateiname und die Anzahl der temporär erkannten Datensätze angezeigt.

> Artikelnummer (SKU) darf maximal 50 Zeichen lang sein. Darüber hinaus gehende Zeichen werden beim Import abgeschnitten.


## Allgemeine Einstellungen

- **Datei-Typ (Inhalt)**<br>
    Wählen Sie den Typ Datei, der importiert werden soll:

    - **Kategorie**<br>Import von Kategorien
    - **Produkt**<br>Import und Aktualisierung von Produkt- und Kategoriedaten
    - **Inventar**<br>Aktualisierung von Bestandsdaten (erst sichtbar, wenn bereits Produkte angelegt wurden)
    - **Preis**<br>Aktualisierung von Preisen (erst sichtbar, wenn bereits Produkte angelegt wurden)

#### Sollten Sie noch keine Importvorlage haben oder keine benutzen wollen, dann müssen die nachfolgenden Einstellungen gesetzt werden.

- **Trennzeichen Datenfeld**<br>
	Spaltentrenner festlegen
    > Beim Import von MS-Excel-Dateien bitte den Tabulator als Trennzeichen markieren.

- **Texterkennungszeichen**<br>
	Texterkennungszeichen eingeben (falls verwendet)

- **Spaltennamen stehen in Zeile**<br>
	Hier die Zeile angeben, in der die Spaltennamen stehen (nicht immer ist es die 1. Zeile)

#### Wenn Sie eine vorhandene Importvorlage benutzen wollen, dann müssen Sie diese mit nachfolgender Einstellung auswählen.

- **Vorlage Spaltenzuordnung**<br>
    Bitte beachten Sie, dass eine gewählte Vorlage für die Spaltenzuordnung zum Dateiformat passen sollte.
	> Wenn noch keine Importvorlage hinterlegt ist, ist diese Einstellung nicht sichtbar.

#### XML-Einstellungen

- **XML-Element der Produktdaten**<br>
    Hier sollte das XML-Element ausgewählt sein, welches die Produktdaten enthält.

- **Varianten**<br>
    Gibt es zusätzlich Variantenartikel, ordnen Sie bitte das entsprechende XML-Feld zu.

Drücken Sie dann auf die Schaltfläche `Diese Einstellungen übernehmen`.


***
# Schritt 3: Feldzuweisungen und Importoptionen

## Stammdaten-Zuweisung

![Stammdaten-Zuweisung](https://data.csv4you.com/media/image/guide/datenimport-produkte/datenpool-datenimport-stammdatenzuweisung.png ':zoom :size=30%')

Ihre Spalteninhalte den Feldern im Datenpool zuweisen

- **Spaltenname in Datenbank**<br>
    Liste aller verfügbaren Felder im System
    Maximal 20 weitere Felder lassen sich über Mein Konto ->Grundeinstellungen ->Datenquellen ->Aktionen ... Freifelder definieren. Diese sollten dann hier als Feldnamen erscheinen.

- **Spalten der Datei**<br>
    Spaltennamen Ihrer Importdatei
    Ordnen Sie die Spaltennamen Ihrer Importdatei dem entsprechenden Feld im Datenpool zu. Kategorien lassen sich ebenfalls über den Produktimport anlegen und aktualisieren. Eventuelle Leerzeichen im Feld ID werden automatisch in Unterstriche umgewandelt.

- **erweiterte Optionen**<br>
    Hier können Sie einem Feld einen festen Wert als Inhalt zuweisen, z.B. NEU.
    Außerdem lassen sich mehrere Spalteninhalte aus Ihrer Importdatei einem Wert im Datenpool zuordnen. Setzen Sie Ihre Feldnamen dazu in eckige Klammern. Beispiel: [title] - [EAN]


## weitere Sprachen

Falls Sie zusätzliche Sprachen freigeschaltet haben, dann werden diese hier angezeigt.

## Extern

![Externe Anbieter zuweisen(optional)](https://data.csv4you.com/media/image/guide/datenimport-produkte/datenpool-datenimport-externzuweisung.png ':zoom :size=30%')

Weisen Sie hier Daten von externen Anbietern, Marktplätzen oder Shopsystemen zu. Das können ID´s der externen Datensätze oder Artikelmerkmale im JSON-Format sein.

## Import-Optionen

### Produkt

![Import-Optionen](https://data.csv4you.com/media/image/guide/datenimport-produkte/datenpool-datenimport-importoptionen-update.png ':zoom :size=30%')

- **Fehlende Produkte im Datenpool anlegen**<br>
    Werden Produkte beim Import gefunden, die noch nicht im Datenpool vorhanden sind, so werden diese neu angelegt (Produkte mit geänderter Produkt-ID sind ebenfalls neue Artikel). Deaktivieren Sie diese Option, wenn z.B. nur ein Update von bereits vorhandenen Produkten erfolgen soll.

- **Datensätze auch ohne eigene ID**<br>
    Enthält Ihre Importdatei Datensätze ohne eigene ID, so markieren Sie bitte diese Option.
    Standardmäßig werden nur Datensätze mit eindeutiger ID importiert.

- **Formatierungen aus den Texten entfernen!**<br>
    Sämtlicher HTML-Code wird aus den importierten Daten entfernt.

- **Wenn UPDATE: Fehlende Spalten ignorieren!**<br>
    Nur zutreffend für UPDATES: Wenn Sie nur bestimmte 'Spalten' Ihres Datenpools aktualisieren möchten, sollte die Option aktiviert sein. Es werden dann nur die für den betreffenden Import ausgewählten Spalten Ihres Datenpools aktualisiert. Beispiel:
    Ihr Datenpool enthält 20 Spalten mit verschiedenen Werten, Sie möchten aber nur die Spalte TITEL und EAN aktualisieren, z.B. weil sich einige Produkttitel Ihres Angebots geändert haben und aktualisiert werden müssten. Markieren Sie dann die Option hier und importieren Sie nur die Spalten EAN und TITEL. EAN-Nummern sollten sich natürlich nicht geändert haben, damit eine korrekte Zuordnung der neuen Titel erfolgen kann.

- **Kategorien aus Importdatei übernehmen**<br>
    Enthält Ihre Importdatei Produktkategorien, so können Sie diese als interne Kategorien im Datenpool übernehmen. Bei erneuten Importen werden bereits vorhandene Daten aktualisiert. Neu hinzugekommene interne Kategorien werden neu angelegt. Voraussetzung ist die Zuweisung von Kategorien in den Feldern externe Kategorie 1 - 5.

- **Sicherung der alten Daten vor dem Import erstellen**<br>
    Vor dem Import wird eine Sicherung der vorhandenen Daten erstellt.

- **Währungsumrechnung**<br>
    Umrechnung der Preise aus der Datei in EUR. Sie müssen dazu die Ausgangswährung auswählen.
    Übernehmen Sie hier bitte immer die Einstellung Standard! Stellen Sie nur dann auf eine bestimmte Währung um, wenn Sie sicher sind was die Funktion bewirkt.

- **Als Importvorlage speichern unter**<br>
    Speichern Sie Ihre Importeinstellungen als Vorlage unter einem aussagekräftigen Namen, z.B. 'IMPORT-Vorlage XTCommerce' (falls Sie hier nichts eingeben wird default verwendet). So müssen Sie bei wiederholten Importen die Spaltenzuweisungen nicht immer wieder neu vornehmen, sondern wählen dazu nur die passende Importvorlage aus. Auch die Aktualisierung einer bereits bestehenden Spaltenzuordnung ist hier möglich.
	> Für den automatischen Import von Daten per Cronjob ist das Anlegen und Zuweisen einer Importvorlage zwingende Voraussetzung!

- **Als neue Export-Schnittstelle anlegen**<br>
    Wenn aktiv, wird anhand der importierten Spalten eine individuelle Schnittstelle generiert (siehe Export ->Individuelle Schnittstellen).


### Inventar

- **Alle Lagerbestände vor dem Import auf 0 setzen**<br>
    Es gibt Lieferanten, welche nicht mehr vorhandene Artikel auch nicht in Ihren Produktdateien führen. Wenn das so ist, dann können vorhandene Bestände im Datenpool nicht geupdatet werden. Dadurch kann es später zu Überverkäufen kommen.
	Diese Funktion sorgt dafür, das bei einem Import erst alle Bestände dieser Datenquelle geleert werden. Danach werden nur die Bestände geschrieben, welche auch tatsächlich in der Importdatei vorkommen.
	> Wenn markiert, werden die Bestände ALLER Datensätze in der Datenquelle vor dem Import auf den Wert 0 gesetzt.

- **Sicherheit vor NULL-Beständen**<br>
    Ist die Anzahl der Produkte mit einem NULL-Bestand in der Importdatei größer dieser Prozentauswahl im Vergleich zum aktuellen Bestand in der Datenquelle, werden die Bestände nicht übernommen. Dies könntet auf einen Fehler beim Import hindeuten. Diese Einstellung funktioniert nur mit Aktivierung von 'Alle Lagerbestände vor dem Import auf 0 setzen' richtig. Ansonsten werden Artikel mit NULL-Bestand nicht importiert.

- **Fehlerhafte Angebote auf eBay/Amazon abgleichen** `Deprecated`<br>
    Nach dem Import wird überprüft, ob der aktuelle Bestand im Datenpool kleiner als der Bestand auf dem Marktplatz ist. Sollte das der Fall sein, werden betreffende Angeboteauf dem Marktplatz angepasst. Es wird dabei immer der Bestand aus dem Datenpool übertragen.
	> Wenn Sie mit einer begrenzten Einstellmenge arbeiten, sollten Sie diese Funktion nicht benutzen.

- **Vorlage Spaltenzuordnung**<br>
    Wählen Sie eine bereits gespeicherte Importvorlage 'Bestand' aus. Aus einer Importvorlage wird im Cronjob nur die Spaltenzuordnung übernommen. Alle Import-Optionen müssen im Cronjob neu definiert werden!
    Der Import von Produktdaten und von Bestandsdaten sollte bereits ein Mal händisch durchgeführt worden sein (unter Datenpool ->Datenimport). Nur so lässt sich hier eine Importvorlage zuweisen. Passt die gewählte Vorlage nicht zum oben angegebenen Datei-Typ, dann stimmt die Spaltenzuordnung nicht und Ihre eingestellten Cronjobs brechen ab bzw. beginnen erst gar nicht.

### Preis

- **Wenn UPDATE: Fehlende Spalten ignorieren!**<br>
    Zutreffend für UPDATES: Wenn Sie nur bestimmte Spalteninhalte Ihrer Datei übernehmen möchten, muss diese Option aktiviert sein (ja). Es werden dann ausschließlich die Daten der ausgewählten Spalten importiert, die in der Importvorlage gespeichert sind. Alle anderen Spalteninhalte werden ignoriert (Standardeinstellung).
    Falls Sie diese Einstellung deaktivieren (nein), werden alle Spalteninhalte Ihrer Produktepreise gelöscht, die nicht in der Importvorlage hinterlegt sind.

- **Währungsumrechnung**<br>
    Umrechnung der Preise aus der Datei in EUR. Sie müssen dazu die Ausgangswährung auswählen.

- **Vorlage Spaltenzuordnung**<br>
    Wählen Sie eine bereits gespeicherte Importvorlage 'Bestand' aus. Aus einer Importvorlage wird im Cronjob nur die Spaltenzuordnung übernommen. Alle Import-Optionen müssen im Cronjob neu definiert werden!
    Der Import von Produktdaten und von Bestandsdaten sollte bereits ein Mal händisch durchgeführt worden sein (unter Datenpool ->Datenimport). Nur so lässt sich hier eine Importvorlage zuweisen. Passt die gewählte Vorlage nicht zum oben angegebenen Datei-Typ, dann stimmt die Spaltenzuordnung nicht und Ihre eingestellten Cronjobs brechen ab bzw. beginnen erst gar nicht.


***
# Besonderheiten Import

### Parentartikel

Um einen Artikel als Parentartikel zu deklarieren, schreiben Sie in das Feld 'Parent-ID' bei 'erweiterte Optionen' den Wert `isParent`.
