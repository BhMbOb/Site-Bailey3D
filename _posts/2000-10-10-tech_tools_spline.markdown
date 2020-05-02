---
layout: post
title: "Spline Tools"
img:  https://drive.google.com/uc?export=view&id=1GSv2FmnCMEfAXdscHIzCwqzGsX0SEhK_# Add image post (optional)
description: Some examples of how I've used spline tools within my work for procedural and dynamic asset creation.
tag: [Environment Art, Art, Lighting]
---
Splines are a great feature in most 3D packages for creating procedural and modular assets, and I've found that setting up assets in a way that splines can be utilized  helps to save a lot of time when laying out environments, not to mention the performance and memory benefits.

These spline systems were all created in Unreal through either Blueprints or C++, and require a bit of forward thinking in terms of which assets are used and how they're made.

The biggest benefit to using splines is that the amount of unique meshes is cut down significantly, most of the examples here use only two simple meshes each. 


When using meshes that aren't deforming it's also useful to use mesh instancing, this will mean that each instance of a unique mesh takes up only a single draw call (Making the assets more efficient than multiple unique meshes).

------

![Image](https://drive.google.com/uc?export=view&id=1jdNNlb7KgrZq--AYXUum9BJUR5j9Dnfa){: .center-image}

This rail-bed system uses two unique assets (Planks & Rail) to allow for easy modular placement of rails within an environment. The height and tangents of the spline can easily be tweaked to conform to the environment without need for many different track variations.

------

![Image](https://drive.google.com/uc?export=view&id=1JccX7pjQEnh6m0dsE_cUnZ9Qxtxuzjx9){: .center-image}

These follow a spline along a path which they're randomly placed, it allows for the books to easily be placed on surfaces (such as windows or bookshelves). Like the previous example, these use instanced meshes and some shader maths to give unique colours and titles, which can be extremely useful for environments like libraries where you can have upwards of 100k book meshes.

This is something I covered in another post but since it's also using splines I thought it'd be useful to include it here.

------

![Image](https://drive.google.com/uc?export=view&id=1uJBVsiD473HJOmE6_Q0yDbqicCz9zgtD){: .center-image}

This pipe spline uses a control spline to dynamically create spline meshes for easy creation of pipes.

The pipes themselves are made up of only 2 assets (Pipe Body & Connector), compared to dozens of variations for a typical spline system.

------

![Image](https://drive.google.com/uc?export=view&id=1JMxTsHQRc2-Bdy8MhmrB21d9mKmi-wBC){: .center-image}

The example above is similar to the rail-bed, except it's spawning instances of the top/bottom meshes stretched to each angle change, and filling the inside with wooden beams to create a dynamic fence.

Other things can be parametrized for systems like this one, such as the spacing of the inside pillars, pillar/rail thickness and height to give a unique look to the fencing.

![Image](https://drive.google.com/uc?export=view&id=1ShwRIOZCydtAHK-UkRwiqcAXIhXjqjDA){: .center-image}