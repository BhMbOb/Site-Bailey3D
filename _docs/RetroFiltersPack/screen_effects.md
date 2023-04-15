---
title: Retro Filters Pack
subtitle: Screen Effects
description: ""

layout: page
image: https://github.com/Bailey3D-Website/2021/blob/main/packages/SketchIt/banner.png?raw=true
menubar: menu_retro_filters_pack

store_name: retro_filters_pack
---
## **Overview:**
<section id="overview"/>

This page provides a detailed overview of the various screen effects included in the Retro Filters Pack. These effects are designed to help you recreate the visual characteristics of classic displays and retro hardware, such as CRT monitors and LED screens. By applying these effects, you can achieve an authentic retro look in your projects or create an artistic aesthetic inspired by vintage hardware.

Each screen effect comes with a set of adjustable parameters, allowing you to fine-tune the appearance to your liking. We will look at each effect in detail, explaining its purpose, how it works, and the parameters you can adjust. By the end of this guide, you should have a better understanding of how to use these screen effects to achieve a wide range of retro-inspired visuals.

Remember that these effects can be applied individually or combined with the image effects provided in the pack to create a unique and personalized look for your projects. Don't be afraid to experiment and find the perfect combination of effects that suits your needs.

---

## **CRT Distortion:**
<section id="crt_distortion"/>

CRT Distortion emulates the curvature and distortion found on classic CRT monitors. This effect helps to create a more authentic retro look, as it mimics the way images were displayed on older screens.

{% include image_slider.html id="crt_distortion_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ScreenEffects/crt_distort_medium.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ScreenEffects/default.jpeg" %}

|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|
|Intensity|Adjusts the overall intensity of the screen curvature.|
|Softness|Modifies the curvature's softness, affecting the smoothness of the curve on the screen.|

---

## **LED Pixels:**
<section id="led_pixels"/>

LED Pixels simulates the appearance of individual pixels on an LED screen, including color bleed and brightness. This effect can be used to recreate the look of retro displays or to create a stylized pixel art aesthetic.

{% include image_slider.html id="led_pixels_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ScreenEffects/led_bleed.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ScreenEffects/default.jpeg" %}

|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|
|Pixel Mask Strength|Determines the strength of the alpha mask cutout for the pixel. Lower values result in more light bleed, while higher values produce a sharper cutout.|
|Pixel Bleed Strength|Controls the extent to which neighboring pixels bleed into the current pixel. A value of 0.0 will display only the current pixel (e.g., green), while a value of 1.0 will result in neighboring pixels blending into it, creating a more mixed color.|
|Pixel Brightness|Alters the overall brightness of the pixel, with higher values producing a more vivid appearance.|
|Pixel Texture|Specifies the texture used for drawing individual pixels. The R/G/B masks determine the visibility of the respective pixels, while the Alpha channel is used as the mask to control the shape of the pixel.|
|Enable LED Color Bleed?|If set to True, color bleed is enabled. Disable this option if you're not using the effect to save on shader instructions.|

---

## **Interlacing:**
<section id="interlacing"/>

Interlacing simulates the appearance of horizontal scanlines commonly found on older CRT and analog displays. This effect adds a sense of motion and flicker, which can make the visuals feel more dynamic and engaging.

Please note that interlacing is a subtle effect and has been increased for the example below.

{% include image_slider.html id="interlacing_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ScreenEffects/interlacing.webp" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ScreenEffects/default.jpeg" %}

|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|
|Frame Rate|Specifies the simulated refresh rate when using the interlacing effect.|
|Strength|Determines the overall strength of the interlacing effect. Low values are typically sufficient (e.g., 0.1).|

---

## **Glitch:**
<section id="glitch"/>

The Glitch effect simulates the visual distortions typically observed on old VHS players. This effect offers a range of customizable parameters for greater control and flexibility.

{% include image_slider.html id="glitch_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ScreenEffects/glitch.webp" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ImageEffects/default.jpeg" %}

|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|
|Phase|Adjusts the overall speed of the glitch effect, enabling faster or slower distortions.|
|Noise Phase|	Modifies the overall speed of the scrolling glitchy noise, adding dynamic movement to the effect.|
|Noise Strength|Determines the intensity of the noise, with lower values resulting in subtler vertical glitching.|
|Noise Frequency|Alters the size of the vertical noise, where lower values produce smoother noise patterns.|
|Offset Speed|Controls the speed of the vertical panning effect, allowing for faster or slower shifts.|

---

## **Vignette:**
<section id="vignette"/>

The Vignette effect enhances your screen by adding a subtle, darkened border around the edges, drawing attention to the center of the image.

If used along with other screen effects (such as the CRT curvature) then this effect will map directly to the altered screen (as opposed to the entire screen)

<!--Note: Make sure the aspect ratio is set in `height` else we'll mess up the presentation of the crt effect-->
{% include image_slider.html id="vignette_slider" img1="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ScreenEffects/vignette_high.jpeg" img2="https://raw.githubusercontent.com/Bailey3D-Website/2021/main/packages/RetroFiltersPack/Images/ScreenEffects/vignette_off.jpeg" %}

|<b>Parameter Name</b>|<b>Parameter Description</b>|
|:---|:---|
|Size|Adjusts the size of the vignette relative to the screen, with 1.0 being equal to the screen size. Higher values expand the vignette beyond the screen edges.|
|Softness|CModifies the smoothness of the vignette mask, allowing for a more gradual or abrupt transition at the border.|
|Strength|Determines the overall intensity of the vignette effect, controlling its prominence on the screen.|