---
layout: post
title: "Shader - Ocean Waves"
img: https://www.dropbox.com/s/vzvp31ghfqeqls5/thumb.gif?raw=1 # Add image post (optional)
description: Ocean shader system utilizing Gerstner waves for wave simulation and foam calculation.
tag: [Environment Art, Art, Lighting]

---
### Gerstner Waves

The main way that the ocean shader simulates the wave movement is using something called a 'Gerstner Wave'. Unlike a sine wave which is typically only used to displace the surface on the z-axis, Gerstner waves offer a more physically accurate simulation which  also takes into account the x and y offset. The gif below shows how a vertex moves using Gerstner waves, compacting vertices more closely at the peaks, and less at the troths. The GPU Gems post linked at the bottom will help in understanding the maths and implementation a bit more.

![Image](https://www.dropbox.com/s/td3ha3q5tcj89gn/wireframe_render.gif?raw=1){: .center-image}

Since this uses a physical calculation for the waves, it means that the input parameters also use real-world values. Some of the most notable ones being: Amplitude, Steepness Phase and Direction. Similarly, since this uses a wave it means that multiple waves of different amplitude/wavelength can be combined by simply adding them together, to give a more detailed ouput. In this I used a total of 16 wave formations (8 being low frequency, 8 being high frequency)

![Image](https://www.dropbox.com/s/m1ytipf8oo0udws/subsurface.jpg?raw=1){: .center-image}

### Detailing Normals

Although the waves themselves do a large part in the realism of the shader, without additional surface detailing they end up looking quite flat. To fix this I used 3 sets of normals at different frequencies (High for main body detailing, Medium for subtle waves and Low for lower frequency ripples and surface disturbance).


Normals alone tend to give a rather static and tiling look to the surface, so phasing between the textures in two states (similar to a flow map) also helps in avoiding this.

Although the Gerstner calculations themselves do a huge part in making the shader feel realistic, without any additional surface detailing you'll find that they still end up looking extremely flat.

![Image](https://www.dropbox.com/s/e1ntjrsi5ic8f2d/normals_comparison.gif?raw=1){: .center-image}

### Sea Foam
Foam is an area I've seen typically overlooked in some shaders, but found that even a subtle amount gives a nice effect. Unlike waves I couldn't find a way of physically simulating this in realtime, so the way it is calculated uses some data from the Gerstner wave to create an 'Amplitude Mask'.


The foam mask was created in Substance Designer, and is a 2 channel mask of Worley noise distorted into a fluid like mask. It uses the phasing method mentioned before to give a nice fluid effect.

![Image](https://www.dropbox.com/s/hfgnq407hfo971z/foam_render.gif?raw=1){: .center-image}

![Image](https://www.dropbox.com/s/b2017ok81rbo79p/foam_noise.jpg?raw=1){: .center-image}
