---
layout: post
title: "Shader - Microfibre Surfaces"
img: https://www.dropbox.com/s/qlinrzximmdmp9t/thumb.png?raw=1 # Add image post (optional)
description: Breakdown of a surface shader for simulating microfibre materials, such as Moss and Cloth.
tag: [Environment Art, Art, Lighting]
---

This was a shader designer to simulate the Microfiber effect found on materials such as Moss, Fur and other surfaces in nature.

The main difference between a Microfiber surface and a regular one is that Microfiber surfaces are built up of thousands of tiny fibers, which each have the ability to both occlude each other and self occlude themselves.
In the real world this would result in the tips of each fiber catching more light than the roots, and this is what the shader aims to simulate.

---

![Image](https://www.dropbox.com/s/suxi5rdn9zfrdzt/moss_turnaround.gif?raw=1){: .center-image}


The effect is entirely dependent on the surfaces normal maps, and is ran through a dot product agains the camera reflection vector along with world space pixel normals. This way we will get a lighter albedo on the tips, and darker deeper in the roots. The use of a reflection vector rather than the raw camera vector adds a subtle lightwrap which breaks up the effect slightly.

The effect also contains some custom controls for altering the specular strength, simulating specular occlusion, helping to give a more realistic final look.

You can see the base, un-altered, map in the gif below.

![Image](https://www.dropbox.com/s/2lg5cpdixibkoa3/moss_renders.png?raw=1){: .center-image}

---

### Parameters

This is a breakdown of the input parameters to the fuzz function:

- __Input Material Attributes__, this is specific to unreal and just packs the previously calculated surface properties into a single struct

- __Albedo Darken Amount__, The overall darkness strength in the core of the material (roots)

- __Albedo Lighten Amount__, For an additional bump in the albedo strength when viewing tips

- __Specular Occlusion Strength__, the overall strength of the specular occlusion when viewing the roots

- __Lightwrap Specular Strength__, an extra specular adjustment value when viewing areas considered light-wrapped

- __Effect Strength__, overall strength of the microfiber effect on the whole surface, this can take in an extra map, uniform value, or vertex colours

- __Subsurface Exponent__, used to simulate less porous surfaces behind the moss (Eg, wood/dirt)