---
title: Retro Filters Pack
subtitle: Image Effects
description: ""

layout: page
image: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/banner.png?raw=true
menubar: menu_retro_filters_pack

store_name: retro_filters_pack
---

{% include carousel.html id="bit_depth_slider"
  img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/3bit.jpeg"
  img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/4bit.jpeg"
  img4="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/4bit.jpeg"
%}

<section id="overview"/>
## **Overview:**

This page provides a comprehensive guide to the various image effects included in the Retro Filters Pack. These effects are designed to help you recreate the visual style of classic games and retro or vintage hardware, enabling you to evoke nostalgia or create an artistic aesthetic in your projects. The image effects can be applied individually or combined in any way you see fit, giving you full control over the look of your scenes.

Each image effect comes with a set of adjustable parameters, allowing you to fine-tune the appearance to your liking. We will explore each effect in detail, explaining its purpose, how it works, and the parameters you can adjust. By the end of this guide, you will have a thorough understanding of how to use these image effects to achieve a wide range of retro-inspired visuals.

Remember that these effects can be applied in combined in various ways to create an even more unique and personalized look for your projects. Don't be afraid to experiment and find the perfect combination of effects that suits your needs.

---

<section id="bit_depth"/>
## **Bit Depth:**

Bit Depth redices the number of colors used in the final image, creating a simpler, more stylized look reminiscent of older games and graphics hardware.

Use this effect to evoke nostalgia or create an artistic aesthetic.

In the images below you can see the same scene rendered with 3 bits, 4 bits, and 8 bits respectively.

{% include image_slider.html id="bit_depth_slider" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/3bit.jpeg"  img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/default.jpeg" %}

|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|
|Bit Depth|Modifies the overall bit depth of the final image (e.g., 4-bit, 8-bit)|

---

<section id="gradient_mapping"/>
## **Gradient Mapping:**

Gradient Mapping replaces all of the colors in the image with colors from the provided gradient map texture.

It can be used to create unique color schemes, stylize the visuals, or simulate specific retro color palettes.

The provided color palette uses the colors of the original GameBoy color, which had a very limited color palette (only 4 colors could be shown on screen at once!)

Take a look at the image below for an example of what the gradient mapping looks like when enabled and disabled.

{% include image_slider.html id="gradient_mapping_slider" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/gradient_map_on.jpeg"  img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/gradient_map_off.jpeg" %}

|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|
|Texture|Specifies the gradient map texture to use. This texture should be 1 pixel high and a maximum of 256 pixels wide.|

---

<section id="pixelate"/>
## **Pixelate:**

Pixelate simplifies the image by reducing its resolution, creating a blocky, pixelated appearance.

This effect is useful for emulating the low-resolution graphics of retro games or creating a stylized, digital look.

{% include image_slider.html id="pixelate_slider" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/pixelate.jpeg" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/default.jpeg" %}

|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|
|Resolution Multiplier|Adjusts the strength of the pixelation. 1.0 represents the current screen resolution, while 0.0 results in a 1-pixel screen.|

---

<section id="saturation"/>
## **Saturation:**

Saturation adjusts the intensity of colors in the image.

By increasing or decreasing saturation, you can make the colors more vibrant or more muted.

This effect is useful for creating a specific mood or matching the color intensity to other visual elements.

Hint: Set the saturation to `0.0` for a grayscale / monochrome effect.

{% include image_slider.html id="saturation_slider" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/saturation_0.jpeg" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/default.jpeg" %}

|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|
|Strength|	Adjusts the overall saturation of the scene. 1.0 = maximum saturation, 0.0 = desaturated (grayscale)|

---

<section id="static"/>
## **Static:**

Static adds a layer of random animated noise to the image, simulating the appearance of an old analog TV signal or a noisy video connection. Use this effect to create an atmosphere of nostalgia or to add visual interest to your project.

Hint: The saturation of the static is also tied to the saturation of the scene, so for monochromatic scenes the static will also be monochromatic!

Check out the images below for examples of a varying level of static settings.

{% include image_slider.html id="static_slider" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/static_rgb.jpeg" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/default.jpeg" %}


|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|
|Strength|Adjusts the overall strength of the noise displayed on the screen. This typically only needs to be very low for subtle values (a value such as 0.1 usually suffices)|