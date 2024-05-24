---
title: 013_Grasshopper
draft: false
tags:
  - "#3D"
  - "#FEM"
---

# Allgemein



# Installation

Grasshopper wird zusammen mit dem Rhino3D installiert.
Grasshopper öffnen unter Werkzeuge/Grasshopper:

![[Pasted image 20240511121920.png]]

# Befehle



https://bimcorner.com/8-grasshopper-shortcuts-which-you-should-know/


Doppelklick auf die Bearbeitungsfläche und Befehl schreiben



### Scribble: Notizen machen 

Shift halten um mehrere Inputs in einen Block zu ziehen (generiert mehrere Outputs)




### Verbindungen / Wires

Display / Draw fancy wires eingeschaltet.

https://www.grasshopper3d.com/notes/index/show?noteKey=What_is_the_difference_between_the_dot_line_and_single_line_and_double_line_in_the_Grasshopper_file%3F


When the **Fancy Wires** option is enabled in the Grasshopper **Display** menu, then the wire display tells you something about the data that flows through them. There are 4 different wire display types:

  1. **Single orange wire:** no data is transferred, the parameter on the left end is empty.

  2. **Single grey wire:** a single data item is transferred.

  3. **Double grey wire:** a list of data items is transferred.

  4. **Double dashed grey wire:** multiple lists of data items are transferred.


![[Pasted image 20230905104357.png]]

"Graft" and  "Flatten" changes the data structure inside a parameter. Sometimes it is necessary to modify the data structure because the default layout does not result in the desired operations. Imagine you divide 5 closed curves into 10 segments each. The result of this operation is a data structure of 5 lists with 10 items (points) each. If you were to Flatten this structure, you'd end up with a single list containing 50 items. If you were to Graft this structure, you'd end up with 50 lists of one item each.



### Cluster

1. Replace your inputs with Cluster Input Components
2. Connect your outputs with Cluster Output Components
3. Select your whole definition. Right click in open space and click Cluster.
4. You can rename the cluster
5. You can password protect your cluster by right clicking the cluster and assigning a password.


### Display / Draw full names
Zeigt den vollen Text statt nur Kurzbezeichnung.



Kopieren

Shift+Alt+ziehen



Bake: 


## Datenstruktur



Datatree
https://bimcorner.com/a-beginners-guide-to-data-trees-in-grasshopper/
https://www.youtube.com/watch?v=uHXaEWQDV9w&ab_channel=LearnGrasshopper






# Weitere Unterlagen