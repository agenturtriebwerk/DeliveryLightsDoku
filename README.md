Lieferampel Dokumentation (DeliveryLights)
==================

Die Lieferampel ist ein Shopware-Plugin und kann über den Shopware Community Store bezogen werden: 
Beschreibung und Download im Shopware Community Store

# Beschreibung
Mit dem Plugin "Lieferampel" wird die Darstellung von Lieferbarkeit erweitert und die Steuerung der Anzeige erleichtert.


# Installation
## Manueller Upload
1. Extrahieren Sie die Inhalte aus der heruntergeladenen ZIP-Datei
2. Laden Sie den Ordner /TriebwDeliveryLights per FTP auf Ihren Webserver in den Ordner /engine/Shopware/Plugins/Local/Backend/.
3. Loggen Sie sich nun in Ihr Shopware-Backend ein.
4. Wählen Sie „Einstellungen“ -> „Plugin-Manager“.
5. Wählen Sie im „Plugin-Manager“ im linken Menü „Alle Erweiterungen“.
6. Suchen Sie in der Auflistung der „inaktiven Plugins“ nach „Lieferampel“.
7. Klicken Sie in der Zeile von „Lieferampel“ rechts auf das grüne Symbol. Das Plugin wird jetzt installiert. Wenn die Installation abgeschlossen ist, erscheint rechts oben im Backend eine Info dass das Plugin erfolgreich installiert wurde.
8. Im nun sich öffnenden Popup wählen Sie „Plugin aktivieren“, nehmen die gewünschten Grundeinstellungen vor und klicken auf "Plugin-Einstellungen speichern"


## Installation über den Community Store
1. Loggen Sie sich nun in Ihr Shopware-Backend ein.
2. Wählen Sie „Einstellungen“ -> „Plugin-Manager“.
3. Wählen Sie den Tab "Community Store" und suchen " Lieferampel "
4. Laden Sie das Plugin in Ihr System
5. Öffnen Sie im Plugin-Manager den Tab "Einkäufe / Erweiterung" und folgen dem manuellen Upload ab Schritt 5


## Konfiguration des Plugins
1. Öffnen Sie die Grundeinstellungen und wählen dort "Weitere Einstellungen" > " Lieferampel "
2. Nehmen Sie die gewünschten Anpassungen vor und klicken auf "Speichern"
3. Um die Berechnung des Tagesentnahme zu berechnen, aktivieren Sie die den Cron-Job in den Grundeinstellungen unter "System" > "Cronjobs"


# Plugin-Einstellungen
![Grundeinstellungen](http://doku.agentur-triebwerk-shop.de/deliverylights/artikeleinstellungen_2.png)
## Einstellungen
* Steuerung über Tagesentnahme aktiv : ja/nein
** Entscheiden Sie ob die Lieferampel die Tagesentnahme der Artikel berechnen soll und mit dieser Tagesentnahme und der vorgegebenen Artikelreichweite (in Tagen) die Anzeige gesteuert werden soll. Kann keine sinnvolle Tagesentnahme berechnet werden (zum Beispiel weil der Artikel noch nie verkauft wurde) greift die Lieferampel auf die eingestellten Lagerbestandsmengen als Steuerungsgröße zurück.
* Artikel vor Einführungsdatum bestellbar: ja/nein
** Entscheiden Sie ob Artikel vorbestellt, also vor dem "Erscheinungsdatum" (in den Stammdaten des Artikels) bestellt werden kann.


## Einstellung für Rote Ampel: 
![Grundeinstellungen](http://doku.agentur-triebwerk-shop.de/deliverylights/status_rot.png)
* Artikelreichweite (in Tagen) mindestens: [Tage, ganze positive Zahl]
* * Bei Erreichen der hier festgelegten Grenzwerte wird die "Rote Ampel" angezeigt. Falls aktiv und berechnet hat die Berechnung über die Tagesentnahme Vorrang.
* Lagerbestand (in Stück) mindestens: [Stück, ganze positive Zahl]
** Bei Erreichen der hier festgelegten Grenzwerte wird die "Rote Ampel" angezeigt. Falls aktiv und berechnet hat die Berechnung über die Tagesentnahme Vorrang.
* Beschreibung: [Text, maximal 48 Zeichen]
** Neben der Ampelfarbe wird die erklärende Beschreibung als Text mit angezeigt.

## Einstellung für Gelbe Ampel:
![Grundeinstellungen](http://doku.agentur-triebwerk-shop.de/deliverylights/status_gelb.png)
* Artikelreichweite (in Tagen) mindestens: [Tage]
** Bei Erreichen der hier festgelegten Grenzwerte wird die "Gelbe Ampel" angezeigt. Falls aktiv und berechnet hat die Berechnung über die Tagesentnahme Vorrang. Die hier festgelegten Grenzwerte sollten über (großer als) denen der "Roten Ampel" liegen.
* Lagerbestand (in Stück) mindestens: [Stück]
** Bei Erreichen der hier festgelegten Grenzwerte wird die "Gelbe Ampel" angezeigt. Falls aktiv und berechnet hat die Berechnung über die Tagesentnahme Vorrang. Die hier festgelegten Grenzwerte sollten über (großer als) denen der "Roten Ampel" liegen.
* Beschreibung: [Text, maximal 48 Zeichen]
** Neben der Ampelfarbe wird die erklärende Beschreibung als Text mit angezeigt.

## Einstellung für Grüne Ampel:
![Grundeinstellungen](http://doku.agentur-triebwerk-shop.de/deliverylights/status_gruen.png)
* Beschreibung: [Text, maximal 48 Zeichen]

Neben der Ampelfarbe wird die erklärende Beschreibung als Text mit angezeigt. Für die "Grüne Ampel" müssen keine Grenzwerte angegeben werden. Sie sind über die Grenzwerte der "Gelben Ampel" definiert: liegt die Artikelreichweite bzw. der Lagerbestand über dem bei "Gelbe Ampel" festgelegten Grenzwert, wird die "Grüne Ampel" angezeigt. 

Einstellung für „Nicht bestellbar“ :
![Grundeinstellungen](http://doku.agentur-triebwerk-shop.de/deliverylights/status_schwarz.png)
•	Beschreibung: [Text, maximal 48 Zeichen]
Diese erklärende Beschreibung wird angezeigt wenn ein Artikel nicht bestellbar ist, weil …
a) er als Abverkaufs-Artikel gekennzeichnet ist und keinen Lagerbestand hat.
b) das Erscheinungsdatum in der Zukunft liegt und der Artikel von dem Einführungsdatum als nicht bestellbar – über die Lieferampel –  gekennzeichnet ist.
c) er manuell – über die Artikeldetails / Lieferampel – als nicht bestellbar gekennzeichnet wurde.

# Artikel-Einstellungen
![Grundeinstellungen](http://doku.agentur-triebwerk-shop.de/deliverylights/artikeleinstellungen_2.png)
* Bestellbar: ja/nein
** Ja ist die Standardeinstellung. Ein deaktivieren macht den Artikel nicht bestellbar, gleich ob er Lagerbestand hat oder nicht. Die Einstellungen im Hinblick auf Anzeige und Veröffentlichung aber nicht beeinflusst. 
* Individuelle Einstellungen aktivieren: nein/ja
** Nein ist die Standardeinstellung. Ein Aktivieren macht die Einstellungen in den Artikeldetails editierbar und überschreibt die Plugin-Einstellungen für diesen Artikel.

# Versionshistorie
0.9 Erste öffentliche Pluginversion

# Unverträglichkeiten
Hier werden die bekannten Unverträglichkeiten gelistet.
Wenn Sie Fragen zur Plugin-Verträglichkeit von Lieferampel haben, kontaktieren Sie gerne vorab unseren Support: shopware@agentur-triebwerk.de
- keine Unverträglichkeiten bekannt
 


