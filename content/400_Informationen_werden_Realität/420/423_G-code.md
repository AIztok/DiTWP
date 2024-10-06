---
title: 423_G-code
draft: false
tags:
  - FAB
---
# Allgemein

[G-Code](https://en.wikipedia.org/wiki/G-code) ist eine der ältesten und am weitesten verbreiteten Programmiersprachen für die Steuerung von CNC-Maschinen (Computerized Numerical Control). Entwickelt in den 1950er Jahren, wurde G-Code zunächst im Rahmen der frühen Computerisierung von Maschinen in der Fertigungsindustrie eingeführt. Die Norm ISO 6983 standardisierte den G-Code und sorgte dafür, dass er weltweit verwendet werden kann. Er ist nach wie vor das Rückgrat vieler Fertigungs- und Produktionsprozesse.

Er gibt der Maschine detaillierte Anweisungen, wie sie sich bewegen soll, z.B. wie schnell, in welche Richtung, auf welcher Achse, sowie wie viel Material abgetragen oder extrudiert werden soll. Der Code besteht aus einer Reihe von Befehlen, die von der Maschine interpretiert werden, um präzise Bewegungen und Bearbeitungsschritte auszuführen.

Ein typischer G-Code-Befehl sieht so aus:

- **G1 X10 Y20 Z0 F150**: Dieser Befehl gibt der Maschine die Anweisung, sich linear zu einer bestimmten Position (X=10, Y=20, Z=0) mit einer Vorschubgeschwindigkeit von 150 zu bewegen.

# Wo wird G-Code angewendet?

G-Code findet in vielen Bereichen der modernen Fertigung und Produktion Anwendung:

- **CNC-Maschinen**: In der CNC-Bearbeitung wird G-Code verwendet, um Fräsmaschinen, Drehmaschinen, Bohrmaschinen und andere Werkzeugmaschinen zu steuern. Hier wird der Code genutzt, um Materialien wie Metall, Kunststoff und Holz präzise zu bearbeiten.
- **3D-Druck**: Im 3D-Druck wird G-Code verwendet, um den Druckkopf des Druckers zu steuern und die Position, Extrusion und Geschwindigkeit des Materials festzulegen. Fast alle FDM-3D-Drucker verwenden G-Code, um Schicht für Schicht ein Objekt zu erstellen.
- **Laser- und Wasserstrahlschneiden**: G-Code steuert Maschinen, die Material durch Laserstrahlen oder Hochdruck-Wasserstrahlen schneiden. Auch hier sind Präzision und wiederholbare Genauigkeit von größter Bedeutung.
- **Roboterarme und automatisierte Systeme**: In der Automatisierung kann G-Code verwendet werden, um Bewegungen von Roboterarmen oder anderen automatisierten Systemen zu steuern, die in der Fertigung oder Verpackung arbeiten.

# Beispiel eines einfachen G-Codes

Hier ist ein einfaches Beispiel eines G-Codes, der eine CNC-Maschine anweist, ein Quadrat zu fräsen:
```
G21        ; Setze Einheiten auf Millimeter
G90        ; Absolutes Positionierungssystem verwenden
G0 Z10     ; Hebe das Werkzeug auf Z = 10 mm (Sicherheitsabstand)
G0 X0 Y0   ; Gehe zum Startpunkt (X=0, Y=0)
G1 Z-5 F300; Senke das Werkzeug auf Z = -5 mm mit Vorschub 300 mm/min
G1 X50 F500; Bewege das Werkzeug auf X=50 mm (erste Linie des Quadrats)
G1 Y50     ; Bewege das Werkzeug auf Y=50 mm (zweite Linie des Quadrats)
G1 X0      ; Bewege das Werkzeug auf X=0 mm (dritte Linie des Quadrats)
G1 Y0      ; Bewege das Werkzeug auf Y=0 mm (fertig)
G0 Z10     ; Hebe das Werkzeug auf Z=10 mm
M30        ; Programm beenden

```

# Beispiel des G-Codes 

Durch das einlesen eines geometrischen Modells, z.B. aus .stp oder .stl (siehe [[136_STEP&STL]]) erstellt, beispielhaft eine Slicer Software, einen G-Code.

Der G-code für den 3D-Druck des einfachen Modells:
https://raw.githubusercontent.com/AIztok/DiTWP_Data/main/423/DiTWP_Habrahmen_slicer.gcode

![[423_3D-Druck_slicer.gif]]

# Weitere Unterlagen
## G-code 3D Druck

<iframe width="560" height="315" src="https://www.youtube.com/embed/2TByiMNduss?si=7IWzbMD-WHwlniGX" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## G-code CNC

<iframe width="560" height="315" src="https://www.youtube.com/embed/FKspL_2U-qk?si=ztYjlIaj2JeVVYGM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


