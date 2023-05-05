---
title: Sketch-It
subtitle: Charcoal (Master Material)
description: ..

layout: page
image: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/banner.png?raw=true
menubar: sketchit_menu

store_name: sketch_it

---
## **Charcoal:**

<img src="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Gifs/charcoal.webp">

<!--{% include carousel.html id="bit_depth_slider"
  img1="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Charcoal/Charcoal_Rift.jpeg?raw=true"
  img2="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Charcoal/Charcoal_Trove.jpeg?raw=true"
  img3="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Charcoal/Pastel_Trove.jpeg?raw=true"
  img4="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Charcoal/Pastel_Vice.jpeg?raw=true"
%}-->

---

### **Template: Charcoal:**
<section id="charcoal"/>

{% include image_slider.html id="charcoal_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/charcoal/off.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/charcoal/charcoal.jpeg" percent=0.25 %}

### **Template: Pastel:**
<section id="pastel"/>

{% include image_slider.html id="pastel_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/charcoal/off.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/charcoal/pastel.jpeg" percent=0.25 %}

---

## **Parameters:**

|<b>Category</b>|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|:---|
|<b>0. Global</b>|Enable Charcoal Outline?|When checked then an additional outline effect will be applied.|
||Background Color|Controls the color of the background.|
||Effect Strength|The overall strength of the charcoal effect. Lower this slightly for a more pastel look.|
||Final Scene Hue Shift|Optional hue shift applied to the rendered scene. Useful when the `EffectStrength` parameter is lower.|
|<b>1. Charcoal</b>|Strength|Overall strength of the charcoal effect.|
||Grunge Mask|Custom mask texture used to break up the charcoal effect.|
||Grunge Mask Scale|Size of the grunge mask in meters.|
||Grunge Mask Strength|The overall strength of the grunge, very low values are usually enough for this.|
|<b>2. Charcoal Outline</b>|Strength|Overall strength of the charcoal outline (if enabled).|
||Color|The color of the charcoal outline.|
||Use Unique Color?|If enabled then the charcoal outline will use its own color (rather than that of the charcoal effect).|
|<b>3. Advanced</b>|Detail Lighting Cutoff|Optional cutoff vaule applied to the detail lighting mask. Lower values will result in harsher detail lighting.|
||Invert Grunge Mask?|Should the grunge mask be inverted?|
||Pressure Bands Count|Adds a banding effect to the final effect, useful for simulating pressure sensitive drawing.|
||Pressure Bands Range|Controls how harsh the banding effect is.|
||Maximum Thickness (Charcoal Outline)|The maximum thickness allowed for the charcoal outline.|
||Minimum Thickness (Charcoal Outline)|The minimum thickness allowed for the charcoal outline.|

## See Also

{% include sketchit/template_thumbs.html %}