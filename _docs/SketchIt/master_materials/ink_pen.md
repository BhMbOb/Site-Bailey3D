---
title: Sketch-It
subtitle: Ink Pen (Master Material)
description: ..

layout: page
image: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/banner.png?raw=true
menubar: sketchit_menu

store_name: sketch_it

---
## **Ink Pen:**

<img src="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Gifs/pen.webp">

---

### **Template: Byro:**
<section id="byro"/>

{% include image_slider.html id="byro_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pen/off.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pen/byro.jpeg" percent=0.25 %}

### **Template: Ink Pen:**
<section id="ink"/>

{% include image_slider.html id="ink_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pen/off.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pen/ink.jpeg" percent=0.25 %}

### **Template: Gel Pen:**
<section id="gel"/>

{% include image_slider.html id="gel_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pen/off.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pen/gel.jpeg" percent=0.25 %}

---

## **Parameters:**

<!--{% include carousel.html id="bit_depth_slider"
  img1="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pen/InkPen_Trove.jpeg?raw=true"
  img2="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pen/ByroPen_Trove.jpeg?raw=true"
  img3="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pen/ByroPen_Vice.jpeg?raw=true"
  img4="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pen/GelPen_Trove.jpeg?raw=true"
  img5="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pen/GelPen_Vice.jpeg?raw=true"
  img6="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pen/InkPen_Rift.jpeg?raw=true"
  img7="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Pen/InkPen_Vice.jpeg?raw=true"
%}-->

|<b>Category</b>|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|:---|
|<b>0. Global</b>|Enable Light Pen?|Should the light pen effect be enabled?|
||Enable Paper Effect?|Should the background paper effect be enabled?|
||Background Color|Controls the color of the background (paper).|
|<b>1. Paper</b>|Mask Texture|Texture applied to the background to simulate a paper effect.|
||Scale|Overall scale of the paper mask in meters.|
||Strength|Overall strength of the paper effect. Higher values will result in a more crumpled paper effect.|
|<b>2. Pen</b>|Strength|The overall strength of the main pen drawing.|
||Color|The color of the pen.|
|<b>3. Pen (Light)</b>|Strength|The overall strength of the light pen drawing.|
||Use Unique Color?|Should a unique color be used for the light pen?|
||Color|The color of the light pen drawings. It is recommended to not make this too different to the main pen color.|
|<b>4. Advanced</b>|Light Pen - Cutoff|Cutoff value applied to the light pen effect, use this to give harsher/softer edges.|
||Light Pen - Maximum Thickness|Controls the maximum fraction for the light pen effect.|
||Sketch - Maximum Thickness|Controls the maximum thickness fraction for the main pen effect, higher values will result in thicker a pen effect.|
||Sketch - Minimum Thickness|Controls the minimum thickness fraction for the main pen effect, lower values will result in higher frequency detail being ignored.|

## See Also

{% include sketchit/template_thumbs.html %}