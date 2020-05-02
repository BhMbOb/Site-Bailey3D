---
layout: post
title: "Shader - Iridescense"
img: https://drive.google.com/uc?export=view&id=1UuWWTNQHHzaLGBqukGXgtzit7zrOb2HW # Add image post (optional)
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
tag: [Environment Art, Art, Lighting]
---
Surface shader created in Unreal Engine, simulating the specular lighting effect commonly seen on iridescent surfaces (Beetles, Oil, etc.), with an additional light-wrap effect for visual flair.

![Image](https://drive.google.com/uc?export=view&id=1UPD_pxPcF1GneYpu9Hjk4p8h5mJKxzJ0){: .center-image}

------

I originally worked on a similar shader in a team a few months back, but more recently decided to rework it to be more realistic looking and suitable for in game use along with more optimized. 


The shader simulates the iridescent effect found on many different surfaces throughout nature (such as oil , beetle shells and more). It tends to be a more difficult effect to simulate with deferred rendering, since the amount of lighting information available is minimal. Instead this shader uses 1 light sample (in this case the sun) to calculate the specular reflection that iridescence relies on.

------

## Quick Breakdown


The effect is applied to a full material using material attributes and packed into a material function, making it super easy to use and set up.

- Required Inputs - include: Iridescent Roughness Normals Influence and UV Scale.

- Optional Inputs - include: Directional Light Vector Hue Shift Strength and Colour Ramp Texture.


Lighting and UV distortion are the two main areas that give the effect.

- Lighting - is calculated pretty simply using surface normals and directional light vector (NDotL)

- UV Distortion - is the main thing giving the effect and is using a grayscale noise texture in -1 to 1 range combined with a Reflection Vector to give a distortion effect that changes depending on the view angle in relation to the lighting.  (See below)
- Hue Shift - is effected by the cameras position relative to the directional light vector. It gives a nice lightwrap effect that effects the hue more at extreme angles than at direct angles. The maths for this is pretty simple you can see the code below and an example of the mask:

{% gist 9faef956ecade207a7fed1d4d5020a70 %}

![Image](https://drive.google.com/uc?export=view&id=15h6zTFsgzTHx-h5qtJQR9vmkRxHCgTLt){: .center-image}
