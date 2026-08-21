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


# Beispiel der Anwendung 

## Anwendung Speckle

## Einrichten 

Nach dem erstellen des Benutzerkontos und dem Einloggen auf:
https://app.speckle.systems/

### Neues Workspace einrichten

Zuerst muss ein neues Workspace eingerichtet werden, links oben:

![[312_Speckle_Workspace.png]]


Danach wird ein Workspace Name vergeben, z.B. DiTWP_W25:

![[312_Speckle_Workspace_name.png]]


Speckle ist für Zusammenarbeit von Teams ausgelegt, deswegen können Teammitglieder ins Workspace eingeladen werden, was ihnen eine Mitarbeit am Workspace ermöglicht. Man kann aber auch diesen Schritt überspringen (continue without inviting):



![[312_Speckle_Workspace_team.png]]

Danach wählt man den kostenlosen 'Free' Plan aus und der Workspace ist eingerichtet. 


### Neues Projekt
Neues Projekt erstellen:

![[312_Speckle_Workspace_Project.gif]]


### Upload IFC

Danach laden wir über Drag&Drop die IFC Datei der Bodenplatte ein:

![[312_Speckle_Upload_IFC.gif]]

![[312_UE#IFC Datei Bodenplatte]]

### Neues Modell
Neues Modell erstellen und der Link zum Modell kann über "Copy link" gespeichert werden:

![[300_Speckle_New_Model.gif]]


### IFC aus Speckle ins Grasshopper


![[112_GH_Speckle_URL.png]]




![[112_Speckle_Link.png]]


![[112_GH_Speckle_Model_URL.png]]

`Load` Komponente von Speckle auswählen:

![[112_GH_Speckle_Load.png]]

Mit Model Link verbinden und auf Load drucken - dies stellt die Verbindung mit dem Cloud von Speckle her.

![[112_GH_Speckle_Load_collection.png]]

> Achtung: immer wenn wir die Grasshopper Datei öffnen, müssen wir das Modell Loaden! Alternativ kann aber auch auf automatisch gewählt werden:

![[112_GH_Speckle_Autoload.png]]


Dann wird auch die Bodenplatte visualisiert:

![[112_GH_Modell_w_BoPla.png]]

Wir können das nutzen um:
- die Schnittstellen mit unseren Bauwerk zu sehen (mögliche Kollision)
- zum Nachmodellieren
- direkt die geladene Geometrie zu zerlegen und zu nutzen

Würden wir gerne das letzte tun, dann ist es wichtig zu wissen, dass die 3D Geometrie aus Speckle als ein `MESH` und kein `BREP` in Grasshopper eingelesen wird.

Durch selektieren des Speckle Objects und Auswahl der Geometrie (`Query Objects` und `Speckle Object`) kann die Geometrie ausgespielt werden.
Dieses Mesh kann dann mittels `Deconstruct Mesh` in Einzelteile zerlegt werden.

![[112_GH_Speckle_geometry.png]]

Es kann passieren dass es Doppelpunkte gibt, diese können einfach mittels `Create Set` rausgefilter werden und im unseren Fall verbleiben nur noch 8 Punkte.

![[112_GH_Speckle_geometry_points.png]]

![[112_GH_Speckle_Model_points.png]]

Und wenn nur ein BREP erforderlich ist, dann kann dieser auch aus dem Mesh direkt erstellt werden:
`Face Boundaries` Komponente mit der Geometry verbinden
`Boundary surfaces` mit Face Boundaries verbinden und es erstellt ein Brep

![[112_GH_Speckle_Mesh2Brep.png]]

![[112_GH_Speckle_BoPla-mehs.png]]

Wie man sieht ist das Mesh aus Dreieckelementen, deswegen sind auch die Punkte mehrmals in der Liste.


### Von Grasshopper aufs Speckle

Im Grasshopper wird unter dem Reiter *Speckle 2* und der Komponente *Send* 

![[Pasted image 20240530110805.png]]

![[Pasted image 20240530110611.png]]

### Von Speckle ins Excel

Nachdem wir den Excel connector als Add-Inn installiert haben (siehe hier [[321_Speckle]]), können die ans Speckle gesendete Daten (in dem Beispiel 4 Punkte).

![[300_Speckle_Excel_DL.gif]]

### Von Excel ins Speckle

Im Excel können diese Punkte zum Beispiel geändert werden (in unseren Fall wird die X-Koordinate vom 4. Punkt korrigiert) oder auch neue ergänzt werden:

![[300_Speckle_Excel_UL.gif]]

### Von Speckle ins Grasshopper

Auf der Web App von Speckle sind mittlerweile unter der Branch "halbrahmen/bodenplatte/punkte" die aus Excel hochgeladenen Daten bereit verfügbar.
Der Link von dem Stream wird kopiert:

![[Pasted image 20240530105125.png]]

Im Grasshopper können über die Komponente Receive die Daten / Punkte ins Modell geholt werden:

![[Pasted image 20240530112109.png]]

![[Pasted image 20240530112020.png]]

### Beispiel Halbrahmen

#### Punkte und Linien fürs statische Modell

Für den Halbrahmen haben wir bereits eine Export des Punkte / Linien Modell gemacht:
[[212_UE#Export der Daten des analytischen Modells (Punkte und Linien) auf Speckle]]


#### 3D Geometrie Teilen

Wir erstellen in Speckle ein neues Modell, dass wir z.B. benennen "312_ue" und kopieren uns den Link:

![[312_UE_3D-Modell_Speckle_1.png]]

Im Grasshopper File (Übung 1) wo wir die 3D Geometrie erstellt haben, exportieren wir die wie folgend:
- Komponente `Send`von Speckle
- Im Stream muss der kopierte Link aus Speckle stehen
- Message ist optional

![[312_UE_3D-Modell_Speckle_2.png]]

Somit wird das 3D Modell über Speckle geteilt:

<iframe title="Speckle" src="https://app.speckle.systems/projects/82c5e61288/models/4effd335ba#embed=%7B%22isEnabled%22%3Atrue%7D" width="600" height="400" frameborder="0"></iframe>





