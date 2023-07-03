# Interactive Cannon Scene

## Overview
The code for this project is currently private, but the [final results are shown below.](#final-product)

## Object Generation
Every object in the scene is created from scratch (without the use of any graphics software). There are sphere, torus, cylinder, and general surface generators. To generate arbitrary surfaces, a surface of revolution generator takes a list of coordinates (for a curve) as input and rotates this curve around an axis to generate the 3-D shape.

## Scene Graph
To make the scene interactive, a hierarchical scene graph is used. This allows different coordinate systems to be used, along with having transformations of objects affect their children objects. For example, all components of the cannon are children of the cannon base node, so each component of the cannon (the entire cannon) moves together when the user inputs transformations to the base (such as moving or turning). Another example is when the elevation screw of the cannon is turned: this leads to the barrel tilting up or down. 

Traversal of the scene graph is used to render the scene, and a model view matrix stack is utilized to store the parenting transformations along the traversal. This allows a parent node's transformation to be passed down to its children.

## Lighting
This project implements shaders for Gouraud, Phong, and Hemisphere lighting models. The main lighting in use is hemisphere lighting. Additionally, Rim lighting is implemented when cel shading (cartoon shading) is active.

## Physics Simulation
Physics simulation is implemented for cannonball collisions against both static and moving objects. The user shoots cannonballs which can bounce off the ground, collide with both static spheres and other moving/movable spheres (such as other cannonballs), and collide with arbitrary cylinders (or disks). Hitboxes can be constructed by placing an "invisible" cylinder inside any object.

## Additional Effects
Additional visual effects were implemented. These include shadows (optional 64-sample high resolution soft shadows), cel shading (cartoon shading), and object outlining.

## Final Product
<!---
![normal300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/3abd3536-8384-4cf2-b729-73866aed543b) 
![cel300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/23ec75c6-869b-42bd-a7a2-37b6b736de11)
![extreme300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/423235e8-43fe-406f-af86-28641c04e07c)

![no-texture300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/20157938-10c1-4f14-a83b-63ee3bb842fd)
![notexture-cel300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/20237aca-a184-435b-8714-8851b3d723bb)
![extreme-notexture300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/6f2d30ab-5fe8-49c5-be70-8e775cb1767f)
-->
### Quick Pictures

Realistic Shading             |  No Texture Realistic 
:-------------------------:|:-------------------------:
![normal300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/1a187d1e-ab7a-4930-93c8-11ff44bb8fdd) | ![no-texture300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/d4779fd0-06a9-40ce-9bdb-b7731b2aafa2)

Cel Shading            |  No Texture Cel 
:-------------------------:|:-------------------------:
![cel300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/d187b42f-eeea-49b0-a2db-4bfec329de66) | ![notexture-cel300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/7d84fca8-e6fe-4e84-854f-9b8ba85111a2)

"Extreme" Cel Shading             |  No Texture "Extreme" Cel
:-------------------------:|:-------------------------:
![extreme300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/52229011-32f9-4860-a01b-c70d4038b761) | ![extreme-notexture300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/cc4794ef-2a9f-4d93-a1cb-8cfac46e2e57)

<!---
Realistic Shading             |  Cel Shading
:-------------------------:|:-------------------------:
![normal300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/3abd3536-8384-4cf2-b729-73866aed543b) | ![cel300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/23ec75c6-869b-42bd-a7a2-37b6b736de11)

No Texture Realistic             |  No Texture Cel 
:-------------------------:|:-------------------------:
![no-texture300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/20157938-10c1-4f14-a83b-63ee3bb842fd) | ![notexture-cel300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/20237aca-a184-435b-8714-8851b3d723bb)

Extreme Cel Shading             |  No Texture Extreme Cel
:-------------------------:|:-------------------------:
![extreme300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/423235e8-43fe-406f-af86-28641c04e07c) | ![extreme-notexture300](https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/6f2d30ab-5fe8-49c5-be70-8e775cb1767f)
-->

<!--- COMMENT
<p align="center">
  <img alt="Light" src="https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/3abd3536-8384-4cf2-b729-73866aed543b)https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/3abd3536-8384-4cf2-b729-73866aed543b" width="48%">
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="Dark" src="https://github.com/russell-nick/Interactive-Cannon-Scene/assets/84354901/23ec75c6-869b-42bd-a7a2-37b6b736de11" width="48%">
</p>
-->

Additional Pictures: (insert link later or upload folder to the repo)

### Videos
The following are videos demonstrating the different lighting effects and the physics simulation. Unfortunately, it seems there is a black bar at the bottom of my recordings.

Lighting effects (YouTube link):
[![Watch the video](https://img.youtube.com/vi/U4ONSY6sLms/maxresdefault.jpg)](https://www.youtube.com/watch?v=U4ONSY6sLms)
Lighting effects in space (YouTube link):
[![Watch the video](https://img.youtube.com/vi/51u1DCG7h-s/maxresdefault.jpg)](https://www.youtube.com/watch?v=51u1DCG7h-s)

Physics (YouTube link):
[![Watch the video](https://img.youtube.com/vi/Cp11kxhSuNE/maxresdefault.jpg)](https://www.youtube.com/watch?v=Cp11kxhSuNE)

