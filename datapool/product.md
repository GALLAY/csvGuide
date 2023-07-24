# Allgemeines

Der Bereich Produkte zeigt eine Liste mit allen im Datenpool gespeicherten Produkten/Parents der aktiven Datenquelle.
Vorhandene Produktdaten im Datenpool sind Voraussetzung um eine CSV- oder API-Schnittstelle nutzen zu können.

Wurden bereits Datensätze importiert bzw. angelegt, sehen Sie hier eine Auflistung Ihrer Produkte. Verschiedene Sortierungen können Sie über die kleine Schaltfläche mit den beiden Pfeilen (aufsteigend/absteigend) rechts neben der Suche vornehmen.

> Die Zuordnung der Produkte zu internen Kategorien ist eine wichtige Voraussetzung für den Export Ihrer Daten inkl. Shopkategorien im Bereich Export.

***
# Produkte

- **Alle Produkte**<br>Es werden Ihnen alle Produkte dieser Datenquelle angezeigt.

- **Produkte mit Bestand**<br>Nur Produkte mit einem Bestand werden angezeigt.

- **Produkte ohne Bestand**<br>Produkte, welche keinen Bestand haben, werden angezeigt.

- **nicht verfügbar**<br>Hier erhalten Sie eine Übersicht der Produkte, welche beim letzten Produktupdate nicht enthalten waren. Somit lassen sich ältere oder ausgelaufene Produkte schneller aussortieren.
> Beispiel: Ihr Großhändler liefert in seinen CSV-Dateien immer nur Daten von Artikeln die er auf Lager hat. Artikel ohne Bestand oder Artikel, die beim Großhändler ausgelaufen sind, stehen nicht in der Datei. Damit sammeln sich mit der Zeit Artikelnummern im System, die schön länger nicht mehr geändert wurden und bei denen gleichzeitig auch keine Bestandsaktualisierung mehr erfolgte (trotz regelmäßigem Import). Über diesen Reiter können solche Produkte schneller gefunden und bei Bedarf aus dem System entfernt werden.

***
# Parents

Hier finden Sie eine Übersicht der vorhanden Hauptartikel einer Variation.

> Varianten können z.B. Halsketten in verschiedenen Längen sein: 1010-42, 1010-45, 1010-50 (cm) oder T-Shirts in unterschiedlichen Farben: 1020-rot, 1020-blau und 1020-grün.
> Es gibt mehrere Möglichkeiten, Variantenartikel im System abzubilden. Welche Art Sie bevorzugen, hängt von der Struktur Ihrer Datensätze, von Ihrer Vorgehensweise oder auch von der Plattform ab,
> auf der Ihre Daten übernommen werden sollen.

### Unterscheidung des Parenttypen

#### Parents

Parents lassen sich als eigenständige Datensätze im Datenpool speichern: `Neuen Parent anlegen`. Solchen Parents können beliebige Produkte als Variantenartikel zugeordnet werden.
Einmal angelegte Parents können Sie jederzeit wieder löschen. Es werden dann übrigens keine Produkte, sondern nur die die Parent-Datensätze gelöscht.

![Übersicht Parents](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-uebersicht.png ':zoom :size=30%')

> **Beispiel 1** - Ein Parent als eigenständiger Datensatz<br><br>
> **Parent**: P12345<br>
> **Variantenartikel**: 12345-weiss, 12345-rot, 12345-schwarz, 12345-blau<br>
> Im Datenpool sind 4 Variantenartikel gespeichert. In jedem der 4 Varianten ist eine Gruppen-ID hinterlegt - die Nummer 'P12345'. Ein Parent als separater Datensatz existiert nicht.

> **Beispiel 2** - Importfile mit Gruppen-IDs<br><br>
> Parents können auch automatisch über die Importfunktion im Datenpool angelegt werden. Dazu müssen im Importfile Parents vorhanden sein. Die Beschreibung von Parents sollte sich wenn möglich von den einzelnen Varianten unterscheiden. <br>
> ![Auswahl Parent(s)](https://wiki.csv4you.com/images/thumb/Parents.png/400px-Parents.png ':zoom :size=30%')

> Nutzen Sie bitte immer die Importfunktion, wenn Sie eine größere Anzahl von Variantenartikeln anlegen möchten.

#### Gruppen-IDs

Gruppen-IDs sind die am häufigsten verwendete Form der Abbildung von Variantenartikeln. Gruppen-IDs werden dabei nicht als eigenständige Datensätze gespeichert, sondern es wird nur eine Gruppen-ID in den Varianten hinterlegt.

![Übersicht Gruppen-ID´s](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-gruppenids-uebersicht.png ':zoom :size=30%')

Optional lassen sich Gruppen-IDs auch in Parents umwandeln. Benutzen Sie dazu die Gruppenfunktion `Parent(s) JETZT anlegen`.

![Auswahl Gruppen-ID](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-gruppenids-auswahl.png ':zoom :size=30%')
![Gruppenfunktion 'Parent(s) JETZT anlegen'](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-gruppenids-auswahl-gruppenfunktion.png ':zoom :size=30%')

> **Beispiel 1** - Gruppen-IDs<br><br>
> **Parent**: P12345<br>
> **Variantenartikel**: 12345-weiss, 12345-rot, 12345-schwarz, 12345-blau<br>
> Es gibt einen Parent und 4 zugeordnete Varianten. Somit sind 5 Datensätze gespeichert.<br>In den 4 Varianten steht im Feld `Parent-ID` der Wert 'P12345'.

> **Beispiel 2** - Importfile mit Parents<br><br>
> Parents können auch automatisch über die Importfunktion im Datenpool angelegt werden. Dazu müssen im Importfile Parents vorhanden sein. Die Beschreibung von Parents sollte sich wenn möglich von den einzelnen Varianten unterscheiden. <br>
> ![Auswahl Parent(s)](https://wiki.csv4you.com/images/thumb/Group-IDs.png/400px-Group-IDs.png ':zoom :size=30%')

> Nutzen Sie bitte immer die Importfunktion, wenn Sie eine größere Anzahl von Variantenartikeln anlegen möchten.


### Unterscheidungsmerkmal dem Parent zuweisen

Um ein Produkt als Variante darzustellen, muss dem Parent noch das Unterscheidungsmerkmal(Größe,Farbe etc.) zugewiesen werden. Dies können Sie direkt beim Parent oder über die Gruppenfunktion erledigen.

![Auswahl Parent(s)](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-auswahl.png ':zoom :size=30%')
![Gruppenfunktion Auswahl Variantenwert](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-gruppenfunktion.png ':zoom :size=30%')

Sie können diese Einstellungen für die benötigten Eigenschaften auch per Import vornehmen. Benutzen Sie dafür folgenden Werte (muss in die Spalte der gewünschten Eigenschaft des Parents):

- 1 = Als Variantenwert 1 benutzen
- 2 = Als Variantenwert 2 benutzen
- 3 = Als Variantenwert 3 benutzen
- 4 = Als Variantenwert 4 benutzen
- 5 = Als Variantenwert 5 benutzen
- 99 = Als Variantenwert benutzen

> **Beispiel:** Wenn Farbe als Variantenwert 1 genutzt werden soll, muss eine 1 in die Spalte geschrieben werden.

Aktuell muss das für alle Parents durchgeführt werden. Sollten sich in der Importdatei Artikelnummern ändern oder neu hinzugefügt werden, müssen Sie auch die jeweiligen Parents (falls notwendig) neu anpassen.

***
# Suche

Geben Sie einen Suchbegriff ein oder nutzen Sie die Suche wie folgt:

- **OR**<br>gibt Artikel zurück, wo mindestens eines der Suchwörter gefunden wird, getrennt durch Leerzeichen. Beispiel: 'OR rot blau'
- **AND**<br>gibt Artikel zurück, in denen alle Suchwörter gefunden werden, getrennt durch Leerzeichen. Beispiel: 'AND rot blau'


***
# Filter

Zusätzlich gibt es die Möglichkeit zur Auswahl spezieller Suchfilter. So können innerhalb der verschiedenen Bereiche gezielt Suchkriterien für das Finden von bestimmten Datensätzen ausgewählt werden.
Klicken Sie dazu einfach auf die Schaltfläche `Filter`.

***
# Gruppenfunktion

Die Schaltfläche `Gruppenfunktion` dient zum gebündelten Bearbeiten von mehreren Produkten. Markieren Sie zunächst die gewünschten Datensätze die Sie bearbeiten oder löschen möchten und klicken Sie dann auf die Schaltfläche `Gruppenfunktion`.
Wählen Sie danach eine Funktion, die auf die markierten Datensätze angewendet werden soll und bestätigen Sie die Aktion durch `Ausführen`.
