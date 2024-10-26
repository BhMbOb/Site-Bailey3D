---
layout: post
title: Iridescense Shader
description: Shader simulating an iridescent surface, similar to that seen in Oil and Beetle shells.
hero_image: https://github.com/Bailey3D-Website/2021/blob/main/projects/Iridescent/thumb.png?raw=true
image: https://github.com/Bailey3D-Website/2021/blob/main/projects/Iridescent/thumb.png?raw=true
hero_height: is-large
hero_darken: true
tags: [Shaders, Lighting, Art, Unreal]
portfolio: iridescent_shader
#series: example_blog_series
---
This pack contains presets for a variety of different Iridescent based effects.

The material is built up from a base material function, which can be easily plugged into existing materials (to add the effect wherever you like)

The effect is ready to use out of the box. It contains one texture which can be swapped out as desired to give different effects.

This pack is for sale [here on the Unreal marketplace](https://www.fab.com/listings/4e908bd7-2fae-4d5e-a913-12a014fad980).

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Iridescent/thumb.png?raw=true){: .center-image}

------

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Iridescent/img_01.png?raw=true){: .center-image}
![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Iridescent/img_02.png?raw=true){: .center-image}
![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Iridescent/img_03.png?raw=true){: .center-image}
![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Iridescent/img_04.png?raw=true){: .center-image}

------


## Parameters

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Iridescent/parameters.png?raw=true){: .center-image}

| Parameter | Description |
| --- | --- |
| <b>Material Attributes</b> | Input material attributes (the base surface to apply the effect to) |
|||
| <b>Input Metallic</b> | Metallic for the iridescent effect. |
| <b>Input Roughness</b> | Roughness for the iridescent effect. |
| <b>Surface Uniformity</b> | How flat the surface should be treated. |
| <b>Input Specular</b> | Specular for the iridescent effect.  |
| <b>Effect Strength</b> | Overall strength of the iridescent effect. |
| <b>Body Strength</b> | OVerall strength of the iridescent distortion in the body of the surface. |
| <b>Exponent</b> | Tighten / loosen the fresnel effect. |
| <b>Frequency</b> | How high/low frequency the noise is for distortion. |
|||
| <b>Iridescent Tint</b> | Base tint for the iridescent effect. |
| <b>Emissive Injection Strength</b> | Optional multiplier for when injection the iridescent coluors into the emissive buffer. |
| <b>Saturation</b> | Saturation boost for the iridescent colours. |
|||
| <b>Pixel Normals</b> | World space normals. Used for surface distortion. Defaults to PixelNormalWS. (Note: World space - not tangent space) |
| <b>Pixel Normal Strength</b> | Strength of the pixel normals. This is useful for lessening the effect a normal map will have on the surface. |
|||
| <b>Mask</b> | Optional mask for the iridescent effect. You can use this for vertex painting / texture masking. |


## Limitations

- True Iridescent lighting is not possible to recreate in Unreal without per-pixel lighting. Instead, this implementation uses a mix of camera-relative hue shifting and a custom lightwrap effect.
