DeliveryLightsDoku
==================

Shopware Plugin to define different state of delivery

# Vorwort
Das Plugin “DeliveryLights” ist für die Darstellung des Lieferbarkeitsstatus / der Möglichkeit der Bestellung eines Artikels zuständig. 

Es können Ausgabetexte für die Stati grün (Artikel ist bestellbar und viele Artikel sind vorhanden), gelb (Artikel ist bestellbar und der Bestand ist gering), rot (Artikel ist bestellbar und Bestand hat nur noch Restmengen) und schwarz (Artikel ist nicht bestellbar, weil: Bestellung deaktiviert, nicht vor Erscheinungsdatum zu verkaufen, keine Unterschreitung der Lagermenge 0 erlaubt).

Weiterhin können Grenzen für die Stati gelb und rot eingestellt werden, die erreicht werden müssen um diesen Status zu bekommen. 

In der Statusanzeige beim Artikel wird entsprechend der „schlechteste“ erreichte Status ausgegeben.
Schwarz > Rot > Gelb > Grün
Ist bei einem Artikel eine Lieferzeit eingegeben, so wird diese zusätzlich beim Lieferstatus angezeigt.

# Hauptfunktion
Erweiterung des standardmäßig vorhandenen Abbilden eines Lieferstatus, damit dieser durch den Shopbetreiber flexibler und klarer abgebildet werden kann

# Einstellungen
## Grundeinstellungen des Plugins
* Rote Grenze in Tagen = Artikel ist maximal x Tage verfügbar für Status rot
* Gelbe Grenze in Tagen = Artikel ist maximal x Tage verfügbar für Status gelb
* Rote Grenze in Stück = Artikel ist maximal x Stück verfügbar für Status rot
* Gelbe Grenze in Stück = Artikel ist maximal x Stück verfügbar für Status gelb
* Bezeichnung Status schwarz = Textausgabe, wenn Artikel nicht bestellbar
* Bezeichnung Status rot = Textausgabe, wenn Artikel Status rot erreicht
* Bezeichnung Status gelb = Textausgabe, wenn Artikel Status gelb erreicht
* Bezeichnung Status grün = Textausgabe, wenn Artikel Status rot erreicht

## Einstellungen beim Artikel
* Bestellbar = regelt ob ein Artikel bestellbar ist, wenn er aktiv ist
* Bestellung vor Einführung = regelt ob ein Artikel vor dem Einführungsdatum bestellt werden kann
* Eigenene Einstellungen für Artikel = legt fest, ob die globalen Einstellungen für Grenzen und Texte durch lokale überschrieben werden sollen
* Tagesentnahme = täglicher Verkauf des Artikels im Schnitt der letzten 365 Tage, Grundlage für Tagesgrenzen
* Rote Grenze in Tagen = Artikel ist maximal x Tage verfügbar für Status rot
* Gelbe Grenze in Tagen = Artikel ist maximal x Tage verfügbar für Status gelb
* Rote Grenze in Stück = Artikel ist maximal x Stück verfügbar für Status rot
* Gelbe Grenze in Stück = Artikel ist maximal x Stück verfügbar für Status gelb
* Text rote Grenze = Textausgabe, wenn Artikel Status rot erreicht
* Text gelbe Grenze = Textausgabe, wenn Artikel Status gelb erreicht
* Text grüne Grenze = Textausgabe, wenn Artikel Status grün erreicht

## Cron-Job
* berechnet den durchschnittlichen Verkauf der Artikel in den letzten 365 Tagen und aktualisiert die Tagesentnahme in den Einstellungen eines Artikels
* wird automatisch in den Systemgrundeinstellungen > Cronjobs angelegt und muss nur noch aktiviert werden
