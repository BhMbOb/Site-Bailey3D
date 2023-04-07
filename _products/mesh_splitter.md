---
title: Mesh Splitter
description: >
  Merge Selection is a tool for simply merging all objects currently selected.
layout: product
image: https://github.com/Bailey3D-Website/2021/blob/main/packages/MeshSplitter/featured.jpg?raw=true
store_name: mesh_splitter
tags: [3DS Max, Tools]

carousels:
  - images: 
    - image: https://github.com/Bailey3D-Website/2021/blob/main/packages/MeshSplitter/gallery_main.jpg?raw=true
    - image: https://github.com/Bailey3D-Website/2021/blob/main/packages/MeshSplitter/gallery_elements.jpg?raw=true
    - image: https://github.com/Bailey3D-Website/2021/blob/main/packages/MeshSplitter/gallery_facecol.jpg?raw=true
    - image: https://github.com/Bailey3D-Website/2021/blob/main/packages/MeshSplitter/gallery_sg.jpg?raw=true
    - image: https://github.com/Bailey3D-Website/2021/blob/main/packages/MeshSplitter/gallery_matid.jpg?raw=true

---
### **Overview:**

These are a series of scripts used to split meshes in various different ways. Useful for processing meshes ready for importing to other packages, or simply splitting them up into individual parts.

{% include carousel.html height="56.25" unit="%" duration="99999" number="1" show_indicators=false %}

- <i><b>Split To Elements:</b></i> This splits all sub-elements in the users selection to unique meshes.
- <i><b>Split by Face Colour:</b></i> This script splits all selected meshes depending on the colours of the faces.
- <i><b>Split By Smoothing Group:</b></i> Splits all selected meshes into unique meshes from the smoothing groups of all faces.
- <i><b>Split By Material ID:</b></i> Splits the meshes into unique meshes from the given face material IDs.

### **Installing:**

Unzip the file to any desired location on your hard drive
In the 3DS Max menus, go to `Scripting -> Run Script` and find the `install.py` script (in the root folder for the tool).

### **Running the Scripts (GUI):**

To run the scripts in GUI mode, in 3DS max go to `Scripting -> Run Script` and find the `mesh_splitter_gui.ms` script (in the root folder for the tool).
This will launch a separate tool with interfaces for all 4 scripts. Just click the one you want and that's it!

### **Assigning Hotkeys:**

Macros are generated for quick running of all available scripts, including the GUI.
To assign a hotkey, in 3DS Max go to `Customize -> Hotkey Editor` and choose the category `FreeLime`. From there you should see macros for:

- Mesh Splitter (GUI)
- Split By Face Color
- Split By Material ID
- Split By Smoothing Group

### **Supported 3DS Max Versions:**

This script has been tested on 3DS Max 2022+, but should work on all versions from 2017 onward.
If you have any issues running the script, feel free to reach out and I'll do my best to assist.

### **Release Notes:**

Added a free demo version of the script.