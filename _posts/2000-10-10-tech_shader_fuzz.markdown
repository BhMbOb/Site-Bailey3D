---
layout: post
title: "Shader - Microfibre Surfaces"
img: https://drive.google.com/uc?export=view&id=1JavYvTuMGmo0aDWB6yTVEns_wxWxLE8_ # Add image post (optional)
description: Breakdown of a surface shader for simulating microfibre materials, such as Moss and Cloth.
tag: [Environment Art, Art, Lighting]
---
Microfibre Surfaces such as moss and cloth differ to regular surfaces due to the fact the surface is built up of thousands of tiny fibres which have the ability to occlude other fibres and also self occlude. In a real world surface this would result in the tips of each fibre catching more light than the roots, which is what this shader aims to simulate.

![Image](https://drive.google.com/uc?export=view&id=1K8DlUweBoXj7YIjIvIrbhkqhHPV_g1-w){: .center-image}

In the real world when a viewer is looking head on to the surface they should be seeing deep into the occluded root area of the fibre, compared to a grazing angle where we should only see the well lit tips.

This is calculated using the dot product of the surface normals and camera position, and outputs a grayscale mask denoting the tips in white and core in black.

This mixed with some rim-lighting and colour ramping gives a nice effect similar to a real world microfibre surface.

![Image](https://drive.google.com/uc?export=view&id=1fHoXJ-3fjj3vpuhc5GRPJJAZGJMYesu6){: .center-image}

Other than the main part of this shader, there are some other areas such as subsurface colour tweaking, albedo and specular calculation, which all combine together to give a more realistic looking surface, along with a set of optional parameters:

- Normals influence - overall strength the surface normals have on the effect
- Effect multiplier - overall effect of the microfibre calculation on the surface
- Inner / outer albedo multiplier - multiplier for the tips and core of the diffuse
- Inner / outer specular exponent - exponent used for tips and core specular calculation
- Subsurface exponent - used to simulate less porous back surfaces such as wood and dirt

![Image](https://drive.google.com/uc?export=view&id=1cuHkhj7btwfwt_HFiEXeN23mtvlh_Qx6){: .center-image}