
# Einführung in die Finite-Elemente-Methode (FEM)

Die Finite-Elemente-Methode (FEM) ist eine numerische Methode zur Lösung von partiellen Differentialgleichungen (PDEs) und Integralgleichungen. Sie wird häufig in der Ingenieurwissenschaft und Physik verwendet, um Probleme zu analysieren, die komplexe Geometrien, Lasten und Materialeigenschaften aufweisen. FEM zerlegt ein großes Problem in kleinere, einfachere Teile, die sogenannten "Finite Elemente". Diese Elemente werden dann einzeln analysiert und schließlich zu einer Gesamtlösung zusammengesetzt.

## Grundkonzept der FEM

1. **Diskretisierung**: Das zu untersuchende Gebiet wird in kleine, einfache Formen unterteilt, z.B. Dreiecke oder Vierecke in 2D oder Tetraeder und Hexaeder in 3D.
2. **Auswahl der Approximationsfunktionen**: Innerhalb jedes Elements wird das physikalische Feld (z.B. Verschiebung, Temperatur) durch eine Funktion angenähert, die oft polynomisch ist.
3. **Formulierung der Elementgleichungen**: Basierend auf den Grundgleichungen der Physik (z.B. Gleichgewichtsgleichungen) werden für jedes Element Gleichungen aufgestellt.
4. **Zusammensetzung des Gesamtsystems**: Die Elementgleichungen werden zu einem globalen Gleichungssystem zusammengefügt.
5. **Lösung des Gleichungssystems**: Das resultierende Gleichungssystem wird gelöst, um die gesuchten Feldgrößen (z.B. Verschiebungen, Spannungen) zu bestimmen.

# Stabelemente

## 1D-Stabmodelle (Axiale Belastung)

Ein 1D-Stabmodell beschreibt ein Element, das hauptsächlich axial belastet wird. Dies bedeutet, dass die Kräfte entlang der Länge des Stabes wirken, und das Element nur axiale Verformungen erfährt.

Die Steifigkeitsmatrix für ein einfaches 1D-Stabelement lautet:

![1D Steifigkeitsmatrix](http://www.sciweavers.org/tex2img.php?eq=K%20%3D%20%5Cfrac%7BEA%7D%7BL%7D%20%5Cbegin%7Bbmatrix%7D%201%20%26%20-1%20%5C%5C%20-1%20%26%201%20%5Cend%7Bbmatrix%7D&bc=White&fc=Black&im=jpg&fs=18&ff=arev&edit=)

Hier ist:
- \( E \) der Elastizitätsmodul des Materials,
- \( A \) die Querschnittsfläche,
- \( L \) die Länge des Stabelements.
## 2D-Stabelemente (Biegebelastung)

Ein 2D-Biegestabelement (auch Balken genannt) hat eine komplexere Steifigkeitsmatrix, die sowohl die axiale Steifigkeit als auch die Biegesteifigkeit berücksichtigt. Die Knotenverschiebungen umfassen Verschiebungen in x- und y-Richtung sowie Rotation.

Wie man an der unteren Matrize sieht, gibt es jetzt 6 x 6 Felder. 

![2D Steifigkeitsmatrix](https://latex.codecogs.com/png.image?\bg_white&space;K=\frac{E}{L}\begin{bmatrix}\frac{A}{L}&0&0&-\frac{A}{L}&0&0\\0&\frac{12I}{L^3}&\frac{6I}{L^2}&0&-\frac{12I}{L^3}&\frac{6I}{L^2}\\0&\frac{6I}{L^2}&\frac{4I}{L}&0&-\frac{6I}{L^2}&\frac{2I}{L}\\-\frac{A}{L}&0&0&\frac{A}{L}&0&0\\0&-\frac{12I}{L^3}&-\frac{6I}{L^2}&0&\frac{12I}{L^3}&-\frac{6I}{L^2}\\0&\frac{6I}{L^2}&\frac{2I}{L}&0&-\frac{6I}{L^2}&\frac{4I}{L}\end{bmatrix})

## 3D-Stabelemente

Wie man an der unteren Matrize sieht, gibt es jetzt 12 x 12 Felder. 

![3D Steifigkeitsmatrix](https://latex.codecogs.com/png.image?\bg_white&space;K=\begin{bmatrix}\frac{EA}{L}&0&0&0&0&0&-\frac{EA}{L}&0&0&0&0&0\\0&\frac{12EI_z}{L^3}&0&0&0&\frac{6EI_z}{L^2}&0&-\frac{12EI_z}{L^3}&0&0&0&\frac{6EI_z}{L^2}\\0&0&\frac{12EI_y}{L^3}&0&-\frac{6EI_y}{L^2}&0&0&0&-\frac{12EI_y}{L^3}&0&-\frac{6EI_y}{L^2}&0\\0&0&0&\frac{GJ}{L}&0&0&0&0&0&-\frac{GJ}{L}&0&0\\0&0&-\frac{6EI_y}{L^2}&0&\frac{4EI_y}{L}&0&0&0&\frac{6EI_y}{L^2}&0&\frac{2EI_y}{L}&0\\0&\frac{6EI_z}{L^2}&0&0&0&\frac{4EI_z}{L}&0&-\frac{6EI_z}{L^2}&0&0&0&\frac{2EI_z}{L}\\-\frac{EA}{L}&0&0&0&0&0&\frac{EA}{L}&0&0&0&0&0\\0&-\frac{12EI_z}{L^3}&0&0&0&-\frac{6EI_z}{L^2}&0&\frac{12EI_z}{L^3}&0&0&0&-\frac{6EI_z}{L^2}\\0&0&-\frac{12EI_y}{L^3}&0&\frac{6EI_y}{L^2}&0&0&0&\frac{12EI_y}{L^3}&0&\frac{6EI_y}{L^2}&0\\0&0&0&-\frac{GJ}{L}&0&0&0&0&0&\frac{GJ}{L}&0&0\\0&0&-\frac{6EI_y}{L^2}&0&\frac{2EI_y}{L}&0&0&0&\frac{6EI_y}{L^2}&0&\frac{4EI_y}{L}&0\\0&\frac{6EI_z}{L^2}&0&0&0&\frac{2EI_z}{L}&0&-\frac{6EI_z}{L^2}&0&0&0&\frac{4EI_z}{L}\end{bmatrix})


# Flächenelemente



# Volumenelemente




# Beispiel des Halbrahmens:

Die Finite Elemente Berechnung des Übungsbeispiel von Grund auf, kann hier eingesehen werden: 

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/AIztok/FH_Jupyter/main?labpath=FH_SBB_FEM_Example.ipynb)

(öffnet das Jupyter Nootbook in Binder, womit der Quellcode über den Webbrowser eingesehen / geändert / berechnet werden kann)




