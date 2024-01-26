# Export


## Hinweise

Die Auswahl der Schnittstelle, des passenden Exportprofils und der verschiedenen Bereiche des Exportprofils erfolgt im linken Menü. Einige Einstellungen können sich je nach Schnittstelle unterscheiden.

> Sie benutzen eine API-Schnittstelle?<br>
> Nach dem Export einer Produktneuanlage sollten Sie aktuelle Marktplatz- bzw. Shopdaten in unser System zurücklesen. Dies erfolgt im Bereich Listings und der Auswahl des jeweiligen Marktplatz oder Shops. Sie können dafür auch einen Cronjob benutzen, welchen Sie unter den jeweilgen Verbindungseinstellungen Ihres Systems mit CSV4YOU finden.
> Bei einigen Schnittstellen kann die Änderung eines Produkts nur über die Artikelnummern(ID´s) des externen Systems erfolgen. Sie können beim Export dann auch auswählen, ob Sie bei einem weiteren Export nur neue Produkte übertragen möchten oder bereits Gelistete. Das erspart Ressourcen, da nicht alle Daten übertragen werden müssen.

---

# Schnelleinstieg

Die meisten Schnittstellen haben weitere unterschiedliche Bereiche, welche Sie bei den jeweilgen Beschreibungen im Bereich der 'Schnittstellen' finden.
Hier erläutern wir nur die grundsätzliche Vorgehensweise, da diese auf fast alle Schnittstellen zutrifft.


### Schritt 1
Sie erstellen eine [Preiskalkulation](/export/pricecalculation) für den Export. Diese wird benötigt, wenn Sie mit anderen Preisen arbeiten möchten, welche aus den Produktpreisen im Datenpool berechnet werden.

Optional können Sie auch ein [Produkttemplate](/export/templates) anlegen.

Dieses wird z.B. in eBay benötigt, damit Ihre Produktbeschreibungen optimal für Suchmaschinen dargestellt werden. 
Mit dem Einsatz von HTML und CSS wird Ihnen ein professioneller Auftritt ähnlich einer kleinen Website ermöglicht.

> Einige Systeme benötigen sogenannte Artikelmerkmale, welche Sie für die internen Kategorien und/oder die Produkte angeben müssen. 
[Amazon](/interface/marketplace/amazon?id=artikelmerkmale), [eBay](/interface/marketplace/ebay?id=artikelmerkmale), [OTTO](/interface/marketplace/otto?id=artikelmerkmale) und [Home24](/interface/marketplace/home24?id=artikelmerkmale) sind einige davon.


### Schritt 2
Legen Sie ein neues Exportprofil für Ihre gewünschte Schnittstelle an und geben Sie diesem einen eindeutigen Namen. Füllen Sie die wichtigsten Felder aus.
Die Schnittstelle haben Sie vorher bereits unter [Abonnements](/account/abonnements) aktiviert.

### Schritt 3
Schauen Sie durch alle [Abschnitte des Exportprofiles](/export/interface), aktivieren Sie die notwendigen Einträge bzw. füllen Sie die gewünschten Felder aus. Auf der jeweiligen Seite das Speichern Ihrer Änderungen nicht vergessen!
Bei API´s müssen Sie unterscheiden, ob neue Artikel(Neu) oder bereits gelistete Artikel(Update) übertragen werden sollen. Am besten legen Sie für unterschiedliche Einstellungen verschiedene Exportprofile an.

[Was sind bereits gelistete Artikel?](/general/api?id=aktuelle-api-listings-abrufen)

### Schritt 4
Wenn Sie alle Bereiche bearbeitet haben, können Sie Ihre gewünschten Daten exportieren. Sollten Sie eine API benutzen, werden die Daten direkt zu Ihrem System gesendet. Voraussetzung dafür sind vorher hinterlegte Zugangsdaten im Bereich [Grundeinstellungen](/account/settings).

### Schritt 5
Nach dem Übertragen der Daten wird in den meisten Fällen eine Downloaddatei angeboten. Diese können Sie auf Ihrem lokalen Rechner speichern und ggf. weiterverarbeiten.

Bei API-Schnittstellen beinhaltet diese Datei die Statusmeldungen des externen Systems.
