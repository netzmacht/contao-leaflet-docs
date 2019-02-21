
Verhalten von Markern individualisieren
=======================================

Leaflet für Contao nutzt für Marker als :ref:`datenformatGeoJson`. Dies bedeutet, dass Marker nicht über die Javascript
API von Leaflet vorgerendert übergeben werden, sondern vielmehr ein GeoJSON Feature übermittelt wird, dass dann als
Marker gerendert wird.

Dieser Aufbau hat den Vorteil, dass im GeoJSON Feature beliebige Daten mitgegeben werden können und damit die
Darstellung individualisiert werden kann.

Mit dem Einstellungsmöglichkeiten *pointToLayer expression* im Kartenlayer und *featureData* im Marker selber kann
direkt über das Backend eine Anpassung erfolgen.


Beispiel: Marker mit Link versehen
----------------------------------

Besteht die Anforderung einen Marker direkt zu verlinken, kann wie folgt vorgegangen werden:


1. Link hinterlegen
~~~~~~~~~~~~~~~~~~~

Zusätzliche Daten können als *JSON* im Eingabefeld *featureData* hinterlegt werden. Diese werden dann im GeoJSON-Feature
als Property *data* hinzugefügt.

.. code-block:: json

    {
        "href": "https://contao.rocks"
    }


Im GeoJSON-Feature existiert nun folgende Eigenschaft *feature.properties.data.href*.


2. *pointToLayer* Expression definieren
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Um einen Marker nun zu verlinken, kann im Marker-Layer der `pointToLayer`_ angepasst werden:

.. code-block:: javascript

    function (geoJsonPoint, latlng) {
        // Erstelle einen Marker anhand der Standard-Routine der Contao-Leaflet Erweiterung
        var marker = L.contao.pointToLayer(geoJsonPoint, latlng);

        // Falls in den GeoJSON Properties ein Link gesetzt ist, füge ein Click-Event hinzu
        if (geoJsonPoint.properties.data !== undefined && geoJsonPoint.properties.data.href !== undefined) {
            marker.on('click', function () {
                window.location.href = geoJsonPoint.properties.data.href;
            })
        }

        return marker;
    }

.. _pointToLayer: https://leafletjs.com/reference-1.4.0.html#geojson-pointtolayer
