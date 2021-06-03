---
layout: post
title: "Shader - Iridescense"
img: https://www.dropbox.com/s/z5x9nyt6cp2i06s/thumb.png?raw=1 # Add image post (optional)
description: Shader simulating an iridescent surface, similar to that seen in Oil and Beetle shells.
tag: [Environment Art, Art, Lighting]
---
Surface shader created in Unreal Engine, simulating the specular lighting effect commonly seen on iridescent surfaces (Beetles, Oil, etc.), with an additional light-wrap effect for visual flair.

![Image](https://www.dropbox.com/s/79nq4xkenul1k2k/materials.png?raw=1){: .center-image}

------

In this project I aimed to create a minimal dependency Iridescent effect shader.

Iridescent surfaces are found on lots of different surfaces in nature (Eg, Oil, Beetle Shells, Titanium)

The shader uses a custom lightwrap based on a world space 3D noise, and doesn't depend on any light positions. This has the advantage of working on virtually any surface, but the disadvantage of not being physically correct.

------

## Quick Breakdown

__Input Values:__
- Iridescent Tint: The base tint of the iridescent effect
- Range: The overall colour range the iridescent gradient extends over (1.0 = full RGB range, 0.5 = base tint -> base tint + 0.5 hue)
- Scale: The overall scale of the 3D noise used with the lightwrap function
- Fresnel Strength: An additional colour bump when viewed at grazing angles


The Noise map is a low resolution 3D Perlin Noise texture, which is combined with a custom lightwrap UV function to simulate the iridescent effect when moving around the surface.

![Image](https://www.dropbox.com/s/laayahsdc03y6gy/iridescent_gif.gif?raw=1){: .center-image}