---
layout: post
title: "Shader - Volumetric Clouds"
img: https://drive.google.com/uc?export=view&id=1EU1EWRCN0E4Cv4UfRgE0S06F4EZK-stQ # Add image post (optional)
description: System created in Unreal Engine, using HLSL and Raymarching techniques to create volumetric clouds.
tag: [Environment Art, Art, Lighting]
---
 Software & Tools Used: Substance Designer, Unreal Engine, HLSL


This is project I worked on to create a drag-and-drop cloud system within Unreal. It uses 3D Noise textures and volumetric raymarching to render a volume shader to simulate clouds. The system covers a few different areas, such as:

- Directional lighting
- Wind movement
- Controllable density, coverage, lighting and steps count
- Time-of-day

The majority of the shader was calculated in HLSL, but pieced together in the material editor.

![Image](https://drive.google.com/uc?export=view&id=1NXEuv7MVT3zv1vBA6wETz3b0kA81qF1_){: .center-image}

3D Texture Sampling

This system uses 'pseudo-volume textures'  to render the 3D volume textures, which is essentially a low fidelity 3D texture baked out into a flipbook texture. Since Unreal has no 3D texturing support built in, I created a HLSL function to simulate a TextureSample3D 

{% gist 008fa85282f1d5bcd348ee770c84dc90 %}

The raymarching code is quite specific to this project, so I won't post it here due to lack of context. But it is packed into a material function in Unreal for further control, and takes inputs such as: UVW_Scale, WindVector, Steps, StepsMultiplier and more.

Directional Lighting

The clouds are lit by a single directional source vector which is passed in as a global value, allowing for fully dynamic sun lighting. This is actually tied to the scenes directional light source to allow for dynamic time-of-day updates. Extinction tinting was also something that helped a lot in bumping the final colour.

![Image](https://drive.google.com/uc?export=view&id=1Zjphvxo4bhM_sNVoPGTYjbPHOrVyBd1a){: .center-image}

Blueprint System

The whole system is packed into a Blueprint Actor to allow for easy setup within any scene. This can be tied into things such as Wind, Weather and Lighting systems to allow for dynamic time and weather systems.

You can see some of the main parameters for the clouds below.

![Image](https://drive.google.com/uc?export=view&id=1EaZCKPdpa6AhAaG8H-95q7NsWeWxYq81){: .center-image}

 Links/Resources: 

- https://shaderbits.com/blog/creating-volumetric-ray-marcher
- https://www.alanzucconi.com/2016/07/01/raymarching/