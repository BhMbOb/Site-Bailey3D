---
layout: post
title: "Cloth Shader"
img:  https://www.dropbox.com/s/kwj7o7m0jsultw6/thumb.png?raw=1
description: Study in creating a custom cloth shader with realistic fuzz and fiber masking.
tag: [Tech Art, Shader, Lighting]
---
An experiment in cloth shading. This uses a few different methods to go from a standard surface / cloth brdf to something more reminiscent of an actual fibrous surface.

The shader is using a few effects, such as single layer pom/shadowing for the fuzz layer, procedural curvature aware masking for fuzz breakup at the edges of the surface, and specular / fibre occlusion, just to list the main ones.

The examples here are each using a fiber height map and fuzz mask map, both of which are generating normals within the shader.
These textures can be swapped out for completely different effects depending on the surface look.

![Image](https://www.dropbox.com/s/khew0bobro7u2sl/turnaround.gif?raw=1){: .center-image}
------


![Image](https://www.dropbox.com/s/ozvrkgy4l0lbca5/05.png?raw=1){: .center-image}

Left: Custom Cloth Shader - Right: Standard Surface Shader

------

![Image](https://www.dropbox.com/s/elotrl3szm0djdu/07.png?raw=1){: .center-image}

The maps used - Normals are generated from the Fibres and Pattern map in realtime, along with parallax + shadowing from the fibres map.

------

![Image](https://www.dropbox.com/s/lrz8uxw1711c5vl/08.png?raw=1){: .center-image}

------

![Image](https://www.dropbox.com/s/oqeic32dm93jemu/02.png?raw=1){: .center-image}

[Fuzz + Fibers Masking + Fibers Self Shadowing] - Edge/curvature masking used to make the surface look less flat