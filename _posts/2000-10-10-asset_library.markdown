---
layout: post
title: "Asset Library Tools"
img: https://www.dropbox.com/s/pchwhaaryic7jne/asset_library.png?raw=1
description: A collection of tools based around creating a standardized asset library, with simple import/export from multiple programs.
tag: [Assets, Tools, Pipeline]
---

Asset Library is a series of pipeline tools I've created for my own personal projects.

The main goals of these are to maximize the efficiency of bringing asset types from many DCC Packages to the final game.

It's all a somewhat personal solution to my own project needs, and is constantly evolving, but since it's starting to morph into a tangible set of tools I thought writing a post on it could be interesting.

---

## Substance Designer

### Material Export

![Image](https://www.dropbox.com/s/3pht3ym28hzwvlb/material_editor.png?raw=1){: .center-image}

This is a tool used to automatically export a material and all variants from Substance Designer to the Asset Library. When the exporter is ran, all textures are re-exported, and the .material file is updated with any edited parameters.

### Material Refresh

![Image](https://www.dropbox.com/s/srujsjv4kfttc8g/designer_to_unreal.png?raw=1){: .center-image}

One of the nicest parts of the material pipeline is the "Import to Unreal Engine" sub-tool. Whevever this is ran, the current material is exported from Substance Designer, and reimported to Unreal with all of the new textures.

This means I no longer have to nagivate to the updated material and manually reimport all dependent textures. Instead it's a single button press.

### Material Import

This loads a .sbs file from a target exported material. Nothing too special. But can save a couple of mouse clicks.

---

## Unreal Engine

### Material Import

This takes the data for a material as exported from Substance Designer, and automatically imports it to Unreal Engine, along with the whole dependency stack (all referenced textures). 

It also creates a new Material Instance from a list of predefined Master Materials/Shaders available to the Asset Library, and sets all of the child parameters accordingly.

![Image](https://www.dropbox.com/s/tzy21d3emm1lsfs/unreal_import.png?raw=1){: .center-image}

### Geometry Import

This is tied to the above Asset Importer, and is responsible for importing the Geometry asset type, along with all of the rest of the dependencies (Textures, Materials, etc)

### Material Export

This tool will serialize all materials currently found inside the Unreal project to .material files, including their parameters, and textures relative to the asset library.

This is useful for tweaking materials in the editor, while still being able to export them out to the asset library for editing in other external DCC applications.

### Shader Exporter

This is a standalone tool which will export the metadata for unreal based shaders to a .shader file. This is useful for reading shader parameters in external programs, and building materials outside of Unreal.

---

## 3DS Max

### Geometry Exporter

This tool will export the currently opened 3DS Max scene to either a single FBX file, or a series of FBX files.

The exporter currently has two modes:

- Single Export: This will export the whole file to a single .fbx file if only a single sub-mesh is found

![Image](https://www.dropbox.com/s/u42chrl3qnle4im/single_export.png?raw=1){: .center-image}

- Multi Export: This will export a series of meshes from a single file. The exporter looks for all layers that start with "SM_" as this is used to denote child meshes.

![Image](https://www.dropbox.com/s/99yn5iujox3s7zk/multi_export.png?raw=1){: .center-image}

---

### TBC..

There are more tools, but at the moment they're all pretty specific use cases for my projects. I'm sure I'll add to this post more info on certain tools as they progress.