# ultrasound-of-bats
## 1. Introducing

This Unity scene features a sample that demonstrates voice-controlled input to activate position-related spatial visual effects within an AR scene. Inspired by how bats detect their surroundings with their own sound.

## 2. Demo

- [ ]  video here

## 3. How it works

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c394a3b1-49d5-493e-98a9-df3037e184ca/185d3034-67f4-4e52-9cb8-808d459c81d3/Untitled.png)

This Unity scene features a sample that demonstrates voice-controlled input to activate position-related spatial visual effects within an AR scene. What it actually do is: get your voice as input, trigger a vfx everytime you make sound. And the vfx is a spatial vfx which needs mesh of your surroundings(we use ARMeshManager to get the mesh)

And the Unity scene consists of three parts: Settings, UI and Objects.

In Settings, we set our main light of scene with a Directional Light object. A Volume to add post-processing effect to our scene. AR Session and XR Origin is basic creating AR experience in Unity.

In UI, we got a Canvas called HoloKit UI Canvas and An EventSystem Obbect. Inside canvas there are four objects:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c394a3b1-49d5-493e-98a9-df3037e184ca/f7b6c644-ae98-4d85-9344-51a99e987bf3/Untitled.png)

First two are default UI for HoloKit usage, we won’t discuss them here. 

The “Mesh Button” controls On&Off of ARMeshManager feature, cause if you always keep this feature On, it will kill the performence of your phone. Here the button on your own hands, you can disable this feature when you got enough mesh information of your surroundings.

The”Mesh Detail Slider” is a slider used to control the level of detail in your mesh. A higher value means a more detailed mesh, resulting in a smoother and better match with your real environment visually.

In Scene:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c394a3b1-49d5-493e-98a9-df3037e184ca/8c99e813-f5de-4cdd-9196-ac49ed90f436/Untitled.png)

Mic Input detect all the voice input of your device, if the volume is beyond the pre-set value, it will trigger the event to make a vfx from your current position.

The BatVFXShaderController grab some parameters and pass them to our vfx. Our vfx is made with ShaderGraph, cause it’s a vfx related to current position, needs an awareness of time to create an gradual visual effect.

Finally, SceneManager provides some functions to connect our UI elements with our needs. UI itself is a button, slider or sth else with no real function in it. We create those functions and bind them to UI element. Such as a function controls the On&Off of ARMeshManager.

And hope you enjoy it!
