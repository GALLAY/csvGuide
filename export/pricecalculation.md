# Preiskalkulation

Eine Preiskalkulation wird verwendet, um Preise aus dem Datenpool für einen Shop oder Marktplatz zu kalkulieren.
Preiskalkulationen werden im Exportprofil im Bereich Grundeinstellungen eingebunden. Sie können beliebig viele Kalkulationen verwalten.

**Bitte beachten!**

Ihre Preiskalkulation sollte `alle möglichen Kosten` beinhalten. Ist Ihr Preis im Datenpool ein Nettoeinkaufspreis,
dann müssen Sie die für das jeweilige Land geltende Mehrwertsteuer hinzurechnen. Diese wird von unserem System nicht mit eingerechnet.

**Weiter Kosten können sein:**

	- Versandkosten/Dropshippinggebühr des Lieferanten
	- Marktplatzgebühr
	- Verkaufsgebühr
	- Rücksendekosten Ihres Kunden
	- Mehrwertsteuer u.a.


Natürlich dürfen Sie Ihre gewünschte Gewinnmarge nicht vergessen.

***
# Übersicht der vorhandenen Preiskalkulationen

Legen Sie eine neue Preiskalkulation an oder bearbeiten eine bereits bestehende Preiskalkulation.

![Übersicht der vorhandenen Preiskalkulationen](https://data.csv4you.com/media/image/guide/export/export-preiskalkulation-uebersicht.png ':zoom :size=30%')

***
# Eintrag bearbeiten

![Vorhandenen Eintrag bearbeiten](https://data.csv4you.com/media/image/guide/export/export-preiskalkulation-bearbeiten.png ':zoom :size=30%')

- **Name**<br>
	Geben Sie Ihrer Preiskalkulation einen aussagekräftigen Namen.

- **kurze Beschreibung**<br>
	Ihre individuelle Beschreibung für diese Preiskalkulation

Als Basis für die Berechnung Ihrer Preise im jeweiligen Exportprofil werden standardmäßig die Einträge im Feld Preis der aktiven Datenquelle verwendet (siehe Datenpool->Produkte).

?> Fixkosten können Sie in das Feld für den Preisaufschlag schreiben. Das erleichtert in einigen Fällen die Kalkulation.


#### Beispiel für ein Produkt mit der passenden Preistaffel

Ihre Preisstaffel für Produkte kann folgendermaßen aussehen (Beispiel):

| Einkaufspreis von | Einkaufspreis bis | x Preisfaktor | + Preisaufschlag |
| --- | --- | --- | --- |
| 0.01 | 2.99 | 2.500 | 4.00 |
| 3.00 | 9.99 | 2.000 | 4.00 |
| 10.00 | 19.99 | 1.900 | 4.00 |
| ... | ... | ... | ... |

Jede Zeile steht dabei für unterschiedliche Preise der Produkte aus dem Datenpool.


Unser Beispielprodukt hat einen Preis von 8.00 EUR und würde damit in die 2. Preisstaffel fallen.<br>
Kalkulierter Wert in Ihrer Exportdatei ist dann: **(8 x 2.000 + 4.00)**

Der berechnete Verkaufspreis für dieses Produkt: **20.00 EUR**


#### Die besondere Bedeutung der Spalte Extra (Sonderpreis)

Einträge in dieser Spalte können für Sonderpreise, reduzierte Preise, Aktionspreise u.ä. verwendet werden. Speichern Sie dort z.B. -10% wird der kalkulierte Preis abzüglich 10% berechnet.
Alle Werte sind dann über den Platzhalter Sonderpreis `[price_extra]` verfügbar. Sie lassen sich im Reiter eigene Spaltenzuordung zuweisen und in Ihrem Exportprofil übernehmen.
In einigen Schnittstellen erfolgt die Zuordnung des Platzhalters Sonderpreis automatisch.
