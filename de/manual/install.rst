Installation
============

Über den Contao Manager
-----------------------

Leaflet für Contao lässt sich komfortabel über den `Contao Manager`_ installieren:

 1. netzmacht/contao-leaflet-maps suchen
 2. Gewünschte Version eingeben (~3.0@alpha) auswählen
 3. Änderungen anwenden
 4. Install-Tool aufrufen und die Datenbank aktualisieren
 5. Fertig!

Manuell mit Composer
--------------------

Desweiteren kann die Erweiterung manuell über Composer installiert werden.

 1. php composer require netzmacht/contao-leaflet-maps:~3.0@alpha 
 3.  Install-Tool aufrufen und die Datenbank aktualisieren
 4. Fertig!
 
 .. hint: Da die Abhängigkeit netzmacht/contao-toolkit noch nicht in einem stabilen Release vorliegt, muss ggf. die minimal  
    Abhängigkeit im Composer auf *Beta* gesetzt werden oder netzmacht/contao-toolkit explizit als Version ~3.0@beta vor Leaflet 
    installiert werden

.. _Contao Manager: https://docs.contao.org/books/manager/de/installation-manager.html
