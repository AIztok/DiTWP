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

Der Datenbau in Grasshopper ist eine Art  genesteter Daten (Nested List im englisch), einer [hierarchisch strukturierten Datenstruktur](https://de.wikipedia.org/wiki/Hierarchisch_strukturierte_Daten). Nicht zu verwechseln mit 

Datenbäume sind eine Methode, um komplexe Datenstrukturen zu organisieren und zu verwalten. Sie erweitern das Konzept von Listen und ermöglichen eine detailliertere und hierarchische Datenverwaltung. Hier ist eine Übersicht, warum Datenbäume nützlich sind und wie sie sich im Vergleich zu normalen Listen darstellen:

### Normale Listen

- **Struktur**: Linear, eindimensional.
- **Datenorganisation**: Einfache Sequenzen von Daten.
- **Einsatzgebiet**: Ideal für einfache Aufgaben, bei denen die Reihenfolge der Daten wichtig ist, aber die Beziehungen zwischen verschiedenen Datensätzen minimal sind.

### Datenbäume

- **Struktur**: Hierarchisch, mehrdimensional.
- **Datenorganisation**: Verschachtelte Listen (Äste und Unteräste), die komplexere Datenbeziehungen ermöglichen.
- **Einsatzgebiet**: Wichtig für die Verwaltung mehrerer zusammenhängender Datensätze, insbesondere in komplexen parametrischen Entwürfen, bei denen Komponenten gruppiert und zusammen verarbeitet werden müssen.

### Vorteile von Datenbäumen

1. **Hierarchische Organisation**: Datenbäume können Daten hierarchisch speichern, wodurch Untergruppen von Daten effizienter verwaltet und abgerufen werden können.
2. **Parallele Verarbeitung**: Sie können Operationen gleichzeitig auf verschiedenen Ästen des Baums anwenden, was Arbeitsabläufe rationalisiert.
3. **Flexibilität**: Bäume ermöglichen die Arbeit mit komplexen Datenstrukturen, die mit flachen Listen umständlich wären.
4. **Gruppierung und Verschachtelung**: Sie ermöglichen eine logische Gruppierung von Daten, was bei komplexen Modellierungsaufgaben, bei denen Elemente miteinander verbunden sind, entscheidend ist.

Auch eine sehr gute Erläuterung des Konzepts:
https://bimcorner.com/a-beginners-guide-to-data-trees-in-grasshopper/

<iframe width="560" height="315" src="https://www.youtube.com/embed/uHXaEWQDV9w?si=xB6XGC1N32Fqs0Rv" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Detaillierte Erläuterung zu Datenbäumen im Grasshopper:

<iframe width="560" height="315" src="https://www.youtube.com/embed/SmNPxKTDcQI?si=Au2TvnNHG4MnQoFe" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>




# Grasshopper und LLMs

Der Grasshopper Plug-In **GHPT** ermöglicht anhand von Prompts in [natürlicher Sprache](https://de.wikipedia.org/wiki/Nat%C3%BCrliche_Sprache) Komponenten Blocks zu erstellen.
Der Plug-In kann über [Food4Rhino/GHPT](https://www.food4rhino.com/en/app/ghpt?_gl=1*apv80h*_up*MQ..*_ga*MTUxNTc0NzUwMS4xNzE5NjMxMDE3*_ga_FE9QK9PL3L*MTcxOTYzMTAxNi4xLjEuMTcxOTYzMTkwOS4wLjAuMA) installier werden.

Mehr Anweisung zum [GitHub/GHPT](https://github.com/enmerk4r/GHPT).

Für die Nutzung ist ein API Key von OpenAI erforderlich, siehe [[411_VO]] .

# Weitere Unterlagen

[Grasshopper Primer](https://modelab.gitbooks.io/grasshopper-primer/content/)

[Grasshopper Shortcuts](https://bimcorner.com/8-grasshopper-shortcuts-which-you-should-know/)