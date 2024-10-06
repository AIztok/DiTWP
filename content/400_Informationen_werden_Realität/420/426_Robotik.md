---
title: 426_Robotik
draft: false
tags:
  - CAM
  - FAB
---



# Robot Operating System

https://de.wikipedia.org/wiki/Robot_Operating_System





# URDF 

Universal robotic description file


## Beispiel einer URDF

Here’s the URDF code with inline comments added for better understanding. I’ll explain each section in detail directly in the code:

### Full URDF File with Inline Comments


```xml
<!-- Root-Element, das den Roboter definiert -->
<robot name="simple_robot_arm">
  
  <!-- Definiert das Basisglied des Roboters -->
  <link name="base_link">
    <!-- Visuelles Erscheinungsbild des Basisglieds -->
    <visual>
      <geometry>
      
        <!-- Eine Box mit den Maßen 0,5 x 0,5 x 0,1 Meter stellt die Basis dar -->
        <box size="0.5 0.5 0.1" />
      </geometry>
      <!-- Material/Farbe des Basisglieds -->
      <material name="blue"/>
    </visual>
  </link>


  <!-- Definiert das erste Armglied -->
  <link name="link_1">
    <visual>
      <geometry>
        <!-- Ein Zylinder, der das erste Armglied mit einem Radius von 0,05 Metern und einer Länge von 1,0 Meter darstellt -->
        <cylinder radius="0.05" length="1.0"/>
      </geometry>
      <!-- Material/Farbe des ersten Gliedes -->
      <material name="green"/>
    </visual>
  </link>


  <!-- Definiert das zweite Armglied -->
  <link name="link_2">
    <visual>
      <geometry>
        <!-- Ein weiterer Zylinder für das zweite Armglied, ähnlich dem ersten -->
        <cylinder radius="0.05" length="1.0"/>
      </geometry>
      <!-- Material/Farbe des zweiten Gliedes -->
      <material name="red"/>
    </visual>
  </link>


  <!-- Definiert das erste Gelenk zwischen der Basis und dem ersten Glied -->
  <joint name="joint_1" type="revolute">
    <!-- Das übergeordnete Glied ist die Basis (fest) -->
    <parent link="base_link"/>
    <!-- Das untergeordnete Glied ist das erste Armglied, das sich bewegt -->
    <child link="link_1"/>
    <!-- Ursprung gibt die Position und Ausrichtung des Gelenks im Raum an. Hier befindet sich das Gelenk leicht über der Basis (z=0,05) -->
    <origin xyz="0 0 0.05" rpy="0 0 0"/>
    <!-- Die Rotationsachse verläuft entlang der z-Achse -->
    <axis xyz="0 0 1"/>
    <!-- Begrenzung definiert den Rotationsbereich (-1,57 bis 1,57 Bogenmaß oder -90 bis 90 Grad), die maximale Kraft und Geschwindigkeit -->
    <limit lower="-1.57" upper="1.57" effort="100" velocity="1.0"/>
  </joint>

  <!-- Definiert das zweite Gelenk zwischen dem ersten und zweiten Glied -->
  <joint name="joint_2" type="revolute">
    <!-- Das übergeordnete Glied ist das erste Glied -->
    <parent link="link_1"/>
    <!-- Das untergeordnete Glied ist das zweite Armglied, das sich bewegt -->
    <child link="link_2"/>
    <!-- Ursprung definiert, wo sich dieses Gelenk relativ zum ersten Glied befindet (am Ende von link_1, z=1,0 Meter) -->
    <origin xyz="0 0 1.0" rpy="0 0 0"/>
    <!-- Rotationsachse verläuft wieder entlang der z-Achse -->
    <axis xyz="0 0 1"/>
    <!-- Begrenzung definiert die Rotationsgrenzen, die maximale Kraft und Geschwindigkeit, ähnlich wie beim ersten Gelenk -->
    <limit lower="-1.57" upper="1.57" effort="100" velocity="1.0"/>
  </joint>
</robot>
```

Lassen Sie uns nun die wichtigsten Abschnitte im Detail aufschlüsseln:

#### 1. **Robot Element**




```xml
<robot name="simple_robot_arm">
```

- This is the root element of the URDF file. The `name` attribute gives a unique identifier to the robot model. Everything else (links, joints, sensors, etc.) will be contained within this tag.



Dies ist das Hauptelement der URDF-Datei. Das Attribut `name` gibt dem Robotermodell einen eindeutigen Bezeichner. Alles andere (Glieder, Gelenke, Sensoren usw.) wird innerhalb dieses Tags enthalten sein.

2. Glieddefinitionen
Ein Glied repräsentiert einen physischen Teil des Roboters, wie die Basis, ein Armsegment oder einen anderen starren Körper. In unserem Beispiel definieren wir drei Glieder: `base_link`, `link_1` und `link_2`.

##### Basisglied:

```xml
<link name="base_link">   
	<visual>     
		<geometry>       
			<box size="0.5 0.5 0.1" />     
		</geometry>     
		<material name="blue"/>   
	</visual> 
</link>
```

- **Link name**: `base_link` defines the robot’s base.
- **Visual block**: Inside this, we define how the link will look visually.
    - **Geometry**: The shape of the link. Here, it’s a box with dimensions of 0.5m x 0.5m x 0.1m.
    - **Material**: We assign a color to the link (blue). This is mainly for simulation and visualization purposes.

##### Link 1 (Erstes Armsegment):


```xml
<link name="link_1">   
	<visual>     
		<geometry>       
			<cylinder radius="0.05" length="1.0"/>     
		</geometry>     
		<material name="green"/>   
	</visual> 
</link>
```

- Dies definiert das erste Armsegment des Roboters.
- **Zylinder:** Eine zylindrische Form mit einem Radius von 0,05 Metern und einer Länge von 1,0 Meter.
- **Material:** Das erste Armglied wird als grün visualisiert.

##### **Link 2 (Second Arm Segment)**:

```xml
<link name="link_2">   
	<visual>     
		<geometry>       
			<cylinder radius="0.05" length="1.0"/>     
		</geometry>     
		<material name="red"/>   
	</visual> 
</link>
```

- The second arm segment is another cylinder, similar to `link_1`, but it’s visualized as red.

#### 3. Gelenkdefinition

Gelenke definieren die Bewegung zwischen den Gliedern. In diesem Beispiel verwenden wir Drehgelenke, die eine Rotation zwischen zwei Gliedern ermöglichen.

##### Gelenk 1 (Zwischen Basis und Link 1):


```xml
<joint name="joint_1" type="revolute">   
	<parent link="base_link"/>   
	<child link="link_1"/>   
	<origin xyz="0 0 0.05" rpy="0 0 0"/>   
	<axis xyz="0 0 1"/>   
	<limit lower="-1.57" upper="1.57" effort="100" velocity="1.0"/> 
</joint>
```

- **Gelenkname:** `joint_1`, das die `base_link` (Elternteil) mit `link_1` (Kind) verbindet.
- **Ursprung:** Gibt an, wo sich das Gelenk relativ zur Basis befindet (0,05 Meter über der Basis auf der z-Achse).
- **Achse:** Das Gelenk dreht sich um die z-Achse (`0 0 1`).
- **Begrenzung:** Dies definiert den Bewegungsbereich von -1,57 bis 1,57 Bogenmaß (ungefähr -90 bis +90 Grad), die maximale Kraft und Geschwindigkeit für das Gelenk.

#### Gelenk 2 (Zwischen Link 1 und Link 2):

```xml
<joint name="joint_2" type="revolute">   
	<parent link="link_1"/>   
	<child link="link_2"/>   
	<origin xyz="0 0 1.0" rpy="0 0 0"/>   
	<axis xyz="0 0 1"/>   
	<limit lower="-1.57" upper="1.57" effort="100" velocity="1.0"/> 
</joint>
```

- **Gelenkname:** `joint_2`, das `link_1` mit `link_2` verbindet.
- **Ursprung:** Definiert, wo das Gelenk am Ende von `link_1` liegt (1,0 Meter entlang der z-Achse).
- **Achse:** Die Rotationsachse verläuft erneut entlang der z-Achse.
- **Begrenzung:** Ähnlich wie bei `joint_1`, mit einem Bewegungsbereich von -90 bis +90 Grad.


Diese einfache URDF-Datei beschreibt einen grundlegenden Roboterarm mit zwei zylindrischen Gliedern, die durch Drehgelenke verbunden sind. Die Glieder werden durch visuelle und geometrische Eigenschaften beschrieben, während die Gelenke die relative Bewegung zwischen diesen Gliedern definieren. 







Simulator

https://rocksi.net/




https://think.cs.vt.edu/blockpy/