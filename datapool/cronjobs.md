# Cronjobs für den Import

> Cronjobs werden automatisch deaktiviert, falls Sie länger als 3 Monate nicht in Ihrem Account eingeloggt waren.

Cronjobs bieten Ihnen die Möglichkeit, unterschiedliche Datenfeeds täglich zu bestimmten Zeiten automatisch in Ihren Datenpool einlesen zu lassen (z.B. aufgrund von Bestandsänderungen).
Folgende Datentypen können aktuell per Cronjob importiert werden: Produkte, Bestand und Preise.

> Für das korrekte Anlegen eines Import-Cronjobs ist die Einrichtung einer entsprechenden Importvorlage zwingende Voraussetzung.


***
# Allgemeine Einstellungen

- **Name des Cronjobs**<br>
    eine beliebige Bezeichnung für diesen Cronjob

- **Datei-Typ**<br>
    Typ der Importvorlage: Produkt, Bestand oder Preis

- **URL/FTP Importdatei**<br>
    URL - für vollständigen Weblink zu Ihrer Importdatei - oder
    FTP - dann den Pfad zur Importdatei auf dem FTP-Server angeben (siehe Mein Konto ->Grundeinstellungen ->FTP-Daten), z.B. /ordner1/ordner2/produkte.csv
    Bei mehreren Dateien muss jede Pfadangabe in einer separaten Zeile stehen und alle Dateien müssen das gleiche Format aufweisen!

- **Trennzeichen Datenfeld**<br>
    Geben Sie den Daten- bzw. Spaltentrenner an, der in Ihrer Importdatei verwendet wird.

- **Texterkennungszeichen**<br>
    das in Ihrer Importdatei verwendet wird

- **Spaltennamen stehen in Zeile**<br>
    Angabe, in welcher Zeile die Spaltenbezeichner notiert sind (meistens ist das die 1. Zeile)

#### optionale Angaben bei XML-Daten
- **XML-Element der Produktdaten**<br>
	XML-Element, das die Produktdaten enthält

- **Varianten**<br>
	Gibt es zusätzlich Variantenartikel, ordnen Sie bitte das entsprechende XML-Feld zu.

> Falls eine per Cronjob importierte Datei leer oder nicht vorhanden ist, informiert Sie unser System per E-Mail darüber. Bitte korrigieren Sie in diesem Fall Ihre Einstellungen oder löschen Sie den betreffenden Import-Cronjob.

***
# Individuelle Einstellungen

> Je nach Typ des Cronjobs sind entweder Einstellungen für den Typ Produkt, Bestand oder Preis zu treffen.


## Produkt

![Übersicht vorhandener Cronjobs für Produktimporte](https://data.csv4you.com/media/image/guide/datenpool/cronjob/datenpool-cronjob-import-produkte-uebersicht.png ':zoom :size=30%')
![Vorhandenen Produkt-Cronjob bearbeiten (Importvariante:Anbieterdaten)](https://data.csv4you.com/media/image/guide/datenpool/cronjob/datenpool-cronjob-import-produkte-bearbeiten.png ':zoom :size=30%')

- **Fehlende Produkte im Datenpool anlegen**<br>
    Produkte aus der Importdatei, die noch nicht im Datenpool angelegt sind, werden als neue Produkte mit neuer ID im Datenpool hinzugefügt. Beachten Sie, dass damit unter Umständen auch fehlerhafte Importdaten als neue Produkte angelegt werden. Achten Sie daher immer darauf, dass Ihre Importdateien korrekt formatiert sind.

- **Formatierungen aus den Texten entfernen!**<br>
    Sämtlicher HTML-Code wird aus den importierten Daten entfernt.

- **Wenn UPDATE: Fehlende Spalten ignorieren!**<br>
    Zutreffend für UPDATES: Wenn Sie nur bestimmte Spalteninhalte Ihrer Datei übernehmen möchten, muss diese Option aktiviert sein (ja). Es werden dann ausschließlich die Daten der ausgewählten Spalten importiert, die in der Importvorlage gespeichert sind. Alle anderen Spalteninhalte werden ignoriert (Standardeinstellung).
    Falls Sie diese Einstellung deaktivieren (nein), werden alle Spalteninhalte Ihrer Produkte gelöscht, die nicht in der Importvorlage hinterlegt sind.
	>  Beispiel: Ihr Datenpool enthält 20 Spalten mit verschiedenen Werten, Sie möchten aber nur die Inhalte der Spalten TITEL und EAN aktualisieren, weil sich z.B. einige Produkttitel Ihres Angebots geändert haben und aktualisiert werden sollen. Die Einstellung muss dazu aktiviert sein (ja). EAN-Nummern sollten sich natürlich nicht geändert haben, damit eine korrekte Zuordnung der neuen Titel erfolgen kann.

- **Kategorien aus Importdatei übernehmen**<br>
    Enthält Ihre Importdatei Produktkategorien, so können Sie diese als interne Kategorien im Datenpool übernehmen. Bei erneuten Importen werden bereits vorhandene Daten aktualisiert. Neu hinzugekommene interne Kategorien werden neu angelegt.

- **Vorlage Spaltenzuordnung**<br>
    Wählen Sie eine bereits gespeicherte Importvorlage 'Produkt' aus. Aus einer Importvorlage wird im Cronjob nur die Spaltenzuordnung übernommen. Alle Import-Optionen müssen im Cronjob neu definiert werden!
    Der Import von Produktdaten und von Bestandsdaten sollte bereits ein Mal händisch durchgeführt worden sein (unter Datenpool ->Datenimport). Nur so lässt sich hier eine Importvorlage zuweisen. Passt die gewählte Vorlage nicht zum oben angegebenen Datei-Typ, dann stimmt die Spaltenzuordnung nicht und Ihre eingestellten Cronjobs brechen ab bzw. beginnen erst gar nicht.
    > Das bedeutet: Für Importcronjobs Typ Produkt benötigen Sie eine Importvorlage vom Typ Produkt.


## Bestand

![Übersicht vorhandener Cronjobs für Bestandsimporte](https://data.csv4you.com/media/image/guide/datenpool/cronjob/datenpool-cronjob-import-bestand-uebersicht.png ':zoom :size=30%')
![Vorhandenen Cronjob bearbeiten (Importvariante:Anbieterdaten)](https://data.csv4you.com/media/image/guide/datenpool/cronjob/datenpool-cronjob-import-bestand-bearbeiten.png ':zoom :size=30%')

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
    > Das bedeutet: Für Importcronjobs Typ Bestand benötigen Sie eine Importvorlage vom Typ Bestand.


## Preis

- **Wenn UPDATE: Fehlende Spalten ignorieren!**<br>
    Zutreffend für UPDATES: Wenn Sie nur bestimmte Spalteninhalte Ihrer Datei übernehmen möchten, muss diese Option aktiviert sein (ja). Es werden dann ausschließlich die Daten der ausgewählten Spalten importiert, die in der Importvorlage gespeichert sind. Alle anderen Spalteninhalte werden ignoriert (Standardeinstellung).
    Falls Sie diese Einstellung deaktivieren (nein), werden alle Spalteninhalte Ihrer Produktepreise gelöscht, die nicht in der Importvorlage hinterlegt sind.

- **Währungsumrechnung**<br>
    Umrechnung der Preise aus der Datei in EUR. Sie müssen dazu die Ausgangswährung auswählen.

- **Vorlage Spaltenzuordnung**<br>
    Wählen Sie eine bereits gespeicherte Importvorlage 'Bestand' aus. Aus einer Importvorlage wird im Cronjob nur die Spaltenzuordnung übernommen. Alle Import-Optionen müssen im Cronjob neu definiert werden!
    Der Import von Produktdaten und von Bestandsdaten sollte bereits ein Mal händisch durchgeführt worden sein (unter Datenpool ->Datenimport). Nur so lässt sich hier eine Importvorlage zuweisen. Passt die gewählte Vorlage nicht zum oben angegebenen Datei-Typ, dann stimmt die Spaltenzuordnung nicht und Ihre eingestellten Cronjobs brechen ab bzw. beginnen erst gar nicht.
    > Das bedeutet: Für Importcronjobs Typ Bestand benötigen Sie eine Importvorlage vom Typ Preis.

***
# Zeiteinstellungen

Mit Hilfe von Cronjobs lassen sich zu festgelegten Zeiten immer wiederkehrende Aufgaben z.B. in den Bereichen Import, Export und Artikellisting vollständig automatisieren. Die Anzahl der Cronjobs, die täglich ausgeführt werden kann, richtet sich nach Ihrem gewählten Tarifpaket. Markieren Sie daher bitte nur die maximal mögliche Anzahl an Cronjobs Ihres Tarifs, die nachfolgend angezeigt wird. Markierte Zeiten, die darüber hinaus gehen, ignoriert das System.

> Beachten Sie auch, dass sämtliche Cronjobs auf dem System in eine Warteschlange gestellt und chronologisch abgearbeitet werden.
Hinweise zum Status eines laufenden Crons finden Sie im jeweiligen Bereich.
Die Anzahl der ausgeführten Cronjobs wird täglich um 0 Uhr MEZ/CET zurückgesetzt.

- **Uhrzeit**<br>
	Markieren Sie die jeweiligen Zeiten, zu denen Ihre Datei eingelesen werden soll.
    Führen Sie die Bestandscronjobs nicht zu den selben Zeiten wie Produktcronjobs aus (oder umgekehrt). So vermeiden Sie Überschneidungen bzw. fehlerhafte Aktualisierungen.

- **Tage**<br>
    Die Wochentage für Ihren Cronjob (mehrere Uhrzeiten bzw. Wochentage markieren/löschen mit Strg + linke Maustaste)
    Damit Ihre Zeiteinstellungen gespeichert werden, muss unbedingt eine Importvorlage ausgewählt sein!
	> Keine Auswahl = Jeder Tag

***
# Tarifpaket / max. Cronjobs je Bereich

| Tarif | Anzahl Cronjobs * |
| --- | --- |
| Free | 3 |
| Starter | 6 |
| Business | 12 |
| Premium | 24 |

> Die Angaben gelten separat für jeden Import sowie für jedes Exportprofil.

*Davon ausgenommen sind vollständige Produktimporte. Hier sind maximal 4 Cronjobs am Tag möglich.
