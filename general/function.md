# Übersicht der erweiterten Feldfunktionen

Erweiterte Feldfunktionen sind speziell geeignet für individuelle Formatierungen, Berechnungen und Abfragen einzelner Spalteninhalte im Import und Export.
Bitte achten Sie auf die korrekte Verwendung der Pipe |, des einfachen Hochkommas ' und der geschwungenen und eckigen Klammern {} [].
Nachfolgend finden Sie alle aktiven Funktionen mit Beispielen.

> Verwenden Sie Funktionen bitte nur so wie hier in den Beispielen angegeben.

Wir leisten keinen Support für mehrfach bzw. fehlerhaft ineinander verschachtelte Funktionen, die nicht in den nachfolgenden Beispielen aufgeführt sind.


***
# Feldinhalte formatieren, berechnen und filtern

## replace - Feldinhalt ersetzen

Die Funktion replace ersetzt einen Wert durch einen anderen. Verwenden Sie als Trenner nicht die Pipe (|) und nicht den Wert, der ersetzt werden soll.
Ansonsten kann als Trenner ein beliebiges Zeichen festgelegt werden. Innerhalb von replace werden keine Hochkommas verwendet..

- Das Komma im Feld price wird durch einen Punkt ersetzt. Trenner ist der Doppelpunkt (:).

	``[price|replace:,:.]``

- Doppelte Doppelpunkte im Feld attributes werden durch einen Doppelpunkt ersetzt. Trenner ist das Doppelkreuz (#). Hier nicht den Doppelpunkt als Trenner verwenden, da die zu ersetzenden Werte Doppelpunkte sind!

	``[attributes|replace#::#:]``

- Aus dem Feld title werden die Wörter Anhänger in Schmuck Anhänger und Stecker in Ohrstecker ersetzt. Trenner ist der Doppelpunkt (:).

	``[title|replace:'Anhänger':'Schmuck Anhänger'{replace:'Stecker':'Ohrstecker'}]``


## find - Werte/Inhalte finden

- Es wird im Inhalt von FELDNAME nach dem Wert "sw" gesucht und wenn vorhanden im betreffenden Feld ID in den Wert "52368-schwarz" geändert (Rückgabewerte: 1 = gefunden, 0 = nicht gefunden). Verwenden Sie als Trenner nicht die Pipe (|) und nicht den Wert, der ersetzt werden soll. Ansonsten kann als Trenner ein beliebiges Zeichen festgelegt werden. ID 52368 dient hier nur als Beispiel:

	``{IF '[FELDNAME|find:sw]' == '1'}[ID]-schwarz{ENDIF}``


## truncate - Feldinhalt kürzen

> Endet die Kürzung in einem Wort, so wird dieses Wort nicht mit übergeben.


- Vom Feld 'Bildname1' Ihrer Importdatei werden nur die ersten 4 Zeichen ausgegeben bzw. importiert:

	``[pic1|truncate:4]``

- Aus Ihrer Art.-Nummer möchten Sie 6 Zeichen ab Position 3 importieren:

	``[itemno|truncate:6:3]``


## lowercase - Feldinhalt mit Kleinbuchstaben

- Bildname1 "GTN765.jpg" soll in Kleinbuchstaben (gtn756.jpg) umgewandelt werden:

	``[pic1|lowercase]``


## uppercase - Feldinhalt mit Großbuchstaben

- Bildname1 "gtne75.jpg" soll in Großbuchstaben (GTNE75.JPG) umgewandelt werden:

	``[pic1|uppercase]``


## capitalize - Anfangsbuchstaben Wörter groß schreiben

- Die Anfangsbuchstaben im Feld color "Farben: schwarz, rot, blau" in Großbuchstaben umwandeln (Farben: Schwarz, Rot, Blau):

	``[color|capitalize]``


## capitalize-f - Anfangsbuchstabe Inhalt groß schreiben

- Nur den ersten Buchstaben des kompletten Inhaltes im Feld title "mein tolles Produkt" groß schreiben (Mein tolles Produkt):

	``[color|capitalize-f]``


## len - Länge des Inhaltes

- Sie benötigen die Länge des Feldes title (Rückgabe ist die Anzahl der Zeichen):

	``[title|len]``

- Die Anzahl der Zeichen im Feld title wird abgefragt und gleichzeitig mit einer IF-Bedingung verküpft. Wenn weniger als 50 Zeichen im Feld title, dann schreibe StartText vor den Titel:

	``{IF '[title|len]' < '50'}StartText{ENDIF}[title]``


## net - Preis Netto

- Ihre Importdatei beinhaltet Bruttopreise. Sie benötigen den Preis jedoch netto, abzgl. (19%) Mehrwersteuer:

	``[price|net]``


## html - Texte mit Html

- Alle Beschreibungstexte sollen mit HTML-Befehlen importiert werden (wenn vorhanden):

	``[description|html]``


## text - Texte ohne Html mit Zeilenumbrüchen

- Aus den Artikelbeschreibungen Ihrer Importdatei werden ggf. vorhandene HTML-Tags entfernt und nur der eigentliche Text wird importiert. Zeilenumbrüche im Text werden formatiert ausgegeben:

	``[description|text]``


## clear - Texte ohne Html und ohne Zeilenumbrüche

- Alle Beschreibungen werden unformatiert und ohne Zeilenumbrüche als fortlaufender Text dargestellt:

	``[description|clear]``


## split - Extrahieren von Daten aus einem Datenfeld mit Trennern

- Feldinhalt sieht wie folgt aus: "Bildpfad1|Bildpfad2|Bildpfad3]". Als Datentrenner im System bei uns ist als Standardtrenner die Pipe | voreingestellt (senkrechter Strich). Es soll nur der Wert 'Bildpfad2' übernommen werden:

	``[FeldNameBild|split:2]``

- Feldinhalt: "Bildpfad1->Bildpfad2->Bildpfad3". Datentrenner Bindestrich und Pfeil nach rechts "->" (als Beispiel für einen eigenen Trenner). Aus dem Feldinhalt mit 3 Werten soll nur der Wert "Bildpfad3" übernommen werden:

	``[FeldNameBild|split:3:->]``

- Feldinhalt eines Feldes 'Category': "Möbel|Wohnzimmer|Sessel". Datentrenner ist wieder die Pipe. Wenn Sie einen anderen Trenner verwenden, dann bitte im Beispiel 2 schauen. In 3 Spalten wird die Übernahme der einzelnen Werte "Möbel", "Wohnzimmer" und "Sessel" wie folgt vorbereitet:

	``[Category|split:1]``
	``[Category|split:2]``
	``[Category|split:3]``


## math - Berechnungen

> Bitte beachten: Innerhalb von Berechnungen mit math funktionieren keine IF/ELSE-Anweisungen!

- Addiere 100 auf den aktuellen Preis:

	``[math|price+100]``

- Multipliziere den aktuellen Preis mit 1.5, benutze als Dezimaltrennzeichen den Punkt:

	``[math|price*1.5|.]``

- Addiere Inhalte aus den Feldern 'price' und 'shippingCost':

	``[math|price+shippingCost]``

- Addiere/berechne 4 Werte in einem Feld: Importpreis [price_list] + Mehrwertsteuer [vat] + 20% Aufschlag + 5 Euro pauschal

	``[math|price_list*1.vat*1.2+5]``

- Wert in Importpreis [price_list] ist z.B. 'VK25.25'. 'VK' soll durch nichts ersetzt, also gelöscht werden (replace innerhalb von math funktioniert nicht!):

    Schema: [math|Spalte+Berechnung|Dezimaltrenner|Suchwert(|Ersatzwert Optional)]

	``[math|price_list|.|VK]``

- Wert in Importpreis [price_list] ist z.B. '30.50 USD '. 'USD' soll in EUR ersetzt, umgerechnet und Dezimaltrenner soll das Komma werden:

    Schema: [math|Spalte+Berechnung|Dezimaltrenner|Suchwert(|Ersatzwert Optional)]

	``[math|price_list*0.9|,|USD|EUR]``


## date() - Datumswerte

- Aktuelles Startdatum mit Angabe Stunde und Minute (z.B. für Auktionen):

	``date(d.m.Y H:i)``

- Aktuelles Startdatum mit zusätzlicher Angabe der Sekunden ausgeben:

	``date(d.m.Y H:i:s)``

- Startdatum mit Stunde und Minute jedoch 2 Tage zurück gesetzt:

	``date(d.m.Y H:i|-2)``


## seo - Zeichenkette für Suchmaschinen optimieren

- Text im Titel wird für Suchmaschinen optimiert ausgegeben:

	``[title|seo]``


## match - Textsegmente in Zeichenketten finden (optional entfernen)

- Ihre Beschreibung enthält jede Menge Text. Sie benötigen jedoch nur einen bestimmten Teil daraus. Geben Sie dafür einen ganz bestimmten Start- und Endtext als Suchmuster z.B. aus Ihrer Produktbeschreibung ein. Alles zwischen TEXTVON und TEXTBIS wird dann ausgelesen und als Wert zurückgegeben. TEXTVON und TEXTBIS müssen Sie natürlich durch Ihre eigenen Werte ersetzen:

	``[description|match:'TEXTVON':'TEXTBIS']``

- gefundenes Textsegment inklusive TEXTVON und TEXTBIS entfernen:

	``[description|match:'TEXTVON':'TEXTBIS',1]``


***
# Verknüpfung von Funktionen

## [func1 {func2}] - Zwei Funktionen verbinden

- Ersetzt in einem String https in http und a-domain.com in b-domain.com:

	``[pic1|replace:'https':'http'{replace:'a-domain.com':'b-domain.com'}]``

- Sie möchten Datumswerte, z.B. "10.09.2015 17:55:49" in "10.09.2016" ändern. Dazu muss der 1. Teil des Datums gesucht und '2015' durch '2016' ersetzt werden. Der Trenner ist das Leerzeichen:

	``[Datum|split:1:{replace:'2015':'2016'}]``


## [func1 {func2}{func3}] - Drei Funktionen verbinden

- Der Titel "Kette, schwarz-rot Metallik, 80cm" wird in "metallic" umgewandelt. Dazu muss der 3. Teil des Titels gesucht, alle Buchstaben klein geschrieben und ein Buchstabe ersetzt werden. Als Trennzeichen der Werte innerhalb des Titels wird das Leerzeichen definiert (vor der ersten geschwungenen Klammer):

	``[title|split:3:{lowercase}{replace:'k':'c'}]``


***
# Bedingte Anweisungen und Verzweigungen (Abfragen)

## IF - Anweisung

- Wenn 'SpalteBestand' Wert größer 5, schreibe 5 - ansonsten schreibe nichts in das Feld:

	``{IF '[SpalteBestand]' > '5'}5{ENDIF}``


## IF-ELSE - Anweisung

- Wenn 'SpalteVerfuegbar' Wert nicht wie 'ja', schreibe 0 - ansonsten schreibe 1.

	``{IF '[SpalteVerfuegbar]' != 'ja'}0{ELSE}1{ENDIF}``

- Wenn 'Lager' Wert leer, schreibe 'nein' - ansonsten schreibe 'ja'.

	``{IF '[Lager]' == ''}nein{ELSE}ja{ENDIF}``

- Wenn 'FeldinDatei' nicht leer, schreibe Wert aus 'FeldinDatei' - ansonsten schreibe 'No Name' in das Feld.

	``{IF '[FeldinDatei]' != ''}[FeldinDatei]{ELSE}No Name{ENDIF}``


## IF-ELSEIF-ELSE - Anweisung

- Wenn 'SpalteVerfuegbar' Wert=nein, schreibe 0 - wenn 'SpalteVerfuegbar' Wert=ja, schreibe 1 - wenn Beides nicht zutrifft schreibe nichts in das Feld.

	``{IF '[SpalteVerfuegbar]' == 'nein'}0{ELSEIF '[SpalteVerfuegbar]' == 'ja'}1{ELSE}{ENDIF}``

- ist etwas komplexer. Es gibt z.B. Variantenfelder für Konfektionsgrößen. Der folgende Code ersetzt die Größenangaben 36-54 aus der Importdatei (Feldname: 'Variation_Size') in die gewünschten Buchstaben-Größenbezeichner, z.B. S, M, L, XL usw.:

	<code>{IF '[Variation_Size]' == '36'}XXS
	{ELSEIF '[Variation_Size]' == '38'}XS
	{ELSEIF '[Variation_Size]' == '40'}S
	{ELSEIF '[Variation_Size]' == '42'}M
	{ELSEIF '[Variation_Size]' == '44'}L
	{ELSEIF '[Variation_Size]' == '46'}XL
	{ELSEIF '[Variation_Size]' == '48'}XXL
	{ELSEIF '[Variation_Size]' == '50'}3XL
	{ELSEIF '[Variation_Size]' == '52'}4XL
	{ELSEIF '[Variation_Size]' == '54'}5XL
	{ELSE}6XL
	{ENDIF}</code>


## IF-ELSE-ELSE - Anweisung

- Wenn Spalte 'Aktiv' Wert='Ja', übernehme Wert aus Spalte 'Bestand' - ansonsten wenn Wert 'Bestand' größer 10, schreibe '10' - ansonsten schreibe '0' in das Feld.

	``{IF '[Aktiv]' == 'Ja'}[Bestand]{ELSE}{IF '[Bestand]' > '10'}10{ELSE}0{ENDIF}{ENDIF}``


***
# Fehlerquellen in Funktionen

Werden innerhalb eines IF-Zweigs Funktionen mit Zahlen verwendet, so muss der zu prüfende WERT entweder ganzahlig sein oder als Dezimaltrennzeichen den Punkt verwenden.

> {IF '[WERT]' < '5'} usw. ... 'WERT' kann z.B. 10, 20.50 oder 23.32 sein. Werte mit Komma als Dezimaltrennzeichen funktionieren in IF-Verzweigungen nicht.

