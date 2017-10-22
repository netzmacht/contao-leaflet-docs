
Konzepte
========

Generierung von Javascript
--------------------------

Leaflet für Contao generiert aus der Datebankdefinition automatisch den entsprechenden Javascript-Code. Dieser wird, anders als bei anderen Erweiterungen nicht im Template zusammengesetzt. Das Verhalten der Generierung lässt sich demnach kaum über das Template steuern. Vielmehr beitet Leaflet für Contao einige Schnittstellen auf Programmierebene, wo die Ausgabe manipuliert werden kann.

Datenformat GeoJSON
-------------------

Leaflet für Contao nutzt als zentrales Datenformat GeoJSON. Selbst wenn im Backend Marker definiert werden, werden diese als GeoJSON Daten übermittelt und erst On The Fly in Marker generiert. Dies ermöglicht zum einem das dynamische Nachladen der Daten via AJAX als auch die individuelle Konvertierung der GeoJSON Features in die Kartenfeatures.

Bounds Mode
-----------




Dynamisches Laden
-----------------
