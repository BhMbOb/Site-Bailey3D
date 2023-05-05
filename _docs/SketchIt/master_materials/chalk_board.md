---
title: Sketch-It
subtitle: Chalk Board (Master Material)
description: ..

layout: page
image: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/banner.png?raw=true
menubar: sketchit_menu

store_name: sketch_it

---
## **Chalk Board:**

<img src="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Gifs/chalkboard.webp">

---

### **Template: Chalkboard:**
<section id="chalk_board"/>

{% include image_slider.html id="chalkboard_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/chalk/off.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/chalk/chalkboard.jpeg" percent=0.25 %}

### **Template: Chalk Drawing:**
<section id="chalk_drawing"/>

{% include image_slider.html id="chalk_drawing_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/chalk/off.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/SketchIt/renders/Comparisons/chalk/chalkdrawing.jpeg" percent=0.25 %}

---

## **Parameters:**

|<b>Category</b>|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|:---|
|<b>0. Global</b>|Use Base Color for Chalk?|If this is enabled then the base color of the scene is used for the chalk color.|
||Enable Detail Chalk?|If enabled this adds a secondary detail chalk to the post process.|
||Background Color|The color tint for the background of the scene (I.e. the color of the chalkboard).|
|<b>1. Detail Lighting</b>|Grunge Mask Scale|Adjusts the size of the grunge mask texture, in meters.|
||Grunge Mask Strength|The overall 0..1 strength of the grunge effect applied to detail lighting.|
||Grunge Mask Texture|The texture mask used for the grunge calculation.|
||Strength|The overall strength of the detail lighting effect on the scene.|
||Use Unique Color?|If True then a unique chalk color is used for the detail lighting.|
|<b>2. Chalk</b>|Color|The base color of the chalk effect.|
||Detail Strength|The overall strength of the detail chalk (if enabled).|
||Strength|The overall strength of the main chalk effect.|
||Use Unique Color?|If True then a unique colour will be used for the chalk effect.|
|<b>3. Advanced</b>|Cutoff (Detail)|Cutoff value applied to the detail chalk mask. This can be used to give softer/harder edges.|
||Maximum Thickness (Detail)|Controls the maximum thickness fraction on the detail chalk.|
||Maximum Thickness|Controls the maximum thickness fraction on the base chalk.|
||Minimum Thickness|Controls the minimum thickness fraction on the base chalk. Increasing this will result in thinner areas being removed.|
||Cutoff (Detail Lighting)|Cutoff value applied to the detail lighting. This can be used to give softer/harder edges to the detail lighting.|

<!-----

{% include carousel.html id="bit_depth_slider"
  img1="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Chalk/Chalkboard_Trove.jpeg?raw=true"
  img2="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Chalk/ChalkboardVice.jpeg?raw=true"
  img3="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Chalk/ChalkDrawing_Trove.jpeg?raw=true"
  img4="https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/renders/Chalk/ChalkDrawing_Vice.jpeg?raw=true"
%}-->

## See Also

{% include sketchit/template_thumbs.html %}