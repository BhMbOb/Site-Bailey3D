---
layout: post
title: "Shader - Iridescense"
img: https://github.com/Bailey3D-Website/2020/blob/main/projects/Iridescent%20Shader/thumb.png?raw=true # Add image post (optional)
description: Shader simulating an iridescent surface, similar to that seen in Oil and Beetle shells.
tag: [Environment Art, Art, Lighting]
---

This is a shader function which can be added to any PBR surface to add an interactive iridescent effect (with colours changing depending on view angle).

It was designed to be as minimal as possible, meaning it can be applied to pretty much any surface. This has the advantage of being plug and play, and works within a regular deferred pass, but the disadvantage ob being only a simulation meaning we're not calculating physically accurate diffraction.

![Image](https://github.com/Bailey3D-Website/2020/blob/main/projects/Iridescent%20Shader/materials.png?raw=true){: .center-image}

------

## Parameters

The effect is fully parameterized so we can add it to any surface, the parameters are listed below:

- __Scale:__ This controls the overall scale of the 3D noise used for the light wrapping and breakup affect

- __Colour Range:__ A [0..1] value which is used for the maximum hue shift allowed by the effect. 1.0 will result in a full colour spectrum (starting at the input tint), whereas 0.0 will result in only the tint being used.

- __Tint:__ The starting tint for the colour of the iridescent effect (Note, this also controls the overall saturation and lightness of the colours)

- __Fresnel Effect Strength:__ When viewed from grazing angles the iridescent hue shift is always bumped up to max. This controls how visible the fresnel effect is.

- __Noise Texture 3D:__ A 3D Texture sample used for the lightwrap and breakup effect. This defaults to a low-res 3D perlin noise texture, which works for most cases.

------

![Image](https://github.com/Bailey3D-Website/2020/blob/main/projects/Iridescent%20Shader/iridescent_gif.gif?raw=true){: .center-image}