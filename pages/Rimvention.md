---
layout: default
title: Rimvention
type: Solo Project
featured: true
tags:
    - In Progress
    - XML
    - C#
    - Unity
preface: |
    A Rimworld mod inspired by the Invention skill from Runescape, which centers around deconstructing items into arbitrary parts that can later be recombined to produce special effects.
startImg:
images:

bgImg:
frontImg:
class: rimvention
---

#### In Progress - 90% Complete

{% include pageButton.html buttonName="View On Github" url="https://github.com/hubba368/Rimvention" %}

As a follow-up to my previous mod, Immersive-ish Research, Rimvention is a substantial mod that adds a completely new gameplay mechanic adjacent to the built-in ones. As I had gained experience in creating mods for Rimworld previously, I spent much of the development time for Rimvention renovating old code and keeping scope creep in check.

As expected, I used Harmony to once again allow for high compatibility with other user-created mods, and to allow for patching of existing functions for my needs.

##### Current Features
* Deconstruct any item into 'Parts' rudimentary items that are chosen and randomly obtained based upon the stats of the item. Deconstructing a wooden club will give different parts to deconstructing a plasma rifle.
* Recombine Parts into 'Imbues' items that can be slotted into a wearable belt that apply special effects to the wearer, positive or negative.


##### Changes from Immersive-ish Research

###### **Removal of XPath patching**
One major flaw of the previous mod was the usage of XPath, which I had used to link the use of in-game items as part of research project costs. This led to a number of instances of negative feedback from users, and significantly increased development time and was extremely unsustainable for later renovation.
* To get around this, Parts are selected and generated dynamically, based on the in-game statistics of the item being deconstructed. Not only does this reduce the amount of effort needed, but also makes it completely compatible with any modded items that maybe used.

###### **Custom Bill Crafting System**
A personal major flaw in Rimworld modding, and a flaw from Immersive-ish Research is the ability to create 'Bills' (essentially crafting) that have customised outputs. For Immersive-ish Research, I created a derived Bill System that followed the actual Bill system it was connected to. This led to a number of bugs and savefile bloating, and a large amount of XML for having to create every single possible crafting output. 
* Essentially, Rimworld crafting is a WYSIWYG system, you are guaranteed to get the output. For Rimvention however, I wanted to make the output have a sense of randomness, much like how the Invention skill works in Runescape.
* Instead of creating an unnecessary derived implementation, I used a seperate crafting queue that would follow the order of the actual crafting queue through Harmony patching.
* I would then be capable of accessing the completed craft and changing what is created before it actually spawns in-game.

###### **Dynamic Tables & Draggable UI Elements**
Initially developed in Immersive-ish Research was a utility class for creating lists of selectable items, something that isn't possible in vanilla Rimworld. However, it wasn't very extendable and only worked for the UI elements it was made for.
* Now redesigned to be much more generic and reusable for any UI windows, with a number of extra features.

###### **Extra Features**
* Can draw dynamically sized text lists.
* Can draw image tables of N width & height, alongside single images that have less overhead to draw.
* Draggable UI elements between seperate UI contexts with transfer of information if needed.




