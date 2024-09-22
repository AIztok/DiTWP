---
title: 136_STEP&STL
draft: false
tags:
  - "#CAM"
---
 

# Allgemein

Die CAD-Datenformate STEP und STL spielen eine wichtige Rolle im Bereich der 3D-Modellierung, da sie es ermöglichen, Modelle zwischen verschiedenen Softwareprogrammen und Anwendungen auszutauschen. Jedes Format hat spezifische Anwendungsbereiche und eignet sich für unterschiedliche Anforderungen.

- **STEP**: Wird vor allem in komplexen industriellen Anwendungen genutzt, wo exakte geometrische Modelle, Produktdaten und Konstruktionsdetails übertragen werden müssen. Es ist vielseitig und standardisiert für die Zusammenarbeit zwischen verschiedenen CAD-Systemen.
- **STL**: Eignet sich hervorragend für den 3D-Druck und Prototyping, da es schnell und einfach die Form eines Objekts speichert. Es wird primär dort eingesetzt, wo es auf die geometrische Form, nicht aber auf präzise Details oder Zusatzinformationen ankommt.

Beide Formate ergänzen sich also je nach Anwendungsfall: STEP für detaillierte Konstruktionsdaten und STL für schnelle, geometriebasierte Anwendungen wie 3D-Druck.

# STEP (Standard for the Exchange of Product Model Data)

**Beschreibung:**

- STEP, auch bekannt als [ISO 10303](https://en.wikipedia.org/wiki/ISO_10303) und [ISO 10303-21](https://en.wikipedia.org/wiki/ISO_10303-21), standardisiertes Format, das entwickelt wurde, um den Datenaustausch zwischen verschiedenen CAD-Systemen zu ermöglichen.
- Es ist in der Lage, komplexe 3D-Geometrien sowie produktbezogene Daten zu speichern, darunter:
    - Geometrie (Volumenmodelle, Flächenmodelle)
    - Toleranzen
    - Materialien
    - Strukturinformationen (Baugruppen, Unterbaugruppen)
    - Fertigungsinformationen (Produktlebenszyklusdaten, Produktionsprozesse)

**Anwendung:**

- **Industrie und Maschinenbau**: STEP wird häufig in der Automobil-, Luft- und Raumfahrt- sowie Maschinenbauindustrie verwendet, da es eine vollständige Beschreibung von Produkten und Bauteilen ermöglicht.
- **Kompatibilität**: Es ist ideal, um Modelle zwischen verschiedenen CAD-Systemen zu übertragen, da es keine proprietären Softwareeinschränkungen hat. Dies ermöglicht eine reibungslose Zusammenarbeit zwischen Ingenieuren, die verschiedene CAD-Programme verwenden.
- **Fertigungsprozesse**: Da STEP mehr als nur geometrische Daten speichert, wird es auch in Prozessen wie der computergestützten Fertigung (CAM) und der Produktentwicklung eingesetzt, wo es wichtig ist, Toleranzen und Materialeigenschaften zu berücksichtigen.

**Vorteile:**

- Verlustfreier Datenaustausch von präzisen Geometrien.
- Unterstützt komplexe Baugruppen.
- Standardisiert und weit verbreitet in der Industrie.

# STL (Stereolithography)

**Beschreibung:**

- Das [STL-Format](https://de.wikipedia.org/wiki/STL-Schnittstelle) wurde ursprünglich von 3D Systems für die Stereolithographie entwickelt, eine der ersten 3D-Drucktechnologien - additive Fertigungstechnik.
- Es speichert nur die Oberflächengeometrie eines Objekts, indem es das Modell als ein Netz von Dreiecken (Dreiecksvermaschung) beschreibt. Jeder Punkt eines Dreiecks wird durch Koordinaten im Raum definiert.
- STL enthält keine Informationen über Farben, Materialien oder Oberflächeneigenschaften. Es ist ein rein geometrisches Format, das die Form eines Objekts beschreibt.

**Anwendung:**

- **3D-Druck**: STL ist das Standardformat für den 3D-Druck, da es die geometrische Oberfläche eines Modells präzise und einfach beschreibt. Drucker verwenden diese Informationen, um Schichten zu erzeugen und das Modell aufzubauen.
- **Prototyping**: Ingenieure und Designer nutzen STL häufig, um schnelle Prototypen zu erstellen, da es sich einfach und effizient verarbeiten lässt.
- **Simulation und Visualisierung**: STL kann auch in der Simulation von Oberflächen und in der Visualisierung von einfachen Modellen verwendet werden, wo es weniger auf detaillierte Konstruktionsdaten ankommt.

**Vorteile:**

- Einfach und weit verbreitet, besonders im 3D-Druck.
- Kompatibel mit den meisten 3D-Druckern und Softwarepaketen.
- Schnell zu verarbeiten, da es keine unnötigen Daten speichert.

Beispiel einlesen der STL Datei in eine [Slicer Software](https://de.wikipedia.org/wiki/Slicer-Software) zum 3D Druck:
![[136_STL_Slicer.png]]

# Stp oder stl Datei in Rhino/Grasshopper erstellen

## Weg über Rhino Elemente

Um ein Modell in Step (.stp) oder .stl Format zu exportieren wird zuerst die gewünschte Geometrie wird "gebacken" - Bake - somit wird die Geometrie in eine Rhino Elemente übertragen.

![[136_Rhino_bake.png]]

Im Rhino erscheinen somit zusätzlich noch die gebackenen Elemente.
Danach sind die zu exportierenden Elemente auszuwählen:

![[136_Rhino_elements.png]]


Und über `File`/ `Export selected` können die Elemente im gewünschten Format exportiert werden:

![[136_Rhino_export_0.png]]

Format auswählen:
![[136_Rhino_export.png]]

## Direkt in Grasshopper

Mithilfe der Komponenten von TT-Toolbox (siehe [[012_Rhino_3D#Food4Rhino]]) gibt es die Komponente `Export STL File` mit der wir unsere Geometrie, die wir vorher über:
- `Mesh Brep` vernetzen
- `Mesh join` das Netz zu einem Netz vereinen
in ein STL speichern können

![[136_STL_TTToolbox.png]]