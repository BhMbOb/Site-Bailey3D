---
layout: post
title: Volumetric Clouds
description: System created in Unreal Engine, using HLSL and Raymarching techniques to create volumetric clouds.
hero_image: https://github.com/Bailey3D-Website/2020/blob/main/projects/Volumetric%20Clouds/thumb.jpg?raw=true
image: https://github.com/Bailey3D-Website/2020/blob/main/projects/Volumetric%20Clouds/thumb.jpg?raw=true
hero_height: is-large
hero_darken: true
tags: [Shader, Lighting, Art]
#series: example_blog_series
---
Software & Tools Used: Substance Designer, Unreal Engine, HLSL


This is project I worked on to create a drag-and-drop cloud system within Unreal. It uses 3D Noise textures and volumetric raymarching to render a volume shader to simulate clouds. The system covers a few different areas, such as:

- Directional lighting
- Wind movement
- Controllable density, coverage, lighting and steps count
- Time-of-day

The majority of the shader was calculated in HLSL, but pieced together in the material editor.

![Image](https://github.com/Bailey3D-Website/2020/blob/main/projects/Volumetric%20Clouds/thumb.jpg?raw=true){: .center-image}

![Image](https://github.com/Bailey3D-Website/2020/blob/main/projects/Volumetric%20Clouds/bailey-martin-volumeclouds-render-01.jpg?raw=true){: .center-image}

3D Texture Sampling

This system uses 'pseudo-volume textures'  to render the 3D volume textures, which is essentially a low fidelity 3D texture baked out into a flipbook texture. Since Unreal has no 3D texturing support built in, I created a HLSL function to simulate a TextureSample3D 

<script src="https://gist.github.com/Bailey3D/008fa85282f1d5bcd348ee770c84dc90.js"></script>

The raymarching code is quite specific to this project, so I won't post it here due to lack of context. But it is packed into a material function in Unreal for further control, and takes inputs such as: UVW_Scale, WindVector, Steps, StepsMultiplier and more.

Directional Lighting

The clouds are lit by a single directional source vector which is passed in as a global value, allowing for fully dynamic sun lighting. This is actually tied to the scenes directional light source to allow for dynamic time-of-day updates. Extinction tinting was also something that helped a lot in bumping the final colour.

![Image](https://github.com/Bailey3D-Website/2020/blob/main/projects/Volumetric%20Clouds/bailey-martin-volumeclouds-render-02.jpg?raw=true){: .center-image}

Blueprint System

The whole system is packed into a Blueprint Actor to allow for easy setup within any scene. This can be tied into things such as Wind, Weather and Lighting systems to allow for dynamic time and weather systems.

You can see some of the main parameters for the clouds below.

![Image](https://github.com/Bailey3D-Website/2020/blob/main/projects/Volumetric%20Clouds/bailey-martin-ezgif-com-resize.jpg?raw=true){: .center-image}

 Links/Resources:

- https://shaderbits.com/blog/creating-volumetric-ray-marcher
- https://www.alanzucconi.com/2016/07/01/raymarching/