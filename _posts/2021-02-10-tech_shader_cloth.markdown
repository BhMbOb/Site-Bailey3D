---
layout: post
title: "Cloth Shader"
img:  https://www.dropbox.com/s/ha66k7toi59bbfo/cloth_turnaround.gif?raw=1
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

![Image](https://www.dropbox.com/s/elotrl3szm0djdu/07.png?raw=1){: .center-image}
(Example of the data maps used)

## Renders:

![Image](https://www.dropbox.com/s/kwj7o7m0jsultw6/thumb.png?raw=1){: .center-image}

![Image](https://www.dropbox.com/s/pmlde33hv2wqklj/materials.png?raw=1){: .center-image}

![Image](https://www.dropbox.com/s/oqeic32dm93jemu/02.png?raw=1){: .center-image}
