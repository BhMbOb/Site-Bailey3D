---
layout: post
title: "Tree Root Generator (Houdini)"
img: https://www.dropbox.com/s/p5ftv8rrvzqybvf/tree_roots.gif?raw=1
description: ""
tag: [Assets, Tools, Pipeline]
---

This is a Houdini based tool used to generate tree roots from input spawn positions, with a variety of inputs.

It uses a 'Space Colonization' algorithm for branch generation rather than L systems. This algorithm typically gives a more realistic distribution of branches, 
as each node is fighting against other existing nodes for growth space.

---

### Space Colonization<br>

Compared to typical branch generation methods that work outward from generated branches, the Space Colonization method works kind of in reverse.
The the generator is given a series of input "Attractors" which act as possible target positions for branches to grow toward. During each cycle all attractors are looped over to find the nearest Node (knot of a branch) within a maximum attraction distance, and then a new node is created at the average position for each nodes closest attractors.

You can see this in action in the gifs below. Where the nodes work outward into the available attractor positions.

|<b>Space Colonization - Single Node</b>|<b>Space Colonization - Multiple Nodes</b>|
| :---: | :---: |
|![Image](https://www.dropbox.com/s/zbpsnqbzcu7cbka/space_colonisation_single.gif?raw=1)|![Image](https://www.dropbox.com/s/31evtemwsgx4yz3/space_colonisation_multi.gif?raw=1)|
| Roots are spawned from a single node.<br> The roots are free to expand as far as possible as they<br>are only fighting against themselves. | Roots are spawned from multiple nodes.<br> Each root is fighting with both itself and its siblings.<br> Resulting in a system that has to fight for growth space. |

|<b>Space Colonization - Inside a 3D Volume</b>|
|---|
|![Image](https://www.dropbox.com/s/9ctk895hbc4yfjr/space_colonization_volume.gif?raw=1)|
|Since the space colonization algorithm goes of possible attraction points, data can be generated on any input volume.|

---

### Inputs

![Image](https://www.dropbox.com/s/58wx6nhqv07kez8/inputs.jpg?raw=1){: .center-image}

| Input | Description |
|---|---|
| <b>Spawn Positions</b> | A series of vertices acting as spawn positions for the roots. |
| <b>Spawn Volume</b> | Geometry used as the spawn volume for the attraction points. |
| <b>Distribution Bounds</b> | Geometry used as the bounds for all attraction points. Positions outside of the geometry are disallowed. |

### Parameters

![Image](https://www.dropbox.com/s/hc821muassasuya/properties.jpg?raw=1){: .center-image}

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
| ![Image](https://www.dropbox.com/s/lq1lpgwqun6dao7/surface.jpg?raw=1) | ![Image](https://www.dropbox.com/s/5do0fb2j205q5m0/volume.jpg?raw=1) |
| Example of attraction point distribution on surface mode. | Example of attraction point distribution on volume mode. |


| <b>Max Branch Levels : 2</b> | <b>Max Branch Levels : 6</b> |
|---|---|
| ![Image](https://www.dropbox.com/s/12i2cdcr6tlqqa6/2_levels.jpg?raw=1) | ![Image](https://www.dropbox.com/s/31yw4bkttru9vk5/6_levels.jpg?raw=1) |

| <b>Conforming To Environments</b> |
|---|
|![Image](https://www.dropbox.com/s/xj6hauo21fv7jjn/wall_example.gif?raw=1)|
|Since any input geometry can be given, the roots can conform to any environment. Here you can see them creeping up a wall.<br>With some minor changes the algorithm could also raycast into geometry to ensure only attraction points on one given side of a surface can interfere with each other (at the cost of generation times).|