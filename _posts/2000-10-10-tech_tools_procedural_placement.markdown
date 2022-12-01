---
layout: post
title: "Procedural Asset Placement Tools"
img: https://github.com/Bailey3D-Website/2019/blob/main/projects/Spline%20Tools/thumb.gif?raw=true # Add image post (optional)
description: Some examples of tools created for procedural placement and generation of assets - includes randomness, modularity, proceduralism ...
tag: [Environment Art, Art, Lighting]
---

These are a series of Unreal based tools focused around procedural generation of geometry, and procedural placement of environment props.
They were all created using a mix of C++ and Blueprints.

The main aim of these tools was to cut down in creation time - taking processes that would typically be full tasks and replacing it with a parameterised, fluid system.

------

### Procedural Railbed Placement

![Image](https://github.com/Bailey3D-Website/2019/blob/main/projects/Spline%20Tools/thumb2.gif?raw=true){: .center-image}

A C++ based Actor type which takes a single input for 'Outer Rail Mesh' and an array of 'Plank Meshes'. Used for modular and dynamic placement of rails within an environmment.
Tangents and Knots of the spline can be easily tweaked to conform to the environment without need of many variations.

All planks are instanced meshes, while the outer rail is an Unreal Spline Mesh. The tool contains extra options for density of the spline mesh to help combat the runtime cost.

------

### Procedural / Randomized Book Placement

![Image](https://github.com/Bailey3D-Website/2019/blob/main/projects/Spline%20Tools/thumb.gif?raw=true){: .center-image}

This is a Blueprint based tool used to place books dynamically along a spline. This was developed for a Library Environment, which contained upward of 100k book meshes, the randomness and instancing helped to break up the look of the shelves, while also improving performance.

It has two major components:

__1 - Placement:__ <br>
Places the books along the spline, with additional parameters for things such as "Placement Messiness" for controlling how messy the placement is, and "Random Scale Range" for the overall book scaling.
The books are all a single instanced mesh, all using the exact same material.

__2 - Material Randomness:__ <br>
Using a single per-instance random integer, multiple random values are generated, which is used in the shader for a few different effects:
- Random book name UVs, selected from a single 1D flipbook.
- Random tinting, from a single 1D look up texture.
- Random patternation, again selected from a 1D flipbook.

------

### Dynamic Pipes

![Image](https://github.com/Bailey3D-Website/2019/blob/main/projects/Spline%20Tools/bailey-martin-a809f0-61f6f37fe755463f89c1c1182d9904d7-mv2.gif?raw=true){: .center-image}

A relatively simple Blueprint based tool which generates a spline mesh per-segment of a spline, with additional parameters for tiling a pipe connector mesh at <i>X</i> intervals.

The pipes also use a Tri-planar material which means the generated mesh does not use the UV channel. Saving a little bit of performance cost, and also helping to alleviate tiling.

------

### Modular Bookcase

![Image](https://github.com/Bailey3D-Website/2019/blob/main/projects/Spline%20Tools/bailey-martin-sdf.gif?raw=true){: .center-image}

Blueprint based actor used to generate modular bookcases. All meshes are instanced where possible, and a single parent material is used for all pieces.
The system used 8 unique bookcase pieces + 1 for the shelves and 1 for the doors.

This was also made for a Library Environment, and save a lot of time compared to hand building different variants, while also helping with art fatigue.

The actor contains parameters for things such as "Rows Count", "Columns Count" and "Use Drawers?"