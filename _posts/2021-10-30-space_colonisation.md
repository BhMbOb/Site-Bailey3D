---
layout: post
title: Tree Root Generator (Houdini)
description: ..
hero_image: https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/thumb.gif?raw=true
image: https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/thumb.gif?raw=true
hero_height: is-large
hero_darken: true
tags: [Houdini, Python, Assets, Tools, Pipeline]
portfolio: space_colonization
#series: example_blog_series
---

This is a Houdini based tool used to generate tree roots from input spawn positions, with a variety of inputs.

It uses a Space Colonization algorithm for branch generation rather than L systems. This algorithm typically gives a more realistic distribution of branches, 
as each node is fighting against other existing nodes for growth space.

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/thumb.gif?raw=true){: .center-image}

---

### Space Colonization<br>

Compared to typical branch generation methods that work outward from generated branches, the Space Colonization method works kind of in reverse.
The the generator is given a series of input "Attractors" which act as possible target positions for branches to grow toward. During each cycle all attractors are looped over to find the nearest Node (knot of a branch) within a maximum attraction distance, and then a new node is created at the average position for each nodes closest attractors.

You can see this in action in the gifs below. Where the nodes work outward into the available attractor positions.

|<b>Space Colonization - Single Node</b>|<b>Space Colonization - Multiple Nodes</b>|
| :---: | :---: |
|![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/space_colonisation_single.gif?raw=true)|![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/space_colonisation_multi.gif?raw=true)|
| Roots are spawned from a single node.<br> The roots are free to expand as far as possible as they<br>are only fighting against themselves. | Roots are spawned from multiple nodes.<br> Each root is fighting with both itself and its siblings.<br> Resulting in a system that has to fight for growth space. |

|<b>Space Colonization - Inside a 3D Volume</b>|
|---|
|![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/space_colonization_volume.gif?raw=true)|
|Since the space colonization algorithm goes of possible attraction points, data can be generated on any input volume.|

---

### Inputs

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/inputs.jpg?raw=true){: .center-image}

| Input | Description |
|---|---|
| <b>Spawn Positions</b> | A series of vertices acting as spawn positions for the roots. |
| <b>Spawn Volume</b> | Geometry used as the spawn volume for the attraction points. |
| <b>Distribution Bounds</b> | Geometry used as the bounds for all attraction points. Positions outside of the geometry are disallowed. |

### Parameters

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/properties.jpg?raw=true){: .center-image}

| Parameter | Description |
| --- | --- |
| <b>Generation Method</b> | Method used to distribute the node attraction points. |
|     Surface | Attraction points are distributed only on the surface of the spawn volume |
|     Volume | Attraction points are distributed anywhere within the spawn volume |
|||
| <b>Recursion Depth</b>| Number of loops used for the generation algorithm. |
| <b>Attraction Point Density</b> | Density of the attraction point generation (10cm² for surface - 10cm³ for volume) |
| <b>Attraction Radius</b> | Distance a valid Node must be from an attraction point to be considered a valid target (cm) |
| <b>Attraction Deadzone</b> | Any attraction points closer than this value to a node are considered occupied. |
| <b>Max Branch Levels</b> | Maximum level depth of branches allowed (Ie, 3 = root -> branch -> twig) |
| <b>Max Child Branches</b> | Maxumum amount of child branches a single branch can have. |
|||
| <b>Root Thickness</b> | Thickness in centimeters of the branch. This is multiplied by current branch level (Ie, thickness of 3 will result in level 1 being 3cm, level 2 being 2cm, level 3 being 1cm) |
| <b>Root Smoothness</b> | Optional post smoothing of the generated root splines. |
| <b>Roots Subdivisions</b> | Number of cylindrical edges in each root. Level 0 branches will use this value, with each later level dropping the density by 1 until a minimum of 3 is reached. |


### Examples

| <b>Generation Method : Surface</b> | Generation Method: Volume |
|---|---|
| ![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/surface.jpg?raw=true) | ![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/volume.jpg?raw=true) |
| Example of attraction point distribution on surface mode. | Example of attraction point distribution on volume mode. |


| <b>Max Branch Levels : 2</b> | <b>Max Branch Levels : 6</b> |
|---|---|
| ![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/2_levels.jpg?raw=true) | ![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/6_levels.jpg?raw=true) |

| <b>Conforming To Environments</b> |
|---|
|![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Roots/wall_example.gif?raw=true)|
|Since any input geometry can be given, the roots can conform to any environment. Here you can see them creeping up a wall.<br>With some minor changes the algorithm could also raycast into geometry to ensure only attraction points on one given side of a surface can interfere with each other (at the cost of generation times).|