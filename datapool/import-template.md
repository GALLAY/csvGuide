# Importvorlagen

> Die Bearbeitung in dieser Ansicht erfordert Kenntnisse im Umgang mit CSV4YOU. Wir empfehlen daher immer das Bearbeiten direkt beim Import durchzuführen. Die Spaltennamen stehen in Rohform in der Importvorlage.

Importvorlagen speichern alle individuellen Einstellungen inklusive Feldzuweisungen eines Datenimports.
Neue Importvorlagen können manuell oder über den Datenimport durch Vergabe eines Vorlagennamens angelegt werden.
Während eines Datenimports geänderte Feldzuordnungen werden automatisch in die verwendete Importvorlage übernommen.

> Machen Sie regelmäßig eine Datensicherung Ihrer Importvorlagen der aktiven Datenquelle. Sicherungsdateien werden bei uns im System gespeichert.
> Sie können diese zur Sicherheit auch downloaden und auf Ihrem Rechner speichern.

***
# Übersicht Importvorlagen

![Übersicht vorhandener Vorlagen](https://data.csv4you.com/media/image/guide/datenpool/importvorlagen/datenpool-importvorlagen-uebersicht.png ':zoom :size=30%')

> Um nicht die Übersicht über Ihre Importvorlagen zu verlieren, geben Sie bitte jeder Vorlage einen aussagekräftigen Namen, z.B. 'Bestand_ImportSchuhe' oder 'Produkte_ImportSchmuck' und löschen Sie ggf. nicht mehr benötigte Vorlagen.

***
# Aufbau

### Eigenschaften

![Eintrag bearbeiten - Eigenschaften](https://data.csv4you.com/media/image/guide/datenpool/importvorlagen/datenpool-importvorlagen-bearbeiten-eigenschaften.png ':zoom :size=30%')

- **Name der Vorlage**<br>
	Geben Sie Ihrer Importvorlage einen Namen (frei wählbar).
- **Trennzeichen Datenfeld**<br>
	Spaltentrenner festlegen
- **Texterkennungszeichen**<br>
	Texterkennungszeichen eingeben (falls verwendet)
- **Spaltennamen stehen in Zeile**<br>
	Hier die Zeile angeben, in der die Spaltennamen stehen (nicht immer ist es die 1. Zeile)

#### optionale Angaben bei XML-Daten
- **XML-Element der Produktdaten**<br>
	XML-Element, das die Produktdaten enthält
- **Varianten**<br>
	Gibt es zusätzlich Variantenartikel, ordnen Sie bitte das entsprechende XML-Feld zu.


### Spaltenzuordnung

![Eintrag bearbeiten - Spaltenzuordnung](https://data.csv4you.com/media/image/guide/datenpool/importvorlagen/datenpool-importvorlagen-bearbeiten-spaltenzuordnung.png ':zoom :size=30%')

Hier sehen Sie die Spaltenzuordnungen Ihrer Importvorlage. Die Anzahl der verfügbaren Spalten hängt davon ab, für welchen Dateityp die Importvorlage eingerichtet wurde: Kategorie, Produkt oder Bestand.

#### Erläuterung der Spalten

- **Spaltenname in Datenbank**<br>
	Hier werden die verfügbaren Felder in der Datenbank aufgelistet (Spaltennamen).
- **Spaltenname in Importdatei**<br>
	Den Spaltennamen Ihrer Datei können Sie anpassen (falls notwendig), wenn sich z.B. Spaltenbezeichner Ihrer Importdatei ändern. Ihr Spaltenname muss natürlich mit dem Namen in Ihrer Datei übereinstimmen. Die Inhalte der jeweiligen Spalten Ihrer Importdatei werden dann später beim Import oder Konvertieren automatisch den Spaltennamen der Schnittstelle (links) zugeordnet. Spaltennamen sollten grundsätzlich keine Leerzeichen, Sonderzeichen oder Umlaute verwenden!
- **erweiterte Optionen**<br>
	Sollen alle Datensätze bestimmter Spalten einen festen Wert bekommen (z.B. Zustand = 'NEU' oder Menge = '1'), so tragen Sie diesen Wert bitte ein (NEU oder 1). Die Zuordnung Spaltenname in Importdatei in solchen Fällen bitte leer lassen.

#### Erweiterte Feldfunktionen

Es stehen verschiedene Möglichkeiten zur individuellen Formatierung, Berechnung und Filterung von Spalteninhalten für den Import und Export von Daten zur Verfügung. Schauen Sie dazu bitte auf unsere Hilfeseite Erweiterte Feldfunktionen.


### Importoptionen

![Eintrag bearbeiten - Importoptionen](https://data.csv4you.com/media/image/guide/datenpool/importvorlagen/datenpool-importvorlagen-bearbeiten-importoptionen.png ':zoom :size=30%')

#### Dateityp Produkt

- **Fehlende Produkte im Datenpool anlegen**<br>
    Produkte aus der Importdatei, die noch nicht im Datenpool angelegt sind, werden als neue Produkte mit neuer ID im Datenpool hinzugefügt. Beachten Sie, dass damit unter Umständen auch fehlerhafte Importdaten als neue Produkte angelegt werden. Achten Sie daher immer darauf, dass Ihre Importdateien korrekt formatiert sind.

- **Datensätze auch ohne eigene ID**<br>
    Enthält Ihre Importdatei Datensätze ohne eigene ID, so markieren Sie bitte diese Option. Standardmäßig werden nur Datensätze mit eindeutiger ID importiert.

- **Formatierungen aus den Texten entfernen!**<br>
    Sämtliche Formatierungen wie z.B. HTML-Tags werden beim Import aus den Daten entfernt.

- **Wenn UPDATE: Fehlende Spalten ignorieren!**<br>
    Zutreffend für UPDATES: Wenn Sie nur bestimmte Spalteninhalte Ihrer Datei übernehmen möchten, muss diese Option aktiviert sein (ja). Es werden dann ausschließlich die Daten der ausgewählten Spalten importiert, die in der Importvorlage gespeichert sind. Alle anderen Spalteninhalte werden ignoriert (Standardeinstellung).
    Falls Sie diese Einstellung deaktivieren (nein), werden alle Spalteninhalte Ihrer Produkte gelöscht, die nicht in der Importvorlage hinterlegt sind.

    > Beispiel: Ihr Datenpool enthält 20 Spalten mit verschiedenen Werten, Sie möchten aber nur die Inhalte der Spalten TITEL und EAN aktualisieren, weil sich z.B. einige Produkttitel Ihres Angebots geändert haben und aktualisiert werden sollen. Die Einstellung muss dazu aktiviert sein (ja). EAN-Nummern sollten sich natürlich nicht geändert haben, damit eine korrekte Zuordnung der neuen Titel erfolgen kann.

- **Kategorien aus Importdatei übernehmen**<br>
    Enthält Ihre Importdatei Produktkategorien, so können Sie diese als interne Kategorien im Datenpool übernehmen. Bei erneuten Importen werden bereits vorhandene Daten aktualisiert.
	Neu hinzugekommene interne Kategorien werden neu angelegt. Erstellt werden die Kategorien aus den Werten der Spalten
	`externe Kategorie 1 (cat1)`, `externe Kategorie 2 (cat2)`, `externe Kategorie 3 (cat3)`, `externe Kategorie 4 (cat4)` und `externe Kategorie 5 (cat5)`

- **Sicherung der alten Daten vor dem Import erstellen**<br>
    Vor dem Import zur Sicherheit eine Datensicherung anlegen

#### Dateityp Bestand

- **Alle Lagerbestände vor dem Import auf 0 setzen**<br>
    Wenn markiert, werden alle Bestände im Datenpool vor dem Import gelöscht und zurück auf 0 gesetzt.