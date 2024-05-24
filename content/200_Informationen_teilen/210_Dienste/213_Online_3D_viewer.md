---
title: 213_Online_3D_viewer
draft: false
tags:
  - 3D
  - BIM
  - IFC
---
# Allgemein

Der [3Dviewer.net](https://3dviewer.net/index.html) ermöglich es uns verschiedene Dateienformate in unseren Browser zu öffnen.
Es werden verschiedene Formate ermöglicht, unter anderen .3dm (siehe [[012_Rhino_3D]]), .IFC (siehe [[145_IFC]]).

# Teile von Modellen

Wenn nur eine lokal am Rechner gespeicherte Datei geöffnet wird, dann kann diese nicht mit anderen über den 3Dviewer geteilt werden und dient nur uns, damit wir ein Modell uns anschauen, messen, im anderen Format speichern usw.. 

Ist er gewünscht eure 3D Modell mit anderen einfach zu teilen, dann ist es erforderlich die Datei zu hosten. 

Für diese Internetseite werden die 3D Dateien auf GitHub in einem Repository (siehe [[212_Git]]) hochgeladen. Diese Datei hat dann einen Link (URL) der im Browser sichtbar ist, z.B.:
*https://github.com/AIztok/DiTWP_Data/blob/main/Rhino/test_1.3dm*

Und im 3Dviewer wird das Modell über das URL geöffnet:

![[Pasted image 20240524160927.png]]

Danach kann dieses Modell mit anderen geteilt werden (sharing link) oder über ein iframe auf einer Internetseite eingepflegt werden.

![[Pasted image 20240524160753.png]]

Beispiel:

<iframe width="640" height="480" style="border:1px solid #eeeeee;" src="https://3dviewer.net/embed.html#model=https://raw.githubusercontent.com/AIztok/DiTWP_Data/main/Rhino/test_1.3dm$camera=21.40111,-6.79451,-24.13458,32.93161,0.01415,-32.33947,0.00000,1.00000,0.00000,45.00000$projectionmode=orthographic$envsettings=fishermans_bastion,off$backgroundcolor=42,43,46,255$defaultcolor=200,200,200$defaultlinecolor=100,100,100$edgesettings=off,0,0,0,1"></iframe>