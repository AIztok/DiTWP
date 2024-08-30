---
title: 015_Blender & BlenderBIM
draft: false
tags:
  - 3D
  - BIM
  - IFC
---
 
# Allgemein

**Blender** ist eine freie und offene 3D-Computergrafik-Software, die für Modellierung, Rigging, Animation, Simulation, Rendering, Compositing und Motion Tracking verwendet wird. Blender unterstützt auch Video-Editing und Game Creation. Die Software ist bekannt für ihre vielseitigen Werkzeuge und die Fähigkeit, eine Vielzahl von Aufgaben im Bereich der Computergrafik zu bewältigen. Blender wird sowohl von professionellen Künstlern als auch von Hobbyisten verwendet und ist durch seine Open-Source-Natur ständig weiterentwickelt und verbessert worden.

**BlenderBIM** ist ein Add-on für Blender, das die Erstellung und Verwaltung von Building Information Models (BIM) direkt in Blender ermöglicht im Sinne von *Native IFC* (siehe [[111_VO#Native IFC]].
Das Add-on bietet Werkzeuge für die Erstellung von architektonischen, strukturellen und MEP-Elementen (Mechanical, Electrical, and Plumbing) und unterstützt den gesamten Lebenszyklus eines Bauwerks von der Planung über die Konstruktion bis zur Instandhaltung. BlenderBIM zielt darauf ab, die Flexibilität und Leistungsfähigkeit von Blender in den Bereich der Bauindustrie zu bringen und gleichzeitig die Vorteile von Open-Source-Software zu nutzen.
# Installation 

Blender und das BlenderBIM sind freeware und open source.
Die Anleitung zur Installation ist hier zu finden:
https://docs.blenderbim.org/users/installation.html

Blende 4.1 installieren! (nicht Blender 4.2 LTS)

# Befehle
Im folgenden werden die wesentlichen Befehle aufgelistet.

## Einstellungen

Snap:
![[Pasted image 20240506225010.png]]


Taste "n": öffnen der Sidebar

![[Pasted image 20240614223959.png]]

![[Pasted image 20240614223914.png]]

## Modellierung

## Erstellen Achsen



## Erstellen Ebenen

![[Pasted image 20240702223653.png]]


![[Pasted image 20240702223751.png]]

## Verschieben

G - Verschieben (Graft)
G + X - Verschieben in X Richtung
G + Y - Verschieben in Y Richtung
G + Z - Verschieben in Z Richtung
G + B - Base point wählen

Der Cursor wird mit
	Shift + Rechte Maus 
platziert und dient dann als Referenzpunkt für das erstellen des nächsten Elements.

![[Pasted image 20240506215722.png]]




Moving: G + X 


## Object Mode / Edit Mode


Zwischen Object Mode und Edit mode kann mit der `Tab` Taste gewechselt werden.


## IFC Class zuweisen

![[Pasted image 20240702225759.png]]


## Aussparungen
### Aussparungen erstellen


Gewünschte Aussparung als einen Körper erstellen und in die richtige Lage platzieren.

1. Auswählen `Create Element`
2. Grundobjekt auswählen
3. Mit `Shift` gedrückt noch das Element das die Geometrie der Aussparung definiert auswählen
4. Unter `Tools / Apply void`


![[Pasted image 20240704224437.png]]

Ergebnis:

![[Pasted image 20240704224620.png]]

### Aussparung verschieben
Erstellte Aussparungen können verschoben werden, bzw. das Element, dass die Geometrie der Aussparung definiert angezeigt werden und dann ausgewählt und verschoben werden.

1. Element mit Aussparung auswählen
2. Geometrie des Elements das die Aussparung definiert anzeigen lassen

![[Pasted image 20240704224935.png]]

Danach kann das Element ausgewählt  und verschoben werden:

![[Pasted image 20240704224826.png]]


## Definition von Material und Zuweisung von Material

Die Basis Information von BIM Modellen ist das Material 
Die Definition und Zuweisung erfolgt in zwei Schritten:

1. Material erstellen
2. Material einzelnen Objekten zuweisen

Neues Material anlegen:
1. Auswählen `Material properties`
2. Neues Material erstellen
3. Neues Material benennen
4. Unter `Base color` kann die Farbe geändert werden

![[Pasted image 20240705223000.png]]

Um die Materialfarbe an den Objekten zu sehen, muss folgende Einstellung ausgewählt sein:
![[Pasted image 20240705223404.png]]

Um das Material zu erstellen auswählen:

![[Pasted image 20240705223448.png]]

Danach benennen, evtl. beschrieben, einer Kategorie zuweisen und danach `Save Attributes`
![[Pasted image 20240705223540.png]]

Entspr. IFC muss noch ein Style zugewiesen werden, hier einfach `Add Stye` und danach `Save current shading style`:

![[Pasted image 20240705223707.png]]

Danach kann das erstellte Material einem oder mehreren ausgewählten IFC Objekten zugewiesen werden:
1. Scene
2. Geometry and Materials
3. Object material - Edit
4. Auswahl Material und bestätigen

![[Pasted image 20240705224045.png]]


Siehe auch das folgende Video:

<iframe width="560" height="315" src="https://www.youtube.com/embed/2fhvLJA-6iE?si=LwiklokxP1QuC_BU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Property set template

Vorlagen für benutzerdefinierte Property sets erstellen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/nlSM593swZY?si=A_KVCbRUgBLkcCXk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

# Weitere Unterlagen

[Konvertieren 2D Zeichnungen ins BIM mit BlenderBIM](https://www.youtube.com/watch?v=L3Ihnkp42tE&ab_channel=BIMvoice).

[4D Bim in Blender BIM](https://www.youtube.com/watch?v=Q7-UBKLBK58&ab_channel=ConsultBIM%28SigmaDimensions%29)


