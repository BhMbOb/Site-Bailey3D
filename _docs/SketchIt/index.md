---
title: SketchIt
subtitle: Documentation
description: ""
layout: page
image: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/banner.png?raw=true
menubar: sketchit_menu

store_name: sketch_it

---

## Getting Started
<section id="getting_started"/>

Getting started with SketchIt is as easy as adding one of the pre-existing material templates to a post-processing volume in your map.

If you're new to Unreal, take a look at the documentation by Epic on how to set up a post processing volume in your scene, and apply a material.<br>
- [Epic Games - Post Process Materials](https://docs.unrealengine.com/4.27/en-US/RenderingAndGraphics/PostProcessEffects/PostProcessMaterials/)

{% include carousel.html id="bit_depth_slider"
  img1="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/featured.jpg?raw=true"
  img2="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_vintage.jpg?raw=true"
  img3="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_schematic.jpg?raw=true"
  img4="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_pencil.jpg?raw=true"
  img5="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_ink_pen.jpg?raw=true"
  img6="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_charcoal.jpg?raw=true"
  img7="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_chalk_drawing.jpg?raw=true"
  img8="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_notepad.jpg?raw=true"
  img9="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_chalkboard.jpg?raw=true"
  img10="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_gel_pen.jpg?raw=true"
  img11="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_byro.jpg?raw=true"
  img12="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_pastel.jpg?raw=true"
  img13="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/gallery_graph_paper.jpg?raw=true"
%}

## Variants
<section id="variants"/>

Check out the examples for all of the available templates below. All pages include:
- <b>GIF examples</b> of the filters in action.
- <b>Before and After</b> image comparison sliders.

{% include sketchit/template_thumbs.html %}

All SketchIt materials are found under the folder `SketchIt/Materials/..`.<br>
(For example `SketchIt/Materials/MI_SketchIt_PP_Vintage`)

## Known Limitations / FAQ
<section id="limitations"/>

<b>Why do translucent materials render over some SketchIt effects?</b><br>
This is due to limitations with deferred rendering. It can be fixed by using dithered opacity for translucent materials.

<b>How do I set up SketchIt to work on a mobile project?</b><br>
Mobile projects must ensure that they are using the mobile deferred renderer.<br>
See Epic's documentation on [Mobile Deferred Shading](https://docs.unrealengine.com/5.1/en-US/using-the-mobile-deferred-shading-mode-in-unreal-engine/) for guidance enabling this.

<b>Why are SketchIt effects tonemapped?</b><br>
In order for TemporalAA to work correctly SketchIt effects are rendered "Before Tonemapper", which results in the final rendered scene being tonemapped.
There is no simple fix to this, but you can alter the tonemapper settings yourself in a post-process volume.<br>
See the documentation by Epic on [Color Grading and Filmic Tonemapper](https://docs.unrealengine.com/4.27/en-US/RenderingAndGraphics/PostProcessEffects/ColorGrading/) for more info on this.
