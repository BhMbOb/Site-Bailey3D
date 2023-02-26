---
layout: post
title: "Cloth Shader"
img:  https://github.com/Bailey3D-Website/2021/blob/main/projects/Cloth%20Shading/cloth_turnaround.gif?raw=true
description: Study in creating a custom cloth shader with realistic fuzz and fiber masking.
tag: [Tech Art, Shader, Lighting]
---
This was experiment in cloth shading. This uses a few different methods to go from a standard surface / cloth brdf to something more reminiscent of an actual fibrous surface.

A few of the main effects this shader utilizes include:

- Single layer parallax shadowing (for the fuzz layer)

- High-frequency normals calculated from height maps

- Curvature edge masking, for altering opacity at grazing angles

- Specular occlusion for the fibers to help simulate the self shadowing and fuzzyness of the surface

- Low frequency normals (for larger scale surface deformation)

- Statically compiled variants for using Colour Tint Maps and Dual-tone tinting

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Cloth%20Shading/07.png?raw=true){: .center-image}
(Example of the data maps used)

## Renders:

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Cloth%20Shading/03.png?raw=true){: .center-image}

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Cloth%20Shading/materials.png?raw=true){: .center-image}

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Cloth%20Shading/02.png?raw=true){: .center-image}
