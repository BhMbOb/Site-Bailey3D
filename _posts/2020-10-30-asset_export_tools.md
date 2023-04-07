---
layout: post
title: Asset Import / Export Tools
description: A series of tools for automating and standardising the export and import process for common DCC packages.
hero_image: https://github.com/Bailey3D-Website/2021/blob/main/projects/Exporters/thumb.png?raw=true
image: https://github.com/Bailey3D-Website/2021/blob/main/projects/Exporters/thumb.png?raw=true
hero_height: is-large
hero_darken: true
tags: [Python, Assets, Tools, Pipeline]
#series: example_blog_series
---
These are a series of tools written to automate the general import and export pipeline of different asset types from various DCC packages, into a final game engine (In this case Unreal).

The main aim with these tools is to take various processes which by default take a series of clicks (and a bit of careful thought) and condense them down to 1 or 2 button clicks, and removing the thinking step all together.

The tools are were all built around an asset pipeline I'm using for my personal projects, so portability is very limited.
However all of the source is available <a href="https://github.com/Juniper3d/Plugin-AssetLibrary" target="_blank">here<a> for you to pick through as you please.

The codebase is also all built around my <a href="https://github.com/Juniper3d/Juniper" target="_blank">Juniper Tools Framework<a> which aims to further standardize the tools pipeline across multiple DCC packages. Feel free to take a look at that.


## Material Exporter <small><i>(Substance Designer)</i></small>

Tool used to auto-export the currently opened Material Graph, and all child graphs.

What happens when the tool is ran: <br>
__1 - Texture Exporting:__ All textures are updated and exported <br>
__2 - Material Metadata:__ A `{mat_name}.material` metadata file is generated (I'll cover this in the unreal export) <br>
__3 - Unreal Reimport:__ If Unreal is open, the textures are re-imported (à la live link) <br>
__4 - SBSAR Export:__ A `{mat_name}.SBSAR` file automatically is generated/updated (for use in Substance Painter) <br>

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Exporters/material_editor.png?raw=true)


## Material Refresh <small><i>(Substance Designer)</i></small>

Automatically imports the current Material into Unreal. Automatically taking care of things such as, Texture Properties, Material Generation, Asset Dependency Importing.

Changing the material import proces to: <br>
__1 - Re-import:__ Material is imported to Unreal from a single button click, no more navigating and picking files, it's all automated.

From the previously cumbersom process of: <br>
~~__1 - Open Unreal:__~~ Must swap to the program before starting <br>
~~__2 - Find in Content Browser:__~~_ Hand find and select all source assets to reimport. Multiple times if the files are in different source folders. <br>
~~__3 - Pick Import Properties:__~~ For new assets things such as texture properties (compression, type, etc) were previously hand done. <br>
~~__4 - Build Material:__~~ For new materials the material would need manually creating.

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Exporters/designer_to_unreal.png?raw=true)


## Material Importer <small><i>(Substance Designer)</i></small>

Used for quick loading of materials. Gathers all valid '.material' files found in the asset library, and adds them to a single combo box.

Removes the task of navigating through all folders to find materials - this can save a lot of time depending on how big the asset library is.


## Geometry Exporter <small><i>(3DS Max)</i></small>

Exports a currently opened '.max' file as FBX - along with associated materials, using a couple of methods.

This is what happens when the exporter is ran:

__1a - Single Export:__ Used when a single sub-mesh is found in the Max file <br>
![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Exporters/single_export.png?raw=true) <br>
__1b - Multi Export:__ Exports a series of meshes from the file. Layers beginning with 'SM_' denote unique meshes to be exported. <br>
![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Exporters/multi_export.png?raw=true) <br>
__2 - Material Processing:__ Material IDs are baked down to ensure only used materials are exported (0..NUM) <br>
__3 - Metadata Export:__ A '.geometry' file is generated per-mesh containing metadata on the asset (such as material paths, and source file data).


## Material Importer <small><i>(Unreal)</i></small>

![Image](https://github.com/Bailey3D-Website/2021/blob/main/projects/Exporters/unreal_import.png?raw=true)

As mentioned previously, this can either be automatic (on export), or manual - this will cover the manual portion. <br>
There's also a batch mode which whill import all materials. Although this needs more work to ensure only "dirty" assets are updated.

This takes the path of a '.material' file, and automatically imports it to unreal, along with some other things. Depending on how many assets your library has, this can save anywhere from minutes, to hours of work.

This is what happens when import is ran: <br>
__1 - Create Unreal Material:__ A new material instance is created (on first import) <br>
__2 - Set Shader:__ A parent master material is applied - if set in the host application (see 'Shader Exporter' below) <br>
__3 - Import Textures:__ All texture dependencies are imported (this means no hand importing all wanted textures) <br>
__4 - Set Parameters:__ All texture parameters are set from the '.material' file


## Geometry Importer <small><i>(Unreal)</i></small>

Similar to the Material Importer, this imports a geometry asset from a '.geometry' file. It will also import the material and texture dependencies if they don't already exist.

<br>

## Shader Exporter <small><i>(Unreal)</i></small>

A smaller, but useful tool, which will loop over all Master Materials in the project, and serialize them to a `{shader_name}.shader` file.
Useful as all existing '.shader' files are then exposed to external Import/Export tools. Meaning things such as parent master materials can be edited per-material outside of Unreal.

This file is '.json' based, and stores things such as:
 - Parameters (Ie, Vector, Float, Bool, etc.)
 - Properties (Statically compiled properties - Ie, "Parent Shader", "Two Sided?")

<br>

## Material Exporter <small><i>(Unreal)</i></small>

This tool serializes <i>all</i> materials inside the currently opened unreal project out to '.material' files.<br>
This adds the option for essentially editing materials outside of the host Unreal instance. Where they can be auto-imported back into the engine. It's a bit of a workaround for the fact everything in unreal is a binary '.uasset' file.

Again, there's more that could be done here to combat the two-way material editing issues which may come from editing inside Unreal, and another host process.

Exported data includes:
- All Material Parameters (Ie, float, vector, etc)
- All Texture Parameters (with paths relative to the project)