
Datei-Layer
===========

Formate
-------

Leaflet für Contao unterstützt neben der Definition der Karten innerhalb von Contao auch externe Daten einzubetten. Dafür werden folgende Datenformate unterstützt:

 - GPS Exchange Format (GPX)
 - Keyhole Markup Language (KML)
 - Wellknown Text (WKT)
 - GeoJSON
 - TopoJSON
 
Die Daten werden mit Hilfe des Plugins `Omnivore`_ zu GeoJSON Features konvertiert. Unterstützt werden dabei alle Funktionen der Formate, welche die Bibliothek mit sich bringt. 
 
Datei-Layer im Backend definieren
---------------------------------

Exterene Dateien werden als Layer im Backend definiert.


 
.. _Omnivore: https://github.com/mapbox/leaflet-omnivore
