# Grundeinstellungen

***
# Datenquellen

Da dieser Bereich sehr viele Informationen beinhaltet, wird er in einem [eigenen Bereich](account/datasource) erklärt.


***
# FTP - Server

![Übersicht hinterlegter FTP-Server](https://data.csv4you.com/media/image/guide/meinkonto/ftp/meinkonto-ftp-uebersicht.png ':zoom :size=30%')
![FTP-Server bearbeiten](https://data.csv4you.com/media/image/guide/meinkonto/ftp/meinkonto-ftp-bearbeiten.png ':zoom :size=30%')

Hinterlegen Sie hier die Zugriffsdaten für Ihren FTP-Server. Damit können Importdaten per FTP-Protokoll automatisch zu bestimmten Zeiten über das Setzen von Cronjobs von diesem Server abgeholt und aktualisiert werden. Zusätzlich lassen sich damit Bilder und Exporte auf Ihren FTP-Server übertragen.

> Legen Sie aus Sicherheitsgründen bitte einen separaten FTP-Benutzer mit eingeschränkten Rechten für CSV4YOU auf Ihrem Server an.
> Dieser FTP-Benutzer sollte lediglich Zugriff auf einen ganz bestimmten Unterordner Ihres Servers haben, in den Sie Ihre CSV-Daten übertragen möchten.
> Geben Sie diesem Benutzer keine administrativen Rechte für außerhalb bzw. oberhalb liegende Verzeichnisse auf Ihrem Webserver.

Sie können in den meisten Fällen auch per WEB-URL auf Ihren FTP-Server zugreifen, weswgen Sie keinen FTP-Server anlegen müssen.

**Format**<br>
https://FTP-Benutzer:FTP-Passwort@www.meineseite.de/dateiname.csv


***
# API

![Verbindung mit einer API herstellen - Bsp. Gambio](https://data.csv4you.com/media/image/guide/meinkonto/grundeinstellungen/meinkonto-grundeinstellungen-api-verbinden.png ':zoom :size=30%')

Hinterlegen Sie unter 'Mein Konto->Grundeinstellungen->API' die passenden Zugangsdaten für Ihr System. Bei einigen Systemen werden Sie direkt auf deren Webseite umgeleitet, um den Zugriff von CSV4YOU zu bestätigen.

> Wir greifen mit der API nur auf die hinterlegten Funktionen bei dem jeweiligen Shop oder Marktplatz zu. Eine Änderung an irgendeiner Funktion ist nicht möglich


***
# Amazon

![Verbindung mit Amazon herstellen](https://data.csv4you.com/media/image/guide/meinkonto/grundeinstellungen/meinkonto-grundeinstellungen-amazon-verbinden.png ':zoom :size=30%')

Für die Verbindung unseres Systems mit Ihrem Amazon-Account benötigen Sie einen eigenen Entwicklerzugang. Weitere Informationen zur Einrichtung finden Sie hier: https://jesseevers.com/selling-partner-api-access/
Laut Amazon muss der hinterlegte LWA-Schlüssel alle 180 Tage erneuert werden.


***
# eBay

![Verbindung mit eBay herstellen](https://data.csv4you.com/media/image/guide/meinkonto/grundeinstellungen/meinkonto-grundeinstellungen-ebay-verbinden.png ':zoom :size=30%')

Die Einrichtung der eBay-Verbindung ist notwendig, um Daten zwischen eBay und CSV4YOU austauschen zu können. Dabei wird eine sichere OAUTH-Verbindung erstellt, welche bei Erfolg einen gültigen TOKEN zurück gibt


***
# eigene Platzhalter

![Übersicht eigene Platzhalter](https://data.csv4you.com/media/image/guide/meinkonto/eigeneplatzhalter/meinkonto-eigeneplatzhalter-uebersicht.png ':zoom :size=30%')
![eigene Platzhalter bearbeiten](https://data.csv4you.com/media/image/guide/meinkonto/eigeneplatzhalter/meinkonto-eigeneplatzhalter-bearbeiten.png ':zoom :size=30%')

Benutze Sie diese Seite, um Platzhalter mit eigenen Informationen für den Export zu hinterlegen.
Der Zugriff auf diese erfolgt in nachfolgender Schreibweise: [own-NAME_DES_PLATZHALTERS]

**Beispiel**<br>
Ihr hinterlegter Platzhalter hat den Namen Test. Der Platzhalter heist dementsprechend: [own-Test]


***
# E-Mail-Konto hinterlegen

![Übersicht hinterlegte E-Mail-Konten](https://data.csv4you.com/media/image/guide/meinkonto/grundeinstellungen/datenquellen/meinkonto-datenquellen-email.png ':zoom :size=30%')

Hinterlegen Sie hier die Zugangsdaten für Ihre E-Mail-Konten. Damit können Exporte über Ihre eigenen E-Mail Adressen versendet werden.


***
# Persönliche Angaben

Speichern Sie hier Ihre Firmen- und Kontakdaten.
Sie können von dieser Seite aus auch Ihren CSV4YOU-Account löschen


***
# Zwei-Faktor-Authentisierung (E-Mail, APP)

Entscheiden Sie hier, ob Sie die Zwei-Faktor-Authentisierung benutzen möchten. Damit ist ein Login nur mit einem eingegebene, Zufalls-Code möglich.
Wahlweise über die hinterlegte E-Mail Adresse oder mit der [Google Authenticator](https://support.google.com/accounts/answer/1066447?hl=de&co=GENIE.Platform%3DAndroid) APP.
