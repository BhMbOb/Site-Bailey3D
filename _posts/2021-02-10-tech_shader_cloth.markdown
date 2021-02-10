---
layout: post
title: "Cloth Shader"
img:  https://drive.google.com/uc?export=view&id=1rfctDQI929Ci08FlO6e3F34OvEcuJjeQ
description: Study in creating a custom cloth shader with realistic fuzz and fiber masking.
tag: [Tech Art, Shader, Lighting]
---
An experiment in cloth shading. This uses a few different methods to go from a standard surface / cloth brdf to something more reminiscent of an actual fibrous surface.

The shader is using a few effects, such as single layer pom/shadowing for the fuzz layer, procedural curvature aware masking for fuzz breakup at the edges of the surface, and specular / fibre occlusion, just to list the main ones.

The examples here are each using a fiber height map and fuzz mask map, both of which are generating normals within the shader.
These textures can be swapped out for completely different effects depending on the surface look.

------

![Image](https://drive.google.com/uc?export=view&id=1VqixDjcA-BEK2gsl5sKVvqYcUj_X3Rdi){: .center-image}

Left: Custom Cloth Shader - Right: Standard Surface Shader

------

![Image](https://drive.google.com/uc?export=view&id=1n4XgJIfo6FWqpGvc1fPvPCf2t_E6y0lm){: .center-image}

The maps used - Normals are generated from the Fibres and Pattern map in realtime, along with parallax + shadowing from the fibres map.

------

![Image](https://drive.google.com/uc?export=view&id=119XuaQilX_PJEgCgpuBTCxDglur2WC_o){: .center-image}

------

![Image](https://drive.google.com/uc?export=view&id=1fmCv-1PZQ58D5-8Vzci6B1Asd4QRUa0c){: .center-image}

![Image](https://drive.google.com/uc?export=view&id=1VKxlSXyPM8EvRE1YVix7AUrdlNJonHNp){: .center-image}

[Fuzz + Fibers Masking + Fibers Self Shadowing] - Edge/curvature masking used to make the surface look less flat