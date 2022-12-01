---
layout: post
title: "HLSL Shader Library In Unreal"
img: https://github.com/Bailey3D-Website/2021/blob/main/projects/HLSL%20Library/thumb.png?raw=true
description: Python based tool used to automate generation of .USF files from external HLSL Libraries
tag: [Tech, Shaders, Tools, Python]
---

As someone who has experience with using HLSL for shader coding, the lack of HLSL support in Unreal has always frustrated me.

This Python library aims to add some rudimentary support for using external HLSL libraries from within Unreal Material Graphs, using a mix of techniques listed below.


### What's the Aim?

The aim with this is to be able to use an external library containing individual '.HLSL' files inside of unreal, using `#include` from inside a custom node.
But before we can do that there are a few hurdles that need to be addressed:

__1__ - Unreal doesn't support custom Shader #includes by default <br>
__2__ - All shaders must be inside the current project's "project/shaders" directory to be usable <br>
__3__ - All shader files must be in '.USF' or '.USH' format - '.HLSL' is not allowed <br>
__4__ - Unreal 'Custom' nodes require all functions to be within some sort of scope <br>

---

### Supporting External Shader Includes in Unreal:

The first issue comes with the fact that Unreal by default doesn't enable #including "project/shaders" directory inside of custom nodes - trying to include them will cause a compiler error.

To fix this we'll need to add in a search path for the shaders. I've done this in a plugin since that's where all of my shaders are stored, but this will work just as well inside of your `ProjectName.h` and `ProjectName.cpp` files.

This is relatively simple, and just requires us to add an extra Shader Source Directory Mapping to the project.
You can see how I've set this up in the code below. In my case there is some extra code for reading the path from the Registry, but that can be omitted if you're using a static path.

<script src="https://gist.github.com/Bailey3D/4786196223ed5e136239958d81c370dc.js"></script>
<script src="https://gist.github.com/Bailey3D/2aa821a85a313c02a3060137aa8dd26f.js"></script>

All being well, this should allow you to #include '.USH' and '.USF' files in your Project/Plugin Shaders directory.


### Creating a Library 'Watchdog'

The second hurdle comes from the fact that all shaders must be inside of the "project/shaders" directory. While it's not technically true that they won't work in an external directory, the fact that all files have to be '.USH' or '.USF' files means that integrating it into a raw '.HLSL' library will get messy fast.

For this reason, I've created a python library to create a folder watcher on our external 'pure' HLSL library, which watches for any and all file changes, and copies the files over to the project's Shaders library.

Since this isn't a tutorial, I'll post links to the source files at the end of this section if you'd like to take a look at how it's done. But the general overview is:

__- On Engine Startup:__ Sets off a script which watches for changes to files in the external library <br>
__- On Change Detected:__ Copies all files from the external library to the project's Shaders directory <br>
__- Convert to USF:__ covered in the next section, but this is required since .HLSL cannot be used in Unreal <br>

Example source files can be found here: <a href="https://github.com/Bailey3D/Juniper/blob/main/lib/python/juniper/framework/types/folder_watcher.py" target="_blank">folder_watcher.py</a> <b>+</b> 
<a href="https://github.com/Bailey3D/Juniper-AssetLibrary/blob/main/scripts/ue4/startup/1/shader_source_watcher.py" target="_blank">shader_source_watcher.py</a> <b>+</b> 
<a href="https://github.com/Bailey3D/Juniper-AssetLibrary/blob/main/lib/python/asset_library/programs/ue4/asset_management/shaders.py" target="_blank">shaders.py</a>


### Converting .HLSL to .USF

A bit of a continuation of the previous point. But since Unreal doesn't support '.HLSL' files, we'll need to convert all references to '.HLSL' over to '.USH'

This is done as part of the conversion scripts, it pretty much has two steps: <br>
__1 - Change File Type:__ Replace the '.hlsl' file extension with '.ush' <br>
__2 - Replace in Files:__ Convert all '.hlsl' #includes to '.ush' includes <br>

### Creating a Shader Library / Function Scoping

The last issue is that, everything inside of a 'Custom' node in unreal must be inside some sort of scope. The trouble comes down to how this is accessed. If you were to just treat it like a regular '.HLSL' file by creating them in the scope of the main file, unreal will throw a compiler error.

I get around this by storing everything within a 'struct'. It can be as simple as creating a struct with everything inside and then instancing the struct. But that's still a bit fiddly.

Instead we can use the HLSL preprocessor to automatically create the instance of the struct. It's a bit of a hack, but works nicely once you're used to setting it up.

To do this I have a file ' defines.hlsl' which contains a macro called 'container'. A container is essentially treated like a namespace or singleton (albeit a bit more limited):

<script src="https://gist.github.com/Bailey3D/482b687fb6a4588adb6abae328526f0a.js"></script>

And here's an example of how a container is populated, and how to call the generated container:

<script src="https://gist.github.com/Bailey3D/f6dc98c141012f90a19bdaa576828bc6.js"></script>

<script src="https://gist.github.com/Bailey3D/ef9ee1c353decc5e6f449b565ca3ed32.js"></script>

---

And that's it - this has allowed me to essentially #include and use data from inside of an external HLSL library directly from Unreal. It's a bit convoluted, but is better than coding directly inside of the Custom nodes, or having to create an actual engine side shader.

I do hope Unreal gets some better shader coding support in the future, I'd love to be able to use HLSL more than just through a custom node and without all these hacks. But until then, I'll be using this method.
