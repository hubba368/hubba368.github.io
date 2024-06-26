---
layout: default
title: Immersive-ish Research
type: Solo Project
featured: true
tags:
    - XML
    - C#
    - Unity
preface: |
    Developed in combination of C# and XML, Immersive-ish Research was designed as a complete overhaul of the original game's research mechanic, adding a new level of immersion and difficulty to the game. 
images:
    - https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718861/IM1_h5hpfd.png
    - https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718862/IM2_d7awn1.png
    - https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718860/IM4_z20md0.png
bgImg: https://res.cloudinary.com/dwwy1fzms/image/upload/e_blur:500/v1718718861/IM1_h5hpfd.png
frontImg: https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718861/IM1_h5hpfd.png
class: rimworld
---

{% include pageButton.html buttonName="View On Github" url="https://github.com/hubba368/RimWorldImmersiveResearch" %}
{% include pageButton.html buttonName="View On Steam Workshop" url="https://steamcommunity.com/sharedfiles/filedetails/?id=1732571153" %}

This was a substantial project to develop, as I had to spend a lot of time understanding an already existing codebase, and to also make sure that I adhered to it in my own project. 

I made usage of the Harmony library to alter the functionality of the original codebase at runtime, and I also used XPath to modify existing XML schema that Rimworld uses to store various things, such as buildings and characters.

To adhere to an acceptable level of mod compatibility with other created mods, I used every effort to limit the usage of Harmony and XPath patching, and opted to derive as much functionality as possible from existing classes. Immersive-ish Research almost completely overhauls the original research mechanics with an entirely new gameplay loop.


##### Mod Features

###### **Experiment System**
* A complete overhaul of the vanilla research mechanics.
* Discovering research costs resources and time.
* Specific topics and resource costs can be chosen to narrow down potential discoveries.

###### **Education and 'Brain Drain' Mechanic**
* Colonists need to learn education topics to keep their collective knowledge secure.
* Losing colonists can cause the colony to lose knowledge and progress.

###### **Ancient Datadisks**
* Locked datadisks that can be discovered and opened for monetary or research value, and can also have random flavour text.