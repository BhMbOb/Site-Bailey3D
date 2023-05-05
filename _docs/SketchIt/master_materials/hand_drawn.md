---
title: Sketch-It
subtitle: Hand Drawn (Master Material)
description: ..

layout: page
image: https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/banner.png?raw=true
menubar: sketchit_menu

store_name: sketch_it

---
## **Hand Drawn:**

<img src="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Gifs/pencil.webp">

---

### **Template: Pencil:**
<section id="pencil"/>

{% include image_slider.html id="pencil_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pencil/off.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pencil/pencil.jpeg" percent=0.25 %}

### **Template: Vintage:**
<section id="vintage"/>

{% include image_slider.html id="vintage_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pencil/off.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pencil/vintage.jpeg" percent=0.25 %}


### **Template: Notepad:**
<section id="notepad"/>

{% include image_slider.html id="notepad_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pencil/off.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/pencil/notepad.jpeg" percent=0.25 %}

---

## **Parameters:**

|<b>Category</b>|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|:---|
|<b>0. Global</b>|Enable Detail Lighting?|Enables / disables the detail lighting.|
||Enable Detail Sketch?|Enables / disables the detail (secondary) sketch effect.|
||Enable Paper Effect?|Should the paper effect be applied to the background?|
||Background Color|Controls the color of the background (the paper color)|
|<b>1. Paper</b>|Mask Texture|Grayscale texture applied to the background to simulate a paper effect.|
||Scale|Scale in meters that the paper mask tiles.|
||Strength|Overall strength of the mask texture. Higher values will give a more crumpled paper texture.|
|<b>2. Sketch</b>|Strength|Overall strength of the main sketch.|
||Pencil Color|The color of the main sketch effect.|
|<b>3. Detail Sketch</b>|Use Unique Color?|Should the detail sketch use a different color to the main sketch?|
||Strength|Overall strength of the detail sketch.|
||Pencil Color (Detail)|The color of the detail sketch.|
|<b>4. Detail Lighting</b>|Effect Strength|Overall strength of the detail lighting effect.|
||Grunge Strength|Overall strength of the grunge mask applied to the detail lighting.|
||Color|The color of the detail lighting.|
||Cutoff|Cutoff value used to give harsher / softer edges to the detail lighting.|
||Mask Scale|Overall skale of the detail lighting grunge mask in meters.|
||Mask Texture|Mask texture used to apply a breakup grunge mask to the detail lighting.|
||Use Unique Color?|Should the detail lighting use a different color to the main sketch?|
|<b>5. Advanced</b>|Detail Lighting - Invert Mask?|If enabled then the grunge mask for the detail lighting is inverted.|
||Detail Sketch - Cutoff|Cutoff value applied to the detail sketch.|
||Detail Sketch - Maximum Thickness|Controls the maximum thickness range for the detail sketch.|
||Sketch - Maximum Thickness|Controls the maximum thickness range for the main sketch, lower will result in thinner line cutoffs.|
||Sketch - Minimum Thickness|Controls the minimum thickness range for the main sketch, higher will result in higher frequency detail being removed.|

---

<!--{% include carousel.html id="bit_depth_slider"
  img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Pencil/Vintage_Trove.jpeg?raw=true"
  img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Pencil/Notepad_Trove.jpeg?raw=true"
  img3="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Pencil/Notepad_Vice.jpeg?raw=true"
  img4="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Pencil/Pencil_Rift.jpeg?raw=true"
  img5="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Pencil/Pencil_Trove.jpeg?raw=true"
  img6="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Pencil/Pencil_Vice.jpeg?raw=true"
  img7="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Pencil/Vintage_Vice.jpeg?raw=true"
%}-->

## See Also

{% include sketchit/template_thumbs.html %}