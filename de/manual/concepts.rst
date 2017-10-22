
Konzepte
========

Generierung von Javascript
--------------------------

Leaflet für Contao generiert aus der Datebankdefinition automatisch den entsprechenden Javascript-Code. Dieser wird, anders als bei anderen Erweiterungen nicht im Template zusammengesetzt. Das Verhalten der Generierung lässt sich demnach kaum über das Template steuern. Vielmehr beitet Leaflet für Contao einige Schnittstellen auf Programmierebene, wo die Ausgabe manipuliert werden kann.

Dynamisches Laden
-----------------

Aus den Kartendefinitionen wird Javascript generiert, welcher in das Markup der Seite geladen wird. Bei großen Datenmengen würde dies unnötig den Quelltext aufblähen und die Ladezeiten negativ beeinflussen. Daher können Daten auch dynamisch geladen werden. Dynamsich geladene Daten können z.b. anhand der Kartengrenzen beegrenzt werden.

Datenformat GeoJSON
-------------------

Leaflet für Contao nutzt als zentrales Datenformat GeoJSON. Selbst wenn im Backend Marker definiert werden, werden diese als GeoJSON Daten übermittelt und erst On The Fly in Marker generiert. Dies ermöglicht zum einem das dynamische Nachladen der Daten via AJAX als auch die individuelle Konvertierung der GeoJSON Features in die Kartenfeatures.

Kartengrenzen
-------------

Ergänzend zu den Standadfunktionen von Leaflet bietet die Erweiterung die Möglichkeit die Grenzen einer Karte unter verschiedenen Bedingungen zu verändern:

 - statisches Festlegen der Grenzen anhand der initialen Konfiguration
 - Laden von Daten innerhalb der Kartengrenzen
 - Daten erweitern die Kartengrenzen initial
 - Daten erweitern die Kartengrenzen, auch wenn diese dynamisch geladen werden
 
Das grundlegende Verhalten ist bei der Karte zu konfigurieren. Bei den einzelnen Layern kann dann das individuelle Verhalten der Layer-Daten definiert werden.

.. hint: Die Konfiguration ist sehr flexibel. Eine falsche Konfiguration kann jedoch auch dazu führen, dass permanent Daten-    Request an den Server gesandt werden.

Caching
-------

Leaflet für Contao generiert aus den im Contao Backend vorgenommenen Konfigurationen eine Definition mit der LeafletPHP_ Bibliothek. Dies ist im Grunde eine Abstraktion dessen, wie man die Karte mit der originalen Javascript-Bibliothek definieren würde. Diese Definition wird letztendlich zu Javascript und GeoJSON Daten konvergiert.

Dieser Aufbau ermöglicht eine flexible Manipulation sämtlicher Definitionen, ist aber auch recht rechenintensiv. Daher unterstützt Leaflet für Contao ein Caching. Dies wird auf der Ebene der Karten definiert. Da manche Layer nicht gecacht werden sollen, z.B. da sie auf die Grenzen der Karte reagieren sollen, kann man Layer vom Caching ausschließen.

.. _LeafletPHP: https://github.com/netzmacht/php-leaflet
