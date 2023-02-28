---
layout: post
title: "SketchIt - Chalk Board (Master Material)"
img: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/banner.png?raw=true
description: ""
tag: [Store, Shaders, Post Process, Documentation]
---
[< Back to Docs](../../docs)

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
