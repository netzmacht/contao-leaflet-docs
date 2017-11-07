
Erste Schritte
==============

Nach der erfolgreichen Installation von Leaflet für Contao erscheint im Contao Backend in der linken Navigationssidebar ein zusätzlicher Bereich *Leaflet*. 

Um die erste Karte zu konfigurieren sind folgende Schritte zu empfehlen:

1. Kachel-Layer definieren
--------------------------

Bevor die erste Karte definiert wird, ist es empfehlenswert die Laryer zu definieren, da Layer separat von den Karten angelegt und in der Karte nur referenziert werden.

Die Kachel-Layer generieren die Karte selbst. Wie Leaflet ist der Anwender hier vollkommen frei eigene Kartenanbieter zu integrieren. Um nicht für jeden Anbieter eine manuelle Konfiguration vorzunehmen, unterstützt die Erweiterung mit dem Layertyp **Vorkonfigurierte Karte** alle Karten die von dem Plugin `Leaflet Providers`_ angeboten werden.

Als Karten-Layer legen wir daher nun ein Layer vom Typ **Vorkonfigurierte Karte** aus und wählen als **Kartenanbieter** *OpenStreetMap* aus.

2. Marker-Layer definieren
--------------------------

Alle Daten werden bei Leaflet für Contao unter Layern verwaltet.
