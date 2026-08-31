---
title: 012_Rhino_3D
draft: false
tags:
  - 3D
---
# Allgemein

**Rhino** (offiziell Rhinoceros) ist eine 3D-Computergrafik- und CAD-Software, die hauptsächlich für die Erstellung, Bearbeitung, Analyse und Übersetzung von NURBS-Kurven und -Flächen (Non-Uniform Rational B-Splines) verwendet wird. Rhino ist besonders beliebt in Bereichen wie Architektur, Industriedesign, Produktdesign, Schmuckdesign, Schiffbau und Maschinenbau.

Die Hauptmerkmale von Rhino umfassen:

- **Präzision**: Ermöglicht die Erstellung komplexer und genauer 3D-Modelle.
- **Kompatibilität**: Unterstützt eine breite Palette von Dateiformaten, was die Zusammenarbeit mit anderen CAD-Programmen erleichtert.
- **Erweiterbarkeit**: Rhino kann durch zahlreiche Plugins erweitert werden, die zusätzliche Funktionen für spezifische Anwendungen bieten.
- **Benutzerfreundlichkeit**: Eine intuitive Benutzeroberfläche und umfangreiche Dokumentation machen es zugänglich für sowohl Anfänger als auch erfahrene Anwender.

Rhino wird oft in Kombination mit anderen Softwarelösungen verwendet, um ein breites Spektrum an Design- und Fertigungsanforderungen abzudecken.
# Installation

## Rhino 8
Wir werden Rhino 8 verwenden.

## Lizenz
Die FH Campus Wien bietet den Studierenden Lizenzen für Rhino an. Siehe hierzu eine gesonderte Email an die Studierenden mit weiteren Anweisungen.

# Food4Rhino
## Allgemein
Food4Rhino ist ein Portal wo Entwickler ihre Add-On (integrierte Zusatzprogramme) anderen Anwendern zur Verfügung stellen können.

## Anmelden
Es ist notwendig einen Account auf Food4Rhino zu erstellen. Die Anmeldung ist kostenlos. Über Food4Rhino können kostenlose und bezahlbare AddOn's heruntergeladen / gekauft werden.

# Weitere Unterlagen

## Add-ons die wir verwenden

### DiTWP-Tools

Das DiTWP-Tools kann über den PackageManager von Rhino installiert werden, in der Kommandoleiste `PackageManager` eingeben und Enter:

![[013_Rhino_DiTWP_Tools_1.png]]

Nach DiTWP_Tools suchen, auswählen und installieren:

![[013_Rhino_DiTWP_Tools_2.png]]

Package Manager und Rhino3D müssen danach geschlossen werden un Rhino3D neu gestartet.

Danach unter Tools / Grasshopper starten:

![[013_Rhino_DiTWP_Tools_3.png]]

In Grasshopper sollte ein neuer Reiter zur Verfügung stehen:
![[013_Rhino_DiTWP_Tools_4.png]]


Beim ersten Platzieren von den Komponenten kann es etwas länger dauern, da die erforderlichen Programmierpakete heruntergeladen und installiert werden:

![[013_Rhino_DiTWP_Tools_5.png]]

## Interessante Add-Ons

### TT-Toolbox
https://www.food4rhino.com/en/app/tt-toolbox
Die Toolbox kann direkt vom Browser installiert werden.

Bei der Übung [[212_UE]] wird das TT-Toolbox für den Export und Import von Excel Dateien verwendet.

### Speckle
Wir werden die Komponenten von Speckle verwenden, diese werden über die Installation von Connectors installier, siehe [[321_Speckle]].

### Excel+

Als alternative zu TT-Toolbox fürs speichern von Daten in Excel format kann auch Excel+ verwendet werden:
https://www.food4rhino.com/en/app/excel

### Lunchbox
https://www.food4rhino.com/en/app/lunchbox


# Basisbefehle

## Default Template

Da wir in Metern an großen Objekten arbeiten werden, ist es sinnvoll die "Default Template" auf "Large Objects - Meters" einzustellen:

File / New (Datei / Neue Datei):

Auswählen und ankreuzen "Use this file when Rhino starts", danach "Öffnen"

![[012_Rhino_DefaultTemplate.png]]
