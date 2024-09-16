---
title: 321_Speckle
draft: false
tags:
  - 3D
  - BIM
  - IFC
---
# Allgemein
Speckle ist eine App und Plattform zum Austausch von Modelldaten zwischen gängigen Programmen der AEC (Architecture, Engineering, Construction) Industrie. 

Speckle besteht aus:
- Speckle Manager: App über die am Rechner der Benutzeraccount und die installierten Connectors verwaltet werden
- Connectors: das sind Add-Ons für diverse Programme (Rhino, Grasshopper, Blender, Revit, Archicad usw.) über die Speckle in die Programme integriert wird und ein Datenaustausch ermöglich wird
- Speckle Web-App: der Online Dienst, wo die Daten die ausgetauscht worden sind sichtbar sind, durch die Web-App kann eingesehen werden wer am Projekt mitarbeitet und wann welche Daten hochgeladen worden sind, es können Kommentare hinterlassen werden und Modell über den Browser eingesehen werden.
- API und SDK: Application programming interfaces und Software development kits zum erstellen von eigenen Programmen die die Kapazitäten von Speckle nutzen

https://speckle.systems/

<iframe width="560" height="315" src="https://www.youtube.com/embed/B9humiSpHzM?si=pN70b7tw9s85Nic7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

# Installieren

Registrieren und Download des Speckle Managers hier: https://speckle.systems/
Die Registrierung und Nutzung der App ist Kostenfrei.
# Connectors

Nachdem starten des Speckle Managers und einloggen (Accounts) können unter dem Reiter Connectors die gewünschten Connectors installiert werden.

Für die Übung sind die Connectors für Grasshopper, Blender und Rhino erforderlich - beim installieren diese Apps nicht geöffnet haben. 

Zur der Installation des Excel Connectors siehe unten.

![[Pasted image 20240531104435.png]]

## Grasshopper Connector

Das der Grasshopper Connector installiert wurde, ist in Grasshopper, Reiter Speckle zu sehen, wo dann die Speckle Komponenten zur Verfügung stehen:

![[Pasted image 20240531104737.png]]

Mehr zu den Speckle Komponenten im Grasshopper:
[Speckle / Grasshopper Guide](https://speckle.guide/user/grasshopper.html)


## Excel Connector
Der Excel connector ist ein Community Add-on, also nicht offiziell von Speckle entwickelt, sondern mit der Nutzung des Speckle [APIs](https://de.wikipedia.org/wiki/Programmierschnittstelle).

Der Connector kann über Excel Add-ins installiert werden:

![[Pasted image 20240531105936.png]]

Hier die Anweisungen zum installieren des Add-ons (via Excel):
[Speckle / Excel](https://speckle.systems/tag/excel/)

## Blender Connector

Hier die Anweisung zum installieren (über Speckle Manager) und aktivieren des Add-Ons im Blender:
[Speckle / Blender](https://speckle.systems/tutorials/getting-started-with-speckle-for-blender/)

# Projects / Modells / Branches 

https://speckle.guide/user/concepts.html#what-are-branches




