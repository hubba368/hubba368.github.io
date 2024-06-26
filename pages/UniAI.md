---
layout: default
title: Super Fly Sprayer - Custom AI & Physics
type: Uni Project
featured: false
tags:
    - Unity
    - C#
    - AI
    - Physics
preface: |
    A set of pathfinding and physics implementations demonstrated inside  of a small proof-of-concept game, made within Unity.
images:
    - https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718897/uniAI2_rzpuok.png
    - https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718896/uniAI1_wtpdy5.png
bgImg: https://res.cloudinary.com/dwwy1fzms/image/upload/e_blur:500/v1718718896/uniAI1_wtpdy5.png
frontImg: https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718896/uniAI1_wtpdy5.png
class: UniAI
---

{% include pageButton.html buttonName="View On Github" url="https://github.com/hubba368/GameBehaviour-SuperFlySprayer" %}

For my undergraduate final year module 'Game Behaviour', we were tasked with implementing physics and AI components within a game setting. With this in mind, I created the game 'Super Fly Sprayer', a horde mode style game that was influenced by Super Smash Bros. The game features 2D Rigidbody physics along with AABB collision, and a robust A* pathfinding solution for the NPCs of the game.

We were tasked with implementing our systems to be independent of existing engine systems. As I was using Unity, this meant I had to create my own Rigidbody and Pathfinding classes. We did not however have to implement our own frame updating function.

##### Features
* Fully developed A* pathfinding system for NPCs, with editable nav graphs and debug path visiblity.
* Custom Rigidbody components, capable of movement and acted upon by various forces.
* Collisions handled by AABBs between static and non-static rigidbodies.