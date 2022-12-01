---
layout: post
title: "Ocean Shader"
img: https://github.com/Bailey3D-Website/2020/blob/main/projects/Gerstner%20Waves/thumb.gif?raw=true # Add image post (optional)
description: Ocean shader system utilizing Gerstner waves for wave simulation and foam calculation.
tag: [Environment Art, Art, Lighting]

---

This was a project aiming to create a realistic looking ocean shader with sea foam, waves and realistic looking lighting.
The shader code was primarily coded in HLSL, and pieced together in Unreal for the final renders.

The way that ocean rendering is typically simulated in 3d rendering is using __Gerstner Waves__.
Unlike sine waves which will only displace the surface in the up axis (z), Gerstner Waves offer a physically accurate simulation of how individual waves actually flow, by also offsetting the other two axis.

You can see in the gif below how the vertices in the water plane move, with them getting more compact closer to the peaks, and less in the troths.

![Image](https://github.com/Bailey3D-Website/2020/blob/main/projects/Gerstner%20Waves/bailey-martin-ezgif-com-optimize.gif?raw=true){: .center-image}

---

## Parameters (Single Gerstner Wave)

| Name | Description |
| --- | --- |
| <b>Amplitude</b> | The overall height of the wave (in Centimeters in this case) |
| <b>Steepness</b> | Controls the "sharpness" of the wave |
| <b>Phase</b> | Overall speed of the Gerstner Wave |
|||
| <b>Direction</b> | Direction vector for the flow of the wave (2 component to avoid expensive sin/cos calls for each function) |
| <b>Scale</b> | Additional multiplier for the final wave to scale up/down from a single parameter |

## Parameters (Wave Set)

Additionally since it's a wave we can combine multiple functions together, so I created a second function (creatively called) __GerstnerWaves__, which has a couple of extra inputs:

| Name | Description |
| --- | --- |
| <b>Waves Count</b> | Overall number of wave layers in the gerstner wave. Each new wave is double the frequency which results in a more finer amount of detail as the loops progress. |
| <b>Uniformity</b> | Where a value of 1.0 will result in all waves moving in the same direction, while lower to 0.0 will result in each layer going in a direction further away than the previous. This is good to alter how random the surface ends up looking. |

---

### Scattering

On top of the other effects the shader includes a simulation of light scattering, while staying fully opaque.
It uses a single directional light source to simulate the light scatter when viewing parallel to the suns vector.

![Image](https://github.com/Bailey3D-Website/2020/blob/main/projects/Gerstner%20Waves/bailey-martin-unnamed.jpg?raw=true){: .center-image}

---

### Sea Foam
Foam is an area that's typically overlooked in some shaders, but found that even a subtle amount gives a nice effect. Unlike waves I couldn't find a way of physically simulating this in realtime, so the way it is calculated uses some data from the Gerstner wave to create an 'Amplitude Mask'.


The foam mask was created in Substance Designer, and is a 2 channel mask of Worley noise distorted into a fluid like mask. It uses the a texture phasing method (described below) to give a nice fluid effect.

![Image](https://github.com/Bailey3D-Website/2020/blob/main/projects/Gerstner%20Waves/bailey-martin-asasd.gif?raw=true){: .center-image}

![Image](https://github.com/Bailey3D-Website/2020/blob/main/projects/Gerstner%20Waves/bailey-martin-ezgif-com-resize22.jpg?raw=true){: .center-image}

---

### Detailing Normals

Although the waves themselves do a large part in the realism of the shader, without additional surface detailing they end up looking quite flat. To fix this I used 3 sets of normals at different frequencies (High for main body detailing, Medium for subtle waves and Low for lower frequency ripples and surface disturbance).

Normals alone tend to give a rather static and tiling look to the surface, so phasing between the textures in two states (similar to a flow map) also helps in avoiding this.

Although the Gerstner calculations themselves do a huge part in making the shader feel realistic, without any additional surface detailing you'll find that they still end up looking extremely flat.

![Image](https://github.com/Bailey3D-Website/2020/blob/main/projects/Gerstner%20Waves/bailey-martin-a809f0-b4ef25b74a3a42e78bf648c2352db3ae-mv2.gif?raw=true){: .center-image}
