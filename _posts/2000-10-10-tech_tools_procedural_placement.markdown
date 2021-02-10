---
layout: post
title: "Procedural Asset Creation"
img: https://drive.google.com/uc?export=view&id=1mAeN8qpLeqQiVgt2BVyGek4BIzNVO1-f # Add image post (optional)
description: Some examples of tools created for procedural placement and generation of assets - includes randomness, modularity, proceduralism ...
tag: [Environment Art, Art, Lighting]
---

These are a series of tools in unreal focused around procedural creation and placement of geometry and environmental details. 
They were all created using a mix of Blueprint and C++.

The main benefit to interactive procedural tools like this is the time cost saving it creates, taking processes which would typically be full tasks and turning them into simple-to-do processes.

------

![Image](https://drive.google.com/uc?export=view&id=1OjGdXKF8vshJGc6RcV4akFOWIUE2gSSF){: .center-image}

This rail-bed system uses two unique assets (Planks & Rail) to allow for easy modular placement of rails within an environment. The height and tangents of the spline can easily be tweaked to conform to the environment without need for many different track variations.

------

![Image](https://drive.google.com/uc?export=view&id=1PSDJGoJ6gbbU-aCB2YtT3k_VscYSbKQ6){: .center-image}

These follow a spline along a path which they're randomly placed, it allows for the books to easily be placed on surfaces (such as windows or bookshelves). Like the previous example, these use instanced meshes and some shader maths to give unique colours and titles, which can be extremely useful for environments like libraries where you can have upwards of 100k book meshes.

------

![Image](https://drive.google.com/uc?export=view&id=16MlrCf6lkIDp7rogGSXy05ltYygWxc4W){: .center-image}

This pipe spline uses a control spline to dynamically create spline meshes for easy creation of pipes.

The pipes themselves are made up of only 2 assets (Pipe Body & Connector), compared to dozens of variations for a typical spline system.

------

![Image](https://drive.google.com/uc?export=view&id=1ka6PYor62_ojeZPS6Sa696SENFjtlidJ){: .center-image}

Procedural and modular bookcase system. Again all unique meshes are instanced, and a single shader is used for all pieces. The system uses 8 unique bookcase pieces along with the shelf and door, meaning the whole system uses 10 draw calls. System is parameterized with settings such as: RowsCount, ColumsCount and bUseDrawers. This system helped to save a lot of time and avoid art fatigue within the library scene along with improving the scenes overall performance.

![Image](https://drive.google.com/uc?export=view&id=1gFGZYYooGn8XjJjLPgESCRoTh_Ijetqe){: .center-image}