---
title: 013_Grasshopper
draft: false
tags:
  - "#3D"
  - "#FEM"
---
# Allgemein

Grasshopper 3D ist ein visuelles Programmiertool, das als Plugin für Rhino 3D, eine weit verbreitete 3D-Modellierungssoftware, dient. Es ermöglicht Nutzern die Erstellung komplexer geometrischer Formen und Architekturen durch parametrisches Design. Anstatt direkt mit Skriptsprachen zu programmieren, können Benutzer in Grasshopper 3D Algorithmen durch das Verbinden von sogenannten "Komponenten" in einer grafischen Benutzeroberfläche erstellen. Diese Komponenten repräsentieren verschiedene Funktionen und Prozesse, die die Geometrie definieren und manipulieren. Grasshopper 3D wird häufig in den Bereichen Architektur, Industriedesign und Ingenieurwesen eingesetzt, um Entwürfe effizient und parametrisch zu entwickeln und anzupassen.

# Installation

Grasshopper wird zusammen mit dem Rhino3D installiert.
Grasshopper öffnen unter Werkzeuge/Grasshopper:

![[Pasted image 20240511121920.png]]


# Komponenten

Der visuelle Code im Grasshopper wird erzeugt durch das verbinden von einzelnen Komponenten (input/output).

Einige Komponenten werden mit Rhino Installation installiert, andere können über Food4Rhino installiert werden, oder werden mit der Installation von anderen Programmen installiert (z.B. bei SOFiSTiK Rhino Interface). Es können auch vom Anwender eigene Komponenten erstellt werden. 

Komponenten von Grasshopper leicht finden:  
[Index aller GH Komponenten](https://grasshopperdocs.com/completeIndex.html)

# Basisbefehle

Unten eine Liste der Befehle die im Zuge der Übung am häufigsten verwendet werden.

## Komponente Ergänzen

Komponenten können über die Leisten ausgewählt werden:

![[Pasted image 20240531100508.png]]

Oder mit Doppelklick auf die Bearbeitungsfläche (Canvas) und über Suchen die Komponente finden.

Wenn bereits auf dem Canvas befindliche Komponenten gesucht werden, dann `STEU+ALT` halten und mit linker Maustaste die Komponente auswählen, dann wird die Position der Komponente auf der Liste (Reiter und wo zu finden) gezeigt.

## Scribble: Notizen machen 

Wie auch jeder Quellcode benötigt auch eine graphische Programmierung gute Beschreibung, damit sich jeder auskennt.

![[Pasted image 20240531100812.png]]

Danach Doppelklick und Text ergänzen, Schriftgröße wählen:

![[Pasted image 20240531100906.png]]

Der Scribble kann wie andere Komponenten am Canvas verschoben werden.

## Verbindungen / Wires

Zuerst prüfen ob unter "Display / Draw",  "fancy wires" eingeschaltet ist.

![[Pasted image 20240531101031.png]]

Wenn die Option Fancy Wires im Grasshopper Display-Menü aktiviert ist, zeigt die Drahtanzeige Informationen über die durch sie fließenden Daten an. Es gibt 4 verschiedene Drahtanzeigetypen:
- Einzelner orangefarbener Draht: Es werden keine Daten übertragen, der Parameter am linken Ende ist leer.
- Einzelner grauer Draht: Ein einzelnes Datenobjekt wird übertragen.
- Doppelter grauer Draht: Eine Liste von Datenobjekten wird übertragen.
- Doppelt gestrichelter grauer Draht: Mehrere Listen von Datenobjekten werden übertragen.

![[Pasted image 20230905104357.png]]

(Bildquelle: [Grasshopper3D/Wires](https://www.grasshopper3d.com/notes/index/show?noteKey=What_is_the_difference_between_the_dot_line_and_single_line_and_double_line_in_the_Grasshopper_file%3F))

<iframe width="560" height="315" src="https://www.youtube.com/embed/zwcKft1eo8s?si=6catbc9BFgQayVcK" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Wenn `Shift` gehalten wird, können zu einer Komponente mehrere Inputs gezogen werden.

## Display / Draw full names

Zeigt den vollen Text statt nur Kurzbezeichnung.

![[Pasted image 20240531101211.png]]

## Komponenten Beschriften

Die Komponenten können beliebig beschriftet werden und diese Beschriftung kann auch angezeigt werden statt: rechte Maustaste auf die Komponenten / Beschriften / Auswählen Draw name:

![[Pasted image 20240622232501.png]]

## Kopieren von Komponenten

Um eine oder mehrere ausgewählte Komponenten schnell zu kopieren ist neben `STEU+C` & `STEU+V` noch die folgenden Möglichkeit:
Komponenten auswählen und bei gedruckten `Shift+Alt` wegziehen.

## Panel erstellen

Ein Panel kann ganz schnell durch Doppelklick und Apostroph + Text + Enter erstellt werden:

![[Pasted image 20240529130724.png]]

## Gruppieren

Komponenten können zu Gruppen gruppiert werden, dies ermöglicht einen besseren Überblick und die Gruppe kann somit mit allen ihren Komponenten auf dem Canvas verschoben werden.

![[Pasted image 20240531095441.png]]

Ergebnis: 

![[Pasted image 20240531095505.png]]

Die Gruppe kann somit 

Mit der Auswahl der Gruppe und einer neuen Komponente (`Shift` halten), Rechtsklick / Add to group, kann die Gruppe erweitert werden:

![[Pasted image 20240531095628.png]]

## Cluster

Ein Cluster fasst mehrere Komponenten zu einer neuen Komponente zusammen, um die Übersichtlichkeit und Wiederverwendbarkeit zu erhöhen.

1. Ersetze deine Eingaben durch Cluster Input-Komponenten.
2. Verbinde deine Ausgaben mit Cluster Output-Komponenten.
3. Wähle die gesamte Definition aus. Rechtsklicke im freien Raum und wähle "Cluster".
4. Du kannst den Cluster umbenennen.
5. Du kannst den Cluster mit einem Passwort schützen, indem du mit der rechten Maustaste auf den Cluster klickst und ein Passwort festlegst.

## Bake

Mit Bake wird die Geometrie der jeweiligen Komponente in den Rhino überführt - "eingebacken". 
Danach kann z.B. das geometrische Modell im Rhino weiter bearbeitet und/oder gespeichert oder in anderen Formaten (z.B. .step) exportiert werden.

Wenn das im Grasshopper parametrisch erstellte Modell "eingebacken" ist, ist es im Rhino nicht mehr parametrisch. Wird die Geometrie im Grasshopper nachträglich verändert, muss das "eingebackene" Modell im Rhino gelöscht oder augeschaltet (Layer) werden.

![[Pasted image 20240531095959.png]]
# Datenstruktur

Wesentlich für einen parametrischen Entwurf ist die Datenstruktur. Gut und sinnvoll strukturierte Daten sind der Grundstein eines parametrischen Modells.

## Einzelelement



## Liste



## Datenbaum (Data tree)

Der Datenbau in Grasshopper ist eine Art  genesteter Daten (Nested List im englisch), einer [hierarchisch strukturierten Datenstruktur](https://de.wikipedia.org/wiki/Hierarchisch_strukturierte_Daten).

"Graft" and  "Flatten" changes the data structure inside a parameter. Sometimes it is necessary to modify the data structure because the default layout does not result in the desired operations. Imagine you divide 5 closed curves into 10 segments each. The result of this operation is a data structure of 5 lists with 10 items (points) each. If you were to Flatten this structure, you'd end up with a single list containing 50 items. If you were to Graft this structure, you'd end up with 50 lists of one item each.


Sehr gute Erläuterung des Konzepts:
https://bimcorner.com/a-beginners-guide-to-data-trees-in-grasshopper/

<iframe width="560" height="315" src="https://www.youtube.com/embed/uHXaEWQDV9w?si=xB6XGC1N32Fqs0Rv" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Detaillierte Erläuterung zu Datenbäumen im Grasshopper:

<iframe width="560" height="315" src="https://www.youtube.com/embed/SmNPxKTDcQI?si=Au2TvnNHG4MnQoFe" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

# Weitere Unterlagen

[Grasshopper Primer](https://modelab.gitbooks.io/grasshopper-primer/content/)

[Grasshopper Shortcuts](https://bimcorner.com/8-grasshopper-shortcuts-which-you-should-know/)