# Becoming Bats

This project features a sample that demonstrates using voice as input to activate position-related spatial visual effects within an AR scene. Inspired by how bats detect their surroundings with their own sound.

![mp4](https://github.com/holoi/becoming-bats/assets/52849063/12c26f09-5b94-4536-b05c-587b3a060ce2)

## How does it work

In this project, we take your voice as input, trigger a visual effect every time you make sound(the volume of sound should be above a pre-set value). And the visual effect is a spatial visual effect which needs mesh information of your surroundings(we use Meshing feature from AR Foundation to get the mesh information).

Our Unity scene consists of three parts: “Settings”, “UI” and “Sound and Effect”:
<img src="https://github.com/holoi/becoming-bats/assets/52849063/6c878ae0-4bfa-4c92-9596-cce0c32ab0f6" width="640px">

## Settings
<img src="https://github.com/holoi/becoming-bats/assets/52849063/6a2d46ca-ff6c-4b37-aa74-989c06731709" width="640px">

In Settings, we set our main light of scene with a Directional Light object. A Volume to add post-processing effect to our scene. AR Session and XR Origin is basic creating AR experience in Unity.

## UI
<img src="https://github.com/holoi/becoming-bats/assets/52849063/0b17344d-a706-4161-bdc4-ff9b9bf7c30e" width="640px">

In UI, we got a Canvas called HoloKit UI Canvas and An EventSystem Obbect. Inside canvas there are four objects:

<img src="https://github.com/holoi/becoming-bats/assets/52849063/353ba83f-8f8d-49e3-916e-cc65486daecf" width="640px">

First two are default UI for HoloKit usage, we won’t discuss them here. 

The “Mesh Button” object is a button to control On&Off of ARMeshManager feature. if you always keep this feature On, meshing feature will kill the performance of your phone. Here the button on your own hands, you can disable this feature when you got enough mesh information of your surroundings.

The”Mesh Detail Slider” is a slider object used to control the level of detail of your mesh. A higher value means a more detailed mesh, resulting in a smoother and better matching between meshing information and real environment

## Sound and Effect

<img src="https://github.com/holoi/becoming-bats/assets/52849063/592e00ce-2815-4ada-b962-d35954ad2cd5" width="640px">

In “Sound and Effect”, “Mic Input” object detects all the voice input of your device, if the volume is beyond the pre-set value, it will trigger a event, which in this case is to make a visual effect from your current position.

The “BatVFXShaderController” objects grab some parameters and pass them to our visual effect. Our visual effect is made with ShaderGraph, relates to current position, needs an awareness of current position and trigger time to create a time-varying visual effect.

Finally, “SceneManager” object provides some functions for our UI elements. UI itself is a button, slider or sth else with no function in it. We create those functions and bind them to UI elements. Such as a function controls the On&Off of ARMeshManager.

# System requirements
I created and tested this project in Unity2022.3.8f1. I recommend you open this project with Unity2022.3.8f1.

I build and tested this project to device with Xcode 14.2.

As for mobile device, I used iPhone 12Pro.

- *This project uses Meshing feature of AR Foundation, which needs a mobile device with Lidar camera, please make sure your device has Lidar camera

# How to try it

1. Clone the project, open with Unity.
2. Open BatSound→Scene.
   <img src="https://github.com/holoi/becoming-bats/assets/52849063/e3816144-be3c-41b0-a60a-cf38f68b8ec5" width="640px">
4. Build this scene to an Xcode project.
5. Open Xcode, open your Xcode project, build to your mobile device.

# License
