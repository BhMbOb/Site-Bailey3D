---
title: Juniper
subtitle: Documentation (WIP)
layout: page
hero_image: https://github.com/Bailey3D-Website/2021/blob/main/projects/Juniper/juniper.png?raw=true
image: https://github.com/Bailey3D-Website/2021/blob/main/projects/Juniper/juniper.png?raw=true
description: ""
menubar: menu_juniper
---
## Juniper
<section id="juniper"/>

<img src="https://raw.githubusercontent.com/Juniper3d/Juniper/main/Resources/Icons/Standard/app_default.png" width="100"/>

Juniper is a unified scripting framework - for use across a variety of applications which include an embedded Python interpreter.

The framework is designed to be easily configurable and extendible, and supports Plugin and Module systems.

You can find the source code on GitHub here.

<a href="https://github.com/Bailey3D/Juniper" target="_blank">https://github.com/Bailey3D/Juniper</a>

## Program Support
<section id="program_support"/>

Modules for all currently supported host programs can be found in `Source/Hosts/{host_name}`
Currently this includes:

- 3DS Max (Tested on 2023)
- Blender (Tested on 2.80)
- Houdini (Tested on 2021 w/ Python 3)
- Substance Designer (Tested on 2021.1.0)
- Substance Painter (Tested on 2021.1.1)
- Unreal Engine (Tested on 5.0)

Generally Juniper should work on all versions of these applications - so long as they are using Python 3.

## Requirements
<section id="requirements"/>

There should be no requirements to use Juniper - so long as at least one supported program is installed.
Simply run the installer from `Binaries/Juniper/juniper_install.bat`

*(An internet connection is needed to download various external Python packages - this is done via Pip)*