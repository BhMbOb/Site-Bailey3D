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
  img1="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Schematic/Schematic_Trove.jpeg?raw=true"
  img2="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pencil/Vintage_Trove.jpeg?raw=true"
  img3="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Chalk/Chalkboard_Trove.jpeg?raw=true"
  img4="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pencil/Pencil_Vice.jpeg?raw=true"
  img5="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Charcoal/Charcoal_Rift.jpeg?raw=true"
  img6="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Schematic/Graph_Rift.jpeg?raw=true"
  img7="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pencil/Notepad_Trove.jpeg?raw=true"
  img8="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Chalk/ChalkDrawing_Trove.jpeg?raw=true"
  img9="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pen/ByroPen_Trove.jpeg?raw=true"
  img10="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pen/InkPen_Trove.jpeg?raw=true"
  img11="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Charcoal/Pastel_Trove.jpeg?raw=true"
  img12="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pen/GelPen_Vice.jpeg?raw=true"
%}

## Variants
<section id="variants"/>

All SketchIt materials are found under the folder `SketchIt/Materials/..`.<br>
(For example `SketchIt/Materials/MI_SketchIt_PP_Vintage`)

Here is a list of all the preset variants currently available:

|Variant Name:|Description:|Documentation:|
|:---|:---|:---|
|<b>Byro Pen:</b>|Emulates the look of a bold and expressive ink pen, perfect for adding dynamic lines and shading to your artwork.|[MM_PP_SketchIt_InkPen](../shader_docs/MM_PP_SketchIt_InkPen)|
|<b>Chalk Board:</b>|Creates a chalkboard-style effect with a textured and grainy appearance, ideal for adding a nostalgic and playful feel to your designs.|[MM_PP_SketchIt_ChalkBoard](../shader_docs/MM_PP_SketchIt_ChalkBoard)|
|<b>Chalk Drawing:</b>|Mimics the look of chalk pastels on a dark background, great for creating whimsical and ethereal art.|[MM_PP_SketchIt_ChalkBoard](../shader_docs/MM_PP_SketchIt_ChalkBoard)|
|<b>Charcoal:</b>|Provides a smudged and textured effect that imitates the look of a charcoal drawing, perfect for adding depth and drama to your sketches.|[MM_PP_SketchIt_Charcoal](../shader_docs/MM_PP_SketchIt_Charcoal)|
|<b>Gel Pen:</b>|Emulates the smooth and vibrant lines of a gel pen, great for creating sharp and precise artwork with a touch of boldness.|[MM_PP_SketchIt_InkPen](../shader_docs/MM_PP_SketchIt_InkPen)|
|<b>Graph Paper:</b>|Adds a subtle grid pattern to your designs, perfect for creating technical drawings and layouts with a touch of personality.|[MM_PP_SketchIt_Schematic](../shader_docs/MM_PP_SketchIt_Schematic)|
|<b>Ink Pen:</b>|Simulates the classic look of an ink pen, ideal for creating clean and crisp lines with a hand-drawn feel.|[MM_PP_SketchIt_InkPen](../shader_docs/MM_PP_SketchIt_InkPen)|
|<b>Notepad:</b>|Adds a charming and rustic touch to your designs, mimicking the look of pencil or pen on a rough paper texture.|[MM_PP_SketchIt_HandDrawn](../shader_docs/MM_PP_SketchIt_HandDrawn)|
|<b>Pastel:</b>|Creates a soft and delicate effect with a pastel-like appearance, great for adding a gentle and dreamy feel to your artwork.|[MM_PP_SketchIt_Charcoal](../shader_docs/MM_PP_SketchIt_Charcoal)|
|<b>Pencil:</b>|Emulates the look of pencil on paper, providing a natural and organic feel that's perfect for sketching and drawing.|[MM_PP_SketchIt_HandDrawn](../shader_docs/MM_PP_SketchIt_HandDrawn)|
|<b>Schematic:</b>|A technical blueprint-style effect with sharp lines and a 3D grid, perfect for creating diagrams and technical illustrations with a unique and eye-catching flair.|[MM_PP_SketchIt_Schematic](../shader_docs/MM_PP_SketchIt_Schematic)|
|<b>Vintage:</b>|Adds an old-school and nostalgic touch to your designs with an aged and stained paper texture, great for creating vintage and retro-inspired artwork.|[MM_PP_SketchIt_HandDrawn](../shader_docs/MM_PP_SketchIt_HandDrawn)|


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
See the documentation by Epic on [Color Grading anf Filmic Tonemapper](https://docs.unrealengine.com/4.27/en-US/RenderingAndGraphics/PostProcessEffects/ColorGrading/) for more info on this.
