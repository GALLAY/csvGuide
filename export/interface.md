# Exportprofile

***
# Grundeinstellungen

![Grundeinstellungen des Exportprofiles](https://data.csv4you.com/media/image/guide/export/export-exportprofil-grundeinstellungen.png ':zoom :size=30%')

> Je nach Schnittstelle, können einige der nachfolgenden Felder ausgeblendet sein.

> Sollten Sie mit Preiskalkulationen und/oder Produkttemplates arbeiten, erfolgt die Zuweisung auf dieser Einstellungsseite.

- **Datei-Typ**<br>
    Wählen Sie aus, wie Sie Ihre Exportdateien downloaden möchten, z.B. als ZIP-Paket oder einzeln.
    Hinweis: Dieses Feld ist nur für solche Exportprofile sichtbar, die mehrere Dateien beim Download beinhalten.

- **Name**<br>
    frei wählbar, nur für die interne Anzeige

- **Dateiname**<br>
    Name der zu exportierenden Datei (bitte keine Sonderzeichen, Leerzeichen etc. verwenden)

- **kurze Beschreibung**<br>
    Kurze Beschreibung zu Ihrer Exportdatei (optional).

- **Datei splitten**<br>
    Hier können Sie die maximale Anzahl der Produkte (Datensätze) festlegen, die in einer Exportdatei enthalten sein sollen (optional). Angenommen Ihre Exportdatei aus csv4you.com enthält ca. 5000 Datensätze und ist etwa 10 MByte groß. Der Import in Ihr Shopsystem erlaubt jedoch nur 2 MByte pro Datei/Upload. Geben Sie z.B. eine 1000 ein, so erhalten Sie 5 Dateien mit jeweils 1000 Datensätzen und etwa 2 MByte Größe. Diese 5 Dateien lassen sich dann nacheinander in Ihr System importieren.

- **Datei per FTP übertragen**<br>
    Nur sichtbar bei hinterlegtem FTP-Zugang. Die erstellte Datei wird nach dem Erstellen auf Ihren FTP-Server kopiert.

- **Direkt-Link 'xXxXxX' ändern**<br>
    Haben Sie bereits eine Exportdatei gespeichert, so können Sie den Link zu Ihrer Datei jederzeit ändern, z.B. aus Sicherheitsgründen (optional). Den Link zu Ihrer Exportdatei finden Sie rechts.


### Allgemeines

- **Produkttexte verwenden aus**<br>
    Falls Produkttexte in verschiedenen Sprachen hinterlegt sind, können diese hier ausgewählt werden. Das Anlegen bzw. die Einrichtung der Felder für unterschiedliche Sprachinhalte erfolgt über Mein Konto ->Grundeinstellungen ->Datenquellen ->Aktionen ->Sprachbezeichner. Mindestens in einem Produkt muss Inhalt in der zusätzlichen Sprache hinterlegt sein. Nur dann ist hier eine Auswahl möglich.

- **Leere Produkttexte auffüllen?**<br>
    Für fehlende Einträge z.B. in Sprache 2 wird der Inhalt aus den Stammdaten verwendet.
    Hinweis: Beide Optionen sind nur verfügbar, wenn im Datenpool mindestens ein Produkttext in einer 2. Sprache existiert.

- **Einstellmenge**<br>
    Festlegen eines globalen Wertes für die Menge pro Artikel, die als verfügbare Anzahl (Bestand) eingestellt werden soll, z.B. bei eBay.
    Der Schalter Ja/Nein wird nur in der 2. Option angewendet.

    Werte > 0 überschreiben den Wert Bestand (quantity) im Export wie folgt:

    - Einstellmenge <= Bestand:<br>
		Es wird die Einstellmenge als Bestand übernommen.

    - Einstellmenge > Bestand:<br>
		Nein - Bestand wird auf 0 gesetzt.<br>
		Ja - Verfügbarer Bestand wird übernommen.<br>

    - Einstellmenge leer:<br>
		Der Bestand aus der Datenquelle wird übernommen.


- **Zusatz zur Art.-Nr.**<br>
    Zusatz zur Art.-Nummer, der vor der Artikelnummer angefügt wird (nicht bei allen Schnittstellen).

- **Formatierung**<br>
    Produktbezeichnung optional in Großbuchstaben

- **Zeichensatzkodierung**<br>
    Standard ist UTF-8.


### Preisgestaltung

- **Währung | In diese Währung umrechnen**<br>
    Bestimmen Sie hier die Währung und legen Sie danach fest, ob Ihre Preise aus dem Datenpool in die gewählte Währung umgerechnet werden sollen oder nicht. Beachten Sie bitte unbedingt, dass unsere interne Ausgangswährung für alle Preisberechnungen im Exportmodul immer der EURO ist! Hierzu einige Beispiele:

    - Beispiel 1:<br>
		Preise im Datenpool sind in EUR, alle Preise Ihrer Exportdatei sollen ebenfalls EUR erscheinen. Markieren Sie dafür EUR und nein.

    - Beispiel 2:<br>
		Preise im Datenpool sind in EUR, alle Preise Ihrer Exportdatei sollen in USD umgerechnet werden. Markieren Sie dafür USD und ja.

    - Beispiel 3:<br>
		Preise im Datenpool sind in USD, alle Preise Ihrer Exportdatei sollen ebenfalls in USD erscheinen. Markieren Sie dafür USD und nein.

    - Beispiel 4:<br>
		Preise im Datenpool sind in USD, alle Preise Ihrer Exportdatei sollen in GBP umgerechnet werden. Dafür müssen Ihre Preise beim Import in den Datenpool zuerst von USD in EUR konvertiert werden. Wie das funktioniert ist unter Besonderheiten Import - Währungsumrechnungen beschrieben.

- **Preis anpassen**<br>
    Angaben im Preisfeld werden automatisch angepasst.
    Preise werden beim Export standardmäßig mit Komma ausgegeben, außer in solchen Schnittstellen, die den Punkt als Dezimaltrennzeichen benötigen. Falls notwendig, können Sie mit Hilfe der replace-Funktion das Komma durch einen Punkt ersetzen (siehe dazu Erweiterte Feldfunktionen).

- **Preisauswahl (optional)**<br>
    Standardmäßig wird immer der Wert aus dem Preisfeld 'Preis' ausgewertet. Sollten Sie mit einem anderen Preisfeld arbeiten, dann wählen Sie dieses hier aus.

- **Preiskalkulation (optional)**<br>
    Wählen Sie hier eine Preiskalkulation für das Exportprofil aus oder legen Sie eine neue Preiskalkulation an.


### Produkttemplate für Datensätze

- **Template**<br>
    Wählen Sie ein Template für die Produktbeschreibung aus. Produkttemplates müssen unter `Export->Produkttemplates` angelegt und eingerichtet sein.
	Ist kein Template bestimmt, wird beim Erstellen Ihrer Exportdatei der Wert aus Beschreibung übernommen, der in Ihren einzelnen Datensätzen/Produkten hinterlegt ist (`Datenpool->Produkte`).


> Mit Hilfe eines Templates lassen sich die einzelnen Beschreibungstexte z.B. um zusätzliche Bilder, allgemeine Texte oder Hinweise erweitern.
Diese müssen dann nur ein Mal im Template zusammen mit dem Platzhalter für die Produktbeschreibung gespeichert werden..


### Download Responsedatei

In API-Schnittstellen (z.B. für eBay und Amazon) gelangen Sie über die Schaltfläche `Download Responsedatei` auf eine neue Seite. Loaden Sie sich dort die gewünschte Antwortdatei herunter.
Responsedateien enthalten Rückmeldungen darüber, ob eine Übertragung erfolgreich oder fehlerhaft lief. Schauen Sie bei Problemen immer zuerst in diese Dateien.

Das Erstellen der gewünschten Responsedatei kann je nach Schnittstelle bzw. Marktplatz eine gewisse Zeit dauern. Wann Ihnen eine Responsedatei nach dem Anfordern zur Verfügung steht, hängt z.B. bei eBay von unterschiedlichen Faktoren ab, auf die unser System keinen Einfluss hat.


### Letzter Statusbericht

Bei einigen API-Schnittstellen befindet sich hingegen der Button `Letzter Statusbericht`. Mit Klick auf diesen, wird Ihnen direkt einen Datei zum Download angeboten.
Diese enthält Rückmeldungen darüber, ob eine Übertragung erfolgreich oder fehlerhaft lief.

> Schauen Sie bei Problemen immer zuerst in diese Datei.


***
# Kategorieauswahl

![Produkte aus welcher Kategorie](https://data.csv4you.com/media/image/guide/export/export-exportprofil-kategorieauswahl.png ':zoom :size=30%')

### Kategoriezuordnung

> Eine Kategoriezuordnung ist nur wählbar, wenn im Menü `Export->Kategoriezuordnung` eine Kategoriezuordnung angelegt ist.

Eine Kategoriezuordung sollte immer dann ausgewählt werden, wenn die Kategorien Ihres Shops z.B. über IDs angesprochen werden.

Ist im Exportprofil keine Kategoriezuordnung ausgewählt, übernimmt die Schnittstelle automatisch die internen Kategorien
aus der Datenquelle inklusive der darin enthaltenen Produkte. Sind im Datenpool keine internen Kategorien angelegt,
enthalten alle Produkte Ihrer Schnittstelle keine Kategorien.

### Produkte aus nachfolgenden Kategorien

Wollen Sie nur Produkte bestimmter Kategorien exportieren, wählen Sie die benötigten Kategorien hier aus. Haben Sie keine Auswahl gesetzt,
werden alle Produkte exportiert, je nach Filtereinstellungen.


***
# Filter

![Filtereinstellungen](https://data.csv4you.com/media/image/guide/export/export-exportprofil-bilder.png ':zoom :size=30%')

Sie können unterschiedliche Filter nutzen, um Ihre Auswahl einzugrenzen.

- **Filter - Preis**<br>
	Optionale Vorgaben für das Filtern von Artikeln mit bestimmten Preisen. Als Dezimaltrenner bitte den Punkt verwenden.
	Es werden immer die Preise aus dem Datenpool zum Auswerten genommen, bevor eine eventuell hinterlegte Preiskalkulation greift.

- **Filter - Bestand**<br>
	Optionale Vorgaben für das Filtern von Artikeln mit bestimmten Beständen.

	*Beispiel für Artikel mit einem Bestand von 6:*<br>
	Sie setzen die Auswahl bei 'größer als' auf 5 und 'kleiner als' auf 7. Damit werden nur Artikel mit einem Bestand von 6 exportiert.

	> Sollten Sie den 'Filter - Nullbestand' aktiviert haben, werden auch die restlichen Produkte exportiert, welche auf alle Filtereinstellungen passen würden, aber mit einem Bestand von NULL.

- **Filter - Nullbestand**<br>
	Die Voreinstellung ist ja. Es werden alle Produkte aus der aktiven Datenquelle in der Schnittstelle übernommen (auch die ohne Bestand).
	Falls Sie nur Artikel mit Bestand (also Bestand > 0) in Ihre Exportdatei aufnehmen möchten, dann setzen Sie den Wert auf nein und speichern die Änderung.

	> Dieser Filter sollte bei einem Bestandsupdate immer ausgewählt sein, da sonst Produkte mit einem Bestand von Null nicht im Shopsystem oder Marktplatz geändert werden.

- **Filter - SQL Abfrage**<br>
	Dieser Filter ist für individuelle Filterangaben geeignet. Wählen Sie eine beliebige Spalte aus der Produkttabelle und tragen dazu einen Wert ein, nach dem gesucht werden soll.

- **Filter - Sonstige**<br>

	- Produkte mit Update<br />Wählen Sie hier die maximale Anzahl 'Tage', innerhalb derer Produkte durch den Import aktualisiert wurden. Der Export beinhaltet dann nur jene Produkte, auf die dieser Filter zutrifft.

- **Filter - Einzelne Datensätze (Komma getrennt)**<br>
	Angaben in diesem Feld überschreiben alle anderen oben gesetzten Filter. Hier können Sie gezielt ganz bestimmte Artikel-Nummern bzw. Produkt-IDs angeben. Nur diese Datensätze werden dann übernommen.
	Die Eingabe muss als fortlaufende Liste mit Komma getrennt erfolgen.

	*Beispiel:*<br>52358,69875,5984-49,a6hz6f,e4888

- **Filter - Ausgeschlossene Datensätze (Komma getrennt)**<br>
	Angaben in diesem Feld überschreiben alle anderen oben gesetzten Filter. Über diesen Filter lassen sich bestimmte Artikel-Nummern bzw. Produkt-IDs vom Export ausschließen.

- **Filter - Neuzugänge**<br>
	Es werden nur die letzten neu importierten Datensätze im Datenpool in die Schnittstelle übernommen.

	*Beispiel:*<br />Sie haben vor einer Woche 1000 Datensätze in Ihren Datenpool importiert und heute 1200. Ihre Exportdatei, enthält dann 200 Produkte, wenn der Filter Nur neue Datensätze auf 'ja' gesetzt ist.


***
# Bilder (optional)

![Bildauswahl(optional)](https://data.csv4you.com/media/image/guide/export/export-exportprofil-bilder.png ':zoom :size=30%')

Hier können Sie festlegen, welche Bilder aus dem Datenpool in welcher Reihenfolge in Ihr Exportprofil übernommen werden.

> Keine Auswahl übernimmt die Bilder in der Reihenfolge, wie Sie im Datenpool hinterlegt sind. Die Anzahl der Bilder ist dabei von der jeweiligen Schnittstelle abhängig.


***
# Varianten (optional)

![Einstellungen für Varianten(optional)](https://data.csv4you.com/media/image/guide/export/export-exportprofil-varianten.png ':zoom :size=30%')

Wenn Sie die Option Export mit Parents aktivieren, erfolgt der Export im Normalfall mit Parents und Varianten. Sie müssen diese Einstellung dann auch für Bestands-Exportprofile benutzen.

> Die Seite Varianten ist nur in bestimmten Schnittstellen, welche Variationen unterstützen, vorhanden.

> Hat ein Parent nur eine Variante, dann wird dieser als Einzelartikel behandelt.


***
# Cronjob

![Cronjob einrichten](https://data.csv4you.com/media/image/guide/export/export-exportprofil-cronjob.png ':zoom :size=30%')

Mit Hilfe von Cronjobs lassen sich zu festgelegten Zeiten immer wiederkehrende Aufgaben z.B. in den Bereichen Import, Export und Artikellisting vollständig automatisieren.
Die Anzahl der Cronjobs, die täglich ausgeführt werden kann, richtet sich nach Ihrem gewählten Tarifpaket.
Markieren Sie daher bitte nur die maximal mögliche Anzahl an Cronjobs Ihres Tarifs, die nachfolgend angezeigt wird. Markierte Zeiten, die darüber hinaus gehen, ignoriert das System.

| Tarif | Anzahl Cronjobs * |
| --- | --- |
| Free | 3 |
| Starter | 6 |
| Business | 12 |
| Premium | 24 |

*Die Angaben gelten separat für jedes Exportprofil.

> Cronjobs werden automatisch deaktiviert, falls Sie länger als 3 Monate nicht in Ihrem Account eingeloggt waren.

> Cronjobs werden per Zufallsreihenfolge gestartet. Das kann den Zeitpunkt der erfolgreichen Erstellung verzögern.
> Wenn der Cronjob noch läuft, aber der Nächste bereits gestartet werden soll, dann wird dieser nicht ausgeführt.


***
# Sonstiges

![Sonstige Einstellungen](https://data.csv4you.com/media/image/guide/export/export-exportprofil-sonstiges.png ':zoom :size=30%')

Hier finden Sie schnittstellenspezifische Einstellungen bzw. Feldinhalte für den Export Ihrer Daten. Dieser Bereich kann je nach Schnittstelle sehr speziell und umfangreich sein.
Stellen Sie eventuell auftretende Fragen bitte über unser Forum oder den Ticketservice.

> Diese Unterseite ist nur in bestimmten Exportprofilen verfügbar.


***
# Eigene Spaltenzuordnung

![Eigene Spaltenzuordnung](https://data.csv4you.com/media/image/guide/export/export-exportprofil-eigene-spaltenzuordnung.png ':zoom :size=30%')

Hier lassen sich einzelne Spalteninhalte durch eigene, individuelle Werte ersetzen. Ihre Änderungen überschreiben die im Exportprofil standardmäßig hinterlegten Inhalte.
Um bestimmte Inhalte aus dem Datenpool zuzuweisen (Spaltenwerte), klicken Sie mit der Maus in das betreffende Eingabefeld.
Danach wählen Sie im oberen Bereich den Platzhalter aus und stellen die gewünschten Optionen bzw. Eigenschaften ein. Vergessen Sie nicht, alle Änderungen zu speichern.

> Die Seite eigene Spaltenzuordnung ist nicht in allen Exportprofilen sichtbar.
