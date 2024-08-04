
# Einführung in die Finite-Elemente-Methode (FEM)

Die Finite-Elemente-Methode (FEM) ist eine numerische Methode zur Lösung von partiellen Differentialgleichungen (PDEs) und Integralgleichungen. Sie wird häufig in der Ingenieurwissenschaft und Physik verwendet, um Probleme zu analysieren, die komplexe Geometrien, Lasten und Materialeigenschaften aufweisen. FEM zerlegt ein großes Problem in kleinere, einfachere Teile, die sogenannten "Finite Elemente". Diese Elemente werden dann einzeln analysiert und schließlich zu einer Gesamtlösung zusammengesetzt.

## Grundkonzept der FEM

1. **Diskretisierung**: Das zu untersuchende Gebiet wird in kleine, einfache Formen unterteilt, z.B. Dreiecke oder Vierecke in 2D oder Tetraeder und Hexaeder in 3D.
2. **Auswahl der Approximationsfunktionen**: Innerhalb jedes Elements wird das physikalische Feld (z.B. Verschiebung, Temperatur) durch eine Funktion angenähert, die oft polynomisch ist.
3. **Formulierung der Elementgleichungen**: Basierend auf den Grundgleichungen der Physik (z.B. Gleichgewichtsgleichungen) werden für jedes Element Gleichungen aufgestellt.
4. **Zusammensetzung des Gesamtsystems**: Die Elementgleichungen werden zu einem globalen Gleichungssystem zusammengefügt.
5. **Lösung des Gleichungssystems**: Das resultierende Gleichungssystem wird gelöst, um die gesuchten Feldgrößen (z.B. Verschiebungen, Spannungen) zu bestimmen.

Finite Elemente werden grundsätzlich unterteilt in:
- Eindimensionale Elemente (Fachwerk, Stab)
- Zweidimensionale Elemente (Dreiecke, Vierecke - Quadrilaterals)
- Dreidimensionale Elemente (Volumen - Tetrahedrons, Hexahedrons, Pentahedrons)

Exemplarisch werden unten die Typen von eindimensionalen Elementen aufgezeigt. 
In der Übung ([[212_UE]]) werden wir 3D Stabelemente verwenden.
# Eindimensionale Elemente

## Fachwerkstab (Axiale Belastung)

Ein 1D-Stabmodell beschreibt ein Element, das hauptsächlich axial belastet wird. Dies bedeutet, dass die Kräfte entlang der Länge des Stabes wirken, und das Element nur axiale Verformungen erfährt.
![[Pasted image 20240804124632.png]]

Die Steifigkeitsmatrix für ein einfaches 1D-Stabelement lautet:

![1D Truss Element Stiffness Matrix](https://latex.codecogs.com/png.image?\bg_white&space;K=\frac{EA}{L}\begin{bmatrix}1&-1\\-1&1\end{bmatrix})

Hier ist:
- \( E \) der Elastizitätsmodul des Materials,
- \( A \) die Querschnittsfläche,
- \( L \) die Länge des Stabelements.
## 2D-Stabelemente (Biegebelastung)

Ein 2D-Biegestabelement (auch Balken genannt) hat eine komplexere Steifigkeitsmatrix, die sowohl die axiale Steifigkeit als auch die Biegesteifigkeit berücksichtigt. Die Knotenverschiebungen umfassen Verschiebungen in x- und y-Richtung sowie Rotation.

![[Pasted image 20240804124643.png]]

Wie man an der unteren Matrize sieht, gibt es jetzt 6 x 6 Felder. 

![2D Steifigkeitsmatrix](https://latex.codecogs.com/png.image?\bg_white&space;K=\frac{E}{L}\begin{bmatrix}\frac{A}{L}&0&0&-\frac{A}{L}&0&0\\0&\frac{12I}{L^3}&\frac{6I}{L^2}&0&-\frac{12I}{L^3}&\frac{6I}{L^2}\\0&\frac{6I}{L^2}&\frac{4I}{L}&0&-\frac{6I}{L^2}&\frac{2I}{L}\\-\frac{A}{L}&0&0&\frac{A}{L}&0&0\\0&-\frac{12I}{L^3}&-\frac{6I}{L^2}&0&\frac{12I}{L^3}&-\frac{6I}{L^2}\\0&\frac{6I}{L^2}&\frac{2I}{L}&0&-\frac{6I}{L^2}&\frac{4I}{L}\end{bmatrix})

Hier ist:
- \( E \) der Elastizitätsmodul des Materials,
- \( A \) die Querschnittsfläche,
- \( L \) die Länge des Stabelements.
- \( I \) Trägheitsmoment des Querschnitts.

## 3D-Stabelemente

In einem 3D System, hat jeder Knoten 6 Freiheitsgrade (3x Verschiebung, 3x Verdrehung):

![[Pasted image 20240804124700.png]]

Wie man an der unteren Matrize sieht, gibt es jetzt 12 x 12 Felder für ein Stabelement. 

![3D Steifigkeitsmatrix](https://latex.codecogs.com/png.image?\bg_white&space;K=\begin{bmatrix}\frac{EA}{L}&0&0&0&0&0&-\frac{EA}{L}&0&0&0&0&0\\0&\frac{12EI_z}{L^3}&0&0&0&\frac{6EI_z}{L^2}&0&-\frac{12EI_z}{L^3}&0&0&0&\frac{6EI_z}{L^2}\\0&0&\frac{12EI_y}{L^3}&0&-\frac{6EI_y}{L^2}&0&0&0&-\frac{12EI_y}{L^3}&0&-\frac{6EI_y}{L^2}&0\\0&0&0&\frac{GJ}{L}&0&0&0&0&0&-\frac{GJ}{L}&0&0\\0&0&-\frac{6EI_y}{L^2}&0&\frac{4EI_y}{L}&0&0&0&\frac{6EI_y}{L^2}&0&\frac{2EI_y}{L}&0\\0&\frac{6EI_z}{L^2}&0&0&0&\frac{4EI_z}{L}&0&-\frac{6EI_z}{L^2}&0&0&0&\frac{2EI_z}{L}\\-\frac{EA}{L}&0&0&0&0&0&\frac{EA}{L}&0&0&0&0&0\\0&-\frac{12EI_z}{L^3}&0&0&0&-\frac{6EI_z}{L^2}&0&\frac{12EI_z}{L^3}&0&0&0&-\frac{6EI_z}{L^2}\\0&0&-\frac{12EI_y}{L^3}&0&\frac{6EI_y}{L^2}&0&0&0&\frac{12EI_y}{L^3}&0&\frac{6EI_y}{L^2}&0\\0&0&0&-\frac{GJ}{L}&0&0&0&0&0&\frac{GJ}{L}&0&0\\0&0&-\frac{6EI_y}{L^2}&0&\frac{2EI_y}{L}&0&0&0&\frac{6EI_y}{L^2}&0&\frac{4EI_y}{L}&0\\0&\frac{6EI_z}{L^2}&0&0&0&\frac{2EI_z}{L}&0&-\frac{6EI_z}{L^2}&0&0&0&\frac{4EI_z}{L}\end{bmatrix})


# Beispiel des Halbrahmens

Die Finite Elemente Berechnung des Übungsbeispiel von Grund auf, kann hier eingesehen werden: 

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/AIztok/FH_Jupyter/main?labpath=FH_SBB_FEM_Example.ipynb)

(öffnet das Jupyter Nootbook in Binder, womit der Quellcode über den Webbrowser eingesehen / geändert / berechnet werden kann)

# Weitere Unterlagen

Zu dem Buch von Prof. Horst Werkle ([[003_Literatur#200 Informationen Generieren]]) werden auch Präsentationen zur Verfügung gestellt, dort ist die FE Methode noch tiefer erläutert:
https://fembau.de/praesentationen-fuer-die-lehre/
