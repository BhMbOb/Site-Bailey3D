---
layout: post
title: "Drop To Terrain [Houdini]"
img: https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Drop/thumb.png?raw=true
description: Houdin script used to drop geometry to input terrain with different drop modes.
tag: [Assets, Tools, Pipeline]
---

Drop To Terrain is a Houdini based tool used to drop different types of geometry to terrain, using different methods.<br>
It includes a few different drop methods for different geometry types, from more deformable geometry such as tree roots, to hard surface geometry such as rocks.

It's worth noting this doesn't run a physics simulation, it's only for direct dropping to terrain.<br>
A good use for this would be foliage placement.  Using per-vertex drop to deform tree roots to terrain, and the bounds based dropfor dropping tree meshes.

You can download the digital asset <a href="https://github.com/Bailey3D-Website/2021/tree/main/resources/houdini_drop">here</a>. It includes a HDA (Terrain Drop), and an example file including the rubber toy dropping to a simple terrain.

---

### Parameters:

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Drop/params.jpg?raw=true){: .center-image}

| Parameter | Description |
| --- | --- |
| <b>Drop Mode</b> | The method used for dropping the geometry to the terrain |
|     Vertex | Each vertex is dropped independently |
|     Element | Each element is dropped independently (sub-mesh) |
|     BBox (Center) | Drop is calculated from the center of the bounding box |
|     BBox (Corners) | Drop is averaged from the 4 lower corners of the bounding box |
|||
| <b>Volume Preservation Mode</b>| Method used to preserve the vertical height in the mesh at each vertex |
|     BBox | Vertical height of the mesh relative to the bounding box is used for thickness. This allows for overhanging geometry at the expense of fully accurate deformation, as the drop can only start from the bottom plane of the bbox |
|     Vertical Thickness | Uses the actual vertical positions of the mesh (Up Axis) to calculate the mesh thickness at each drop position. This gives geometry that's perfectly deformed to therrain, however can struggle when it comes to overhanging areas. |
|||
| <b>Hit Normal Influence</b> | Overall strength the normals of the terrain have on the final drop [0..1] |
| <b>Cap Holes?</b> | Caps open edges in the geometry. Useful as open edges can cause thickness calculations to fail. |
| <b>Height Offset</b> | Height offset applied to the geometry in the up axis. Useful to make the mesh sink into the terrain slightly |
| <b>Fractional Offset?</b> | When true, a [0..1] fraction is used for the offset. Where a value of 1.0 is equal to the meshes bounds in the up axis |
| <b>Smooth Strength</b> | Strength of the geometry smoothing applied to the mesh after drop is complete. This can help to clean up noisy geometry when hit normal influence is non-zero |

---

### Example: Per Vertex (Thickness Based)

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Drop/per_vert_with_thickness.jpg?raw=true){: .center-image}

Properties: `Drop Mode: Vertex`  `Volume Mode: Vertical Thickness`

This mode is best used on geometry that should flow with the terrain, as the geometry is actually deformed with the drop mesh (Ie, tree roots)

Drops each vertex in the mesh independently to the terrain. Gathers a terrain normal for each vertex, meaning normal deformation will match exactly to the terrain below.


### Example: Per Vertex Drop (BBox Based)

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Drop/vertex_with_bbox.jpg?raw=true){: .center-image}

Properties: `Drop Mode: Vertex` `Volume Mode: BBox`

Same drop method as the previous example, but uses a Bounds based thickness calculation. Useful for larger meshes with overhanging pieces, as the height is preserved (see the image comparisons)

| Thickness Based      | BBox Based |
| ----------- | ----------- |
| ![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Drop/vertex_with_thickness.jpg?raw=true)| ![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Drop/vertex_with_bbox.jpg?raw=true) |
| Note the inaccurate looking drop on the overhanging portions of the mesh (snout)   | Overhanging areas have vertical height preserved        |


### Example: Per Element Drop

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Drop/elements_with_thickness.jpg?raw=true){: .center-image}

Properties: `Drop Mode: Element` `Volume Mode: Vertical Thickness`

Drop is applied to each sub-mesh in the geometry using the average offset for all verts in the element, resulting in a final drop that has no deformation.
Useful for hard surface geometry such as rocks and clutter.


### Example: BBox Center Drop / BBox Corners Drop

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Drop/bbox_center_with_bbox_corners.jpg?raw=true){: .center-image}

Properties: `Drop Mode: BBox (Center) or BBox (Corners)`

Uniform drop offset is applied across the whole geometry. <br>
When using BBox (Corners) drop position is the average of the 4 bottom corners of the bounds.<br>
When using BBox (Center) drop is calculated from the center of the bounds.


---

### The Other Stuff

The node graph itself is pretty basic, as the drop is all calculated through a python node inside the network. But here it is for those who are interested:

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Houdini%20Drop/node_graph.jpg?raw=true){: .center-image}

And here's a gist of the python code for the actual drop:

<style type="text/css">
  .gist-file
  .gist-data {max-height: 500px;}
</style>
<script src="https://gist.github.com/Bailey3D/7d8f17750df1b33481070e6542cfd7f0.js"></script>
