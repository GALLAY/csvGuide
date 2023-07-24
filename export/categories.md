# Kategoriezuordnung

Mit Hilfe von Kategoriezuordnungen können Sie eigene Kategoriebezeichnungen oder Kategorie-IDs für Ihre Schnittstelle definieren, die mit den Kategorien in Ihrem Shopsystem oder auf einem Marktplatz übereinstimmen müssen. Nur so kann eine erfolgreiche Zuordnung der Produkte in die passenden Kategorien Ihres Shopsystem oder Marktplatzes erfolgen.

Zu jeder Schnittstelle bzw. für jedes Exportprofil lassen sich unterschiedliche Kategoriezuordnungen speichern.

> Eine Ausnahme stellen Amazon, eBay, Home24 und OTTO da. Diese Zuordnungen erfolgen direkt über die internen Kategorien oder Produkte.

***
# Übersicht vorhandener Kategoriezuordnungen

![Übersicht vorhandener Kategoriezuordnungen](https://data.csv4you.com/media/image/guide/export/export-kategoriezuordnung-uebersicht.png ':zoom :size=30%')

Klicken Sie die gewünschten Schnittstelle an bzw. auf eine der verfügbaren Optionen.
Wird keine Schnittstelle angezeigt, muss zuerst eine neu abonniert werden (siehe `Mein Konto->Abonnements`).
Eigene Schnittstellen erstellen Sie über den Bereich `Export->Individuelle Schnittstellen`.

> Voraussetzung für das Anlegen eine Kategoriezuordung: In der Datenquelle muss mindestens eine Interne Kategorie mit Produkten vorhanden sein.

***
# Eintrag bearbeiten

![Vorhandenen Eintrag bearbeiten](https://data.csv4you.com/media/image/guide/export/export-kategoriezuordnung-bearbeiten.png ':zoom :size=30%')

- **Name der Kategoriezuordnung**<br>
	Geben Sie der Kategoriezuordung Ihrer Schnittstelle einen aussagekräftigen Namen (frei wählbar).

- **Zuweisung der externen Kategorie-Namen oder -ID´s**<br>
	Links sehen Sie die ID und den internen Kategorienamen aus Ihrem Datenpool. Tragen Sie zu jeder dieser internen Kategorien die passende Nummer oder Bezeichnung Ihrer Schnittstellenkategorie ein, also den Kategorienamen oder die Kategorienummer Ihres Shops. Die eingetragenen Werte werden als Kategoriezuordnung zu jedem Produktdatensatz in Ihre CSV-Datei übernommen.

	Bei einigen Schnittstellen können Sie mit der angezeigten Lupe direkt die Kategorien Ihres externen Systems aussuchen. Voraussetzung ist die hinterlegung der API-Zugangsdaten.

> Falls Sie keine eigenen Kategorien eintragen, sind später in Ihrer Exportdatei auch keine Kategorien vorhanden, d.h. die Inhalte der Kategoriespalten bleiben leer. Dies führt oft zu Fehlermeldungen beim Import der CSV-Datei in Ihr Shopsystem. Es sollte daher immer eine Kategoriezuordnung angelegt sein.


***
# Sicherung exportieren

Exportieren Sie eine ausgewählte Kategoriezuordnung. Dazu müssen bereits Werte gespeichert sein. Öffnen Sie die exportierte Datei mit MS-Excel oder einem geeigneten Editor und tragen Sie dann die Kategoriebezeichnungen (oder IDs) Ihres Shops in die dafür vorgesehenen Spalten ein.


***
# Sicherung importieren

Importieren Sie eine fertig ausgefüllte Datei wieder in das System. Bitte beachten Sie, dass ID-Nummern und Kategoriebezeichnungen in Export- und Importdatei übereinstimmen müssen. Achten Sie bitte auch auf Unterschiede in Groß- und Kleinschreibung!