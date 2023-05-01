---
layout: post
title: Spline Tools
description: Some examples of how I've used spline tools within my work for procedural and dynamic asset creation.
hero_image: https://github.com/Bailey3D-Website/2019/blob/main/projects/Spline%20Tools/bailey-martin-a809f0-c0ef469af24a443a8553696429c38242-mv2.gif?raw=true
image: https://github.com/Bailey3D-Website/2019/blob/main/projects/Spline%20Tools/bailey-martin-a809f0-c0ef469af24a443a8553696429c38242-mv2.gif?raw=true
hero_height: is-large
hero_darken: true
tags: [Environment Art, Assets, Tools, Pipeline, Blueprints, Unreal]
#series: example_blog_series
---
Splines are a great feature in most 3D packages for creating procedural and modular assets, and I've found that setting up assets in a way that splines can be utilized  helps to save a lot of time when laying out environments, not to mention the performance and memory benefits.

These spline systems were all created in Unreal through either Blueprints or C++, and require a bit of forward thinking in terms of which assets are used and how they're made.

The biggest benefit to using splines is that the amount of unique meshes is cut down significantly, most of the examples here use only two simple meshes each. 

When using meshes that aren't deforming it's also useful to use mesh instancing, this will mean that each instance of a unique mesh takes up only a single draw call (Making the assets more efficient than multiple unique meshes).

------

![Image](https://github.com/Bailey3D-Website/2019/blob/main/projects/Spline%20Tools/bailey-martin-a809f0-c0ef469af24a443a8553696429c38242-mv2.gif?raw=true){: .center-image}

This rail-bed system uses two unique assets (Planks & Rail) to allow for easy modular placement of rails within an environment. The height and tangents of the spline can easily be tweaked to conform to the environment without need for many different track variations.

------

![Image](https://github.com/Bailey3D-Website/2019/blob/main/projects/Spline%20Tools/thumb.gif?raw=true){: .center-image}

These follow a spline along a path which they're randomly placed, it allows for the books to easily be placed on surfaces (such as windows or bookshelves). Like the previous example, these use instanced meshes and some shader maths to give unique colours and titles, which can be extremely useful for environments like libraries where you can have upwards of 100k book meshes.

This is something I covered in another post but since it's also using splines I thought it'd be useful to include it here.

------

![Image](https://github.com/Bailey3D-Website/2019/blob/main/projects/Spline%20Tools/bailey-martin-a809f0-61f6f37fe755463f89c1c1182d9904d7-mv2.gif?raw=true){: .center-image}

This pipe spline uses a control spline to dynamically create spline meshes for easy creation of pipes.

The pipes themselves are made up of only 2 assets (Pipe Body & Connector), compared to dozens of variations for a typical spline system.