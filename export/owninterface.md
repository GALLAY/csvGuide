# Individuelle Schnittstellen

Im Bereich Individuelle Schnittstellen können Sie freie, individuelle CSV- oder XML-Formate definieren.
Sie sehen dazu ein Auswahlmenü zum Anlegen bzw. zur Auswahl einer bereits von Ihnen vorbereiteten Schnittstelle.
Die Anzahl individueller Schnittstellen ist nicht begrenzt.

> Beispiel: Sie besitzen ein eigenes Shopsystem und möchten viele Produkte eines Ihrer Lieferanten auf einfache Art und Weise in Ihr System importieren.
Eine solche Schnittstelle lässt sich individuell einrichten und jederzeit umkonfigurieren.


***
# Übersicht vorhandener individueller Schnittstellen

![Übersicht vorhandener individueller Schnittstellen](https://data.csv4you.com/media/image/guide/export/export-indiv-schnittstellen-uebersicht.png ':zoom :size=30%')


***
# Eintrag bearbeiten

## Grundeinstellungen

![Neuanlage individueller Schnittstellen](https://data.csv4you.com/media/image/guide/export/export-indiv-schnittstellen-neuanlage.png ':zoom :size=30%')
![Grundeinstellungen bearbeiten individueller Schnittstellen](https://data.csv4you.com/media/image/guide/export/export-indiv-schnittstellen-bearbeiten-grundeinstellungen.png ':zoom :size=30%')

- **Name**<br>
    Geben Sie Ihrer individuellen Schnittstelle eine aussagekräftigen Bezeichnung (frei wählbar).

- **Datei-Typ**<br>
    Hier den passenden Dateityp auswählen

- **Trennzeichen Datenfeld**<br>
    z.B.: Semikolon (;) oder Komma (,)

- **Texterkennungszeichen**<br>
    z.B.: Anführungszeichen (") oder das einfache Hochkomma (')

- **Freifelder benutzen**<br>
    Legt fest, ob Sie die individuelle Schnittstelle zeilenweise oder einem Freifeld bearbeiten möchten.


## Bearbeiten ohne Freifelder

![Bearbeiten individueller Schnittstellen: Spalten anlegen](https://data.csv4you.com/media/image/guide/export/export-indiv-schnittstellen-bearbeiten-spalten-neu.png ':zoom :size=30%')
![Bearbeiten individueller Schnittstellen: Spalten bearbeiten](https://data.csv4you.com/media/image/guide/export/export-indiv-schnittstellen-bearbeiten-spaltenuebersicht.png ':zoom :size=30%')

Bearbeiten Sie die Spalten Ihrer eigenen Schnittstelle zeilenweise.


## Bearbeiten mit Freifelder

![Bearbeiten individueller Schnittstellen: Freifeld Kopfbereich](https://data.csv4you.com/media/image/guide/export/export-indiv-schnittstellen-bearbeiten-freifeld-kopfbereich.png ':zoom :size=30%')
![Bearbeiten individueller Schnittstellen mit Freifelder: Freifeld Inhaltsbereich](https://data.csv4you.com/media/image/guide/export/export-indiv-schnittstellen-bearbeiten-freifeld-inhaltsbereich.png ':zoom :size=30%')

Bearbeiten Sie die Spalten Ihrer eigenen Schnittstelle in einem Textfeld.


### Kopfbereich

Im Kopfbereich befindet sich normalerweise die Spaltendefinition Ihrer Schnittstelle, z.B. für eine einfache CSV-Datei. Bitte fügen Sie hinter jeden Spaltennamen den Platzhalter {#S#} ein (nicht beim letzten Wert!). Sollen Spalten leer bleiben, dann nur {#S#} als Platzhalter an dieser Stelle verwenden.

*Ein Beispiel für den Kopfbereich einer CSV-Schnittstelle:*
<code>
id{#S#}
title{#S#}
desc{#S#}
quantity{#S#}
gewicht{#S#}
size{#S#}
bild1{#S#}
bild2{#S#}
ean{#S#}
...{#S#}
...{#S#}
status
</code>

> Möchten Sie mehrere Kopfzeilen erstellen, fügen Sie am Ende jeder Kopfzeile, außer in der der letzten Zeile(!), ein {#BR#} ein .

*oder ein Beispiel für einen einfachen XML-Kopf:*
<code>
&lt;supplier name="LieferantA" supplierid="56847">
&lt;products category="Schuhe" categoryid="1234567">
&lt;items all="657">
</code>


### Inhaltsbereich

Im Inhaltsbereich müssen Sie den Spaltenbezeichnern aus dem Kopfbereich die richtigen Daten zuordnen. Auf der rechten Seite finden Sie dazu passend alle verfügbaren Werte (Platzhalter). Setzen Sie den Cursor mit der Maus in das Inhaltsfenster und klicken Sie auf einen der Platzhalter rechts. Bitte hier ebenfalls hinter jeden Wert den Platzhalter {#S#} einfügen (nicht beim letzten Wert!).

*Ein Beispiel für den Inhaltsbereich:*
<code>
[productid]{#S#}
[title]{#S#}
[description]{#S#}
[quantity]{#S#}
[weight]{#S#}
[size]{#S#}
[pic1]{#S#}
[pic2]{#S#}
[ean]{#S#}
...{#S#}
...{#S#}
[lstatus]
</code>

> Die Reihenfolge der Spalten im Kopfbereich muss mit der Reihenfolge im Inhaltsbereich übereinstimmen.

*und ein Content-Beispiel für eine XML-Datei:*
<code>
&lt;item>
&lt;title>Produktname&lt;/title>
&lt;price>Preis&lt;/price>
&lt;/item>
</code>


### Fußbereich

Hier können Sie den Footer für Ihre Schnittstelle einrichten (für CSV-Dateien nicht notwendig).
Diese Auswahl erscheint nur bei der XML-Schnittstelle.

*Beispiel für die XML-Datei:*
<code>
&lt;/items>
&lt;/products>
&lt;/supplier>
</code>


## Kategorien

Tragen Sie hier bitte Ihre Kategoriebezeichner ein. Sie finden diese dann danach im Bereich `Export->Kategoriezuordnung` als Spaltenname für Ihre Kategoriennamen bzw. IDs.

> Individuelle Schnittstellen benötigen zwingend Kategoriebezeichner!