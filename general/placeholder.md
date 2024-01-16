# Übersicht der Platzhalter

Sie können diese Platzhalter für Angaben in den Artikelmerkmalen, für die Produkttemplates sowie den Export benutzen.

!> Platzhalter müssen immer in eckigen Klammern stehen.

> Beim Import stehen Ihnen diese Platzhalter nicht zur Verfügung.
Sie müssen dort immer die Spaltennamen der Importdateien als Platzhalter benutzen.
Es stehen Ihnen dort nur die [erweiteren Feldfunktionen](general/function) zur Verfügung.


***
# Eigenschaften

| Wert | Platzhalter |
| --- | --- |
| Breite | [width] |
| Geschlecht | [gender] |
| Gewicht | [weight] |
| Gewicht in KG | [weightKG] |
| Größe | [size] |
| Höhe | [height] |
| Länge | [length] |
| Ringgröße | [ringsize] |


***
# Preise

| Wert | Platzhalter |
| --- | --- |
| Alter Preis | [price_old] |
| Einkaufspreis | [price_ek] |
| Grundpreis | [price_basic] |
| Grundpreis Einheit | [basepriceunit] |
| Grundpreis Inhalt | [basepricecontent] |
| Mehrwertsteuer | [vat] |
| Preis | [price] |
| Preis 2 | price2] |
| Preis 3 | [price3] |
| Preis 4 | [price4] |
| Preis 5 | [price5] |
| Sonderpreis | [price_extra] |
| UVP | [price_uvp] |


***
# Stammdaten

| Wert | Platzhalter |
| --- | --- |
| Beschreibung | [description] |
| Bulletpoint 1 | [bullet1] |
| Bulletpoint 2 | [bullet2] |
| Bulletpoint 3 | [bullet3] |
| Bulletpoint 4 | [bullet4] |
| Bulletpoint 5 | [bullet5] |
| Farbe | [color] |
| Keywords | [keys] |
| Kurzbeschreibung | [small_description] |
| Material | [material] |
| Name/Titel | [title] |
| SearchTerms 1 | [searchTerms1] |
| SearchTerms 2 | [searchTerms2] |
| SearchTerms 3 | [searchTerms3] |
| SearchTerms 4 | [searchTerms4] |
| SearchTerms 5 | [searchTerms5] |
| Verpackungseinheit (Bsp. 1) | [piece] |
| Verpackungseinheit (Bsp. 1Stck) | [pieceunit] |
| Verpackungseinheit (Bsp. Stck) | [unit] |

> Sollten Sie weitere Sprachen benutzen, können Sie durch anhängen eines Unterstrichs mit der passenden SprachID auf diese Werte zugreifen.

**Beispiel**<br>
Name/Titel aus Sprache 2: `[title_2]`


***
# Bilder

| Wert | Platzhalter |
| --- | --- |
| 1. Bild / Bild-URL | [pic1] / [pic1url] |
| 2. Bild / Bild-URL | [pic2] / [pic2url] |
| 3. Bild / Bild-URL | [pic3] / [pic3url] |
| 4. Bild / Bild-URL | [pic4] / [pic4url] |
| 5. Bild / Bild-URL | [pic5] / [pic5url] |
| 6. Bild / Bild-URL | [pic6] / [pic6url] |
| 7. Bild / Bild-URL | [pic7] / [pic7url] |
| 8. Bild / Bild-URL | [pic8] / [pic8url] |
| 9. Bild / Bild-URL | [pic9] / [pic9url] |
| 10. Bild / Bild-URL | [pic10] / [pic10url] |


***
# Parent Bilder

| Wert | Platzhalter |
| --- | --- |
| 1. Bild / Bild-URL | [parent_pic1] / [parent_pic1url] |
| 2. Bild / Bild-URL | [parent_pic2] / [parent_pic2url] |
| 3. Bild / Bild-URL | [parent_pic3] / [parent_pic3url] |
| 4. Bild / Bild-URL | [parent_pic4] / [parent_pic4url] |
| 5. Bild / Bild-URL | [parent_pic5] / [parent_pic5url] |
| 6. Bild / Bild-URL | [parent_pic6] / [parent_pic6url] |
| 7. Bild / Bild-URL | [parent_pic7] / [parent_pic7url] |
| 8. Bild / Bild-URL | [parent_pic8] / [parent_pic8url] |
| 9. Bild / Bild-URL | [parent_pic9] / [parent_pic9url] |
| 10. Bild / Bild-URL | [parent_pic10] / [parent_pic10url] |


***
# Kategorien

| Wert | Platzhalter |
| --- | --- |
| Interne Kategorie-ID | [catID] |
| 1. Kategorie | [category1] |
| 2. Kategorie | [category2] |
| 3. Kategorie | [category3] |
| 4. Kategorie | [category4] |
| 5. Kategorie | [category5] |


***
# Sonstige

| Wert | Platzhalter |
| --- | --- |
| Datum | [date] |
| Hersteller | [manufacturer] |
| Hersteller Artikelnummer | [manufacturerItemno] |
| Hersteller ID | [manufacturerID] |
| Infotext | [info] |
| Lieferstatus (0 oder 1) | [lstatus] |
| Lieferzeit | [deliveryTime] |
| Marke | [brand] |
| Versandgröße | [shippingSize]


***
# Freifelder/Variationen

Im Bereich [Mein Konto->Grundeinstellungen->Freifelder/Variationen](account/datasource?id=freifeldervariationen-einrichten) können bis zu 20 individuelle Freifelder definiert werden,
z.B. für Spalten einer Importdatei, die zu keinem der vorhandenen Feldbezeichner passen.
Die Zuweisung von Freifeldern erfolgt in den Import- und Exporteinstellungen über die Platzhalter [spec1], [spec2], usw. ... bis [spec20].


| Wert | Platzhalter |
| --- | --- |
| Freifeld 1 | [spec1] |
| Freifeld 3 | [spec2] |
| Freifeld 3 | [spec3] |
| ... | ... |
| Freifeld 20 | [spec3] |


***
# eigene Platzhalter

Der Zugriff auf diese erfolgt in nachfolgender Schreibweise:
	`[own-NAMEDESPLATZHALTERS]`

**Beispiel**<br>
* Ihr hinterlegter Platzhalter hat den Namen Test. Der Platzhalter heißt dementsprechend: `[own-Test]`

!> Eigene Platzhalter sind in allen Datenquellen gültig.


***
# eigene Artikelmerkmale

Der Zugriff auf diese erfolgt in nachfolgender Schreibweise:
	`[feature-NAMEDESPLATZHALTERS]`

**Beispiel**<br>
* Ihr hinterlegter Platzhalter hat den Namen Hausnummer. Der Platzhalter heißt dementsprechend: `[feature-hausnummer]`<br>
Es erfolgt eine Umwandlung in SEO konforme Schreibweise.

!> Eigene Artikelmerkmale sind nur in der jeweiligen Datenquelle gültig.

