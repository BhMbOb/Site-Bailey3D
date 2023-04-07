---
title: Sketch-It
subtitle: Schematic (Master Material)
description: ..
carousels:
  - images: 
    - image: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Schematic/Schematic_Trove.jpeg?raw=true
    - image: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Schematic/Graph_Rift.jpeg?raw=true
    - image: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Schematic/Graph_Vice.jpeg?raw=true
    - image: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Schematic/Schematic_Rift.jpeg?raw=true

layout: page
image: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/banner.png?raw=true
menubar: sketchit_menu

store_name: sketch_it

---
{% include carousel.html height="50" unit="%" duration="99999" number="1" %}

|<b>Category</b>|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|:---|
|<b>0. Global</b>|Enable Detail Lighting?|Should the detail lighting effect be enabled?|
||Enable Detail Sketch?|Should the detail (secondary) sketch be enabled?|
||Enable Grid?|Should the grid be enabled?|
||Enable Paper Effect?|Should the paper effect be applied to the background?|
||Enable Secondary Grid?|Optional secondary grid effect.|
||Detail Color|The main color of the sketch / grid effects.|
||Schematic Color|Controls the color of the main schematic background.|
||Use Final Render As Background?|Should the final rendered scene be used as the background color?|
|<b>1. Paper</b>|Mask Texture|Mask texture used to simulate a paper effect.|
||Scale|Overall scale of the paper effect in meters.|
||Strength|Overall strength of the paper effect, higher values will result in a more crumpled paper look.|
|<b>2. Grid</b>|Color|The color tint applied to the grid.|
||Opacity|Overall opacity of the grid effect.|
||Scale|Overall tiling of the grid in meters.|
||Thickness|Thickness of the grid in centimeters.|
||Use Unique Color?|Should the grid use a unique color tint?|
|<b>3. Secondary Grid</b>|Use Unique Color?|Should the secondary grid use a unique color tint?|
||Color|The color tint of the secondary grid.|
||Opacity|Overall opacity of the secondary grid.|
||Size|Overall tiling of the secondary grid in meters.|
||Thickness|Thickness of the secondary grid in centimeters.|
|<b>4. Sketch</b>|Strength|Overall strength of the sketch effect.|
||Pencil Color|The color of the pencil drawing.|
||Use Custom Color?|Should the sketch effect use a unique color?|
|<b>5. Detail Sketch</b>|Use Unique Color?|Should the detail sketch effect use a unique color?|
||Strength|The overall strength of the detail sketch.|
||Pencil Color|The color of the detail sketch effect.|
|<b>6. Detail Lighting</b>|Effect Strength|The overall strength of the detail lighting effect.|
||Grunge Strength|Strength of the grunge mask applied to the detail lighting, very low values usually suffice here.|
||Color|The color tint of the detail lighting effect.|
||Cutoff|Cutuff value applied to the detail lighting mask, used to give harder/softer edges.|
||Invert Mask?|Should the grunge mask be inverted?|
||Mask Scale|Overall scale of the grunge mask in meters.|
||Mask Texture|The texture used as the grunge mask.|
||Use Unique Color?|Should the detail lighting use a unique color tint?|
|<b>7. Advanced</b>|Detail Sketch - Cutoff|Cutoff value used to give harder/softer edges on the detail sketch.|
||Detail Sketch - Maximum Thickness|Controls the maximum thickness fraction on the detail sketch.|
||Grid - Render Distance|Used to fade out the grid at a given distance. This is useful to avoid ailiasing when rendering the grid from very far away.|
||Sketch - Maximum Thickness|Controls the maximum thickness fraction of the sketch effect. Higher vaules will result in thicker lines rendering.|
||Sketch - Minimum Thickness|Controls the minimum thickness fraction of the sketch effect. Lower values will result in higher frequency detail being ignored.|
