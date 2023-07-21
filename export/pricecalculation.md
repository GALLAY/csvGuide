# Preiskalkulation

Eine Preiskalkulation wird verwendet, um Preise aus dem Datenpool für eine Schnittstelle zu kalkulieren.
Legen Sie eine neue Preiskalkulation für ein Exportprofil an oder bearbeiten Sie eine bereits bestehende Kalkulation.
Preiskalkulationen werden im Exportprofil unter dem Bereich Grundeinstellungen eingebunden. Sie können beliebig viele Kalkulationen verwalten.


***
# Übersicht der vorhandenen Preiskalkulationen

![Übersicht der vorhandenen Preiskalkulationen](https://data.csv4you.com/media/image/guide/export/export-preiskalkulation-uebersicht.png ':zoom :size=30%')

***
# Eintrag bearbeiten

![Vorhandenen Eintrag bearbeiten](https://data.csv4you.com/media/image/guide/export/export-preiskalkulation-bearbeiten.png ':zoom :size=30%')

- **Name**<br>
	Geben Sie Ihrer Preiskalkulation einen aussagekräftigen Namen.

- **kurze Beschreibung**<br>
	Ihre individuelle Beschreibung für diese Preiskalkulation

Als Basis für die Berechnung Ihrer Preise im jeweiligen Exportprofil werden standardmäßig die Einträge im Feld Preis der aktiven Datenquelle verwendet (siehe Datenpool->Produkte).


#### Ein Beispiel

| Spalte | Wert |
| --- | --- |
| Preis in Datenquelle	| 8,00 |
| Einkaufspreis von | 3,00 |
| Einkaufspreis bis| 10,00 |
| x Preisfaktor | 2,000 |
| + Preisaufschlag | 4,00 |
| **Kalkulierter Wert in Ihrer Exportdatei (8 x 2 + 4)** | **20,00** |


#### Die Spalte Extra (Sonderpreis) hat eine besondere Bedeutung

Einträge in dieser Spalte können für Sonderpreise, reduzierte Preise, Aktionspreise u.ä. verwendet werden. Speichern Sie dort z.B. -10% wird der kalkulierte Preis abzüglich 10% berechnet.
Alle Werte sind dann über den Platzhalter Sonderpreis `[price_extra]` - verfügbar. Sie lassen sich im Reiter eigene Spaltenzuordung zuweisen und in Ihrem Exportprofil übernehmen.
In einigen Schnittstellen erfolgt die Zuordnung des Platzhalters Sonderpreis automatisch.