---
title: 132_JSON
draft: false
tags:
  - JSON
---
# Allgemein

JSON steht für JavaScript Object Notation.
JSON ein leichtgewichtiges, textbasiertes Datenformat ist, das sowohl für Menschen als auch für Maschinen leicht lesbar und schreibbar ist. JSON ist plattformunabhängig und wird von vielen Programmiersprachen unterstützt, was die Integration und den Datenaustausch zwischen verschiedenen Systemen erleichtert. Außerdem ist JSON durch seine hierarchische Struktur ideal zur Darstellung komplexer Datenstrukturen geeignet.

Mehr über JSON auf [w3schools](https://www.w3schools.com/whatis/whatis_json.asp).

# Schreiben und Lesen von JSON Dateien



# Online VIewer / Editor

Es stehe auch diverse Online Editors zum lesen und bearbeiten von JSON Dateien, wie z.B: der [jsoneditoronline.org](https://jsoneditoronline.org).

# Beispiel

Beispiel einer Datenstruktur im ifcJSON Format für drei Wände (nur ein Ausschnitt zur Veranschaulichung):

```json
{
  "type": "ifcJSON",
  "version": "2.0",
  "data": {
    "walls": [
      {
        "type": "IfcWallStandardCase",
        "GlobalId": "1",
        "Name": "Structural Wall 1",
        "Location": {
          "type": "IfcLocalPlacement",
          "PlacementRelTo": "2",
          "RelativePlacement": {
            "type": "IfcAxis2Placement3D",
            "Location": {
              "type": "IfcCartesianPoint",
              "Coordinates": [
                10,
                20,
                0
              ]
            }
          }
        },
        "Width": 0.3,
        "Height": 3.0,
        "Material": "Concrete",
        "Properties": {
          "LoadBearing": true,
          "FireResistance": "REI120"
        }
      },
      {
        "type": "IfcWallStandardCase",
        "GlobalId": "2",
        "Name": "Structural Wall 2",
        "Location": {
          "type": "IfcLocalPlacement",
          "PlacementRelTo": "2",
          "RelativePlacement": {
            "type": "IfcAxis2Placement3D",
            "Location": {
              "type": "IfcCartesianPoint",
              "Coordinates": [
                15,
                25,
                0
              ]
            }
          }
        },
        "Width": 0.25,
        "Height": 3.0,
        "Material": "Brick",
        "Properties": {
          "LoadBearing": false,
          "FireResistance": "EI60"
        }
      },
      {
        "type": "IfcWallStandardCase",
        "GlobalId": "3",
        "Name": "Partition Wall 1",
        "Location": {
          "type": "IfcLocalPlacement",
          "PlacementRelTo": "2",
          "RelativePlacement": {
            "type": "IfcAxis2Placement3D",
            "Location": {
              "type": "IfcCartesianPoint",
              "Coordinates": [
                20,
                30,
                0
              ]
            }
          }
        },
        "Width": 0.15,
        "Height": 2.5,
        "Material": "Drywall",
        "Properties": {
          "LoadBearing": false,
          "FireResistance": "EI30"
        }
      }
    ]
  }
}
```

Wird aber die JSON Datei in einem Viewer geöffnet kann auch die Datenstruktur als Baum (Tree) gezeigt werden, wo die verschachtelte Datenstruktur wesentlich leichter zu lesen ist:

![[132_JSON_Tree_view.gif]]



# Weitere Unterlagen

https://de.wikipedia.org/wiki/GeoJSON
https://geojson.io
