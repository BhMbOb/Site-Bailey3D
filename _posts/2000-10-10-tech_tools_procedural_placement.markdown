---
layout: post
title: "Procedural Asset Placement"
img: https://drive.google.com/uc?export=view&id=1JccX7pjQEnh6m0dsE_cUnZ9Qxtxuzjx9 # Add image post (optional)
description: Some examples of tools created for procedural placement of assets - includes randomness, modularity, proceduralism ...
tag: [Environment Art, Art, Lighting]
---
Setting up systems for different types of procedural assets is something that I have done for multiple projects, and can be used for things such as saving time, minimizing art fatigue and giving more realistic outputs. This post is going to cover some of the different procedural assets I've created for multiple projects.

In the top image - Procedural book placement system with tinting. Uses the mesh bounding box and some maths to give random height, thickness, rotation and offsets. Every mesh in this gif uses a single instanced mesh, and single shader with pseudo-random tinting.

------

![Image](https://drive.google.com/uc?export=view&id=1oKhtzyixgRhr4xBgNKFc9l-v0IKfaGvb){: .center-image}

Procedural and modular bookcase system. Again all unique meshes are instanced, and a single shader is used for all pieces. The system uses 8 unique bookcase pieces along with the shelf and door, meaning the whole system uses 10 draw calls. System is parameterized with settings such as: RowsCount, ColumsCount and bUseDrawers. This system helped to save a lot of time and avoid art fatigue within the library scene along with improving the scenes overall performance.

![Image](https://drive.google.com/uc?export=view&id=1kCyjtDGM790jMTdtx_AH0H1Q4ZtuZrQw){: .center-image}