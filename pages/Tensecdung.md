---
layout: default
title: 10 Second Dungeon
type: Solo Project
featured: false
tags:
    - UE4
    - C++
    - UE BP
preface: |
    10 Second Dungeon is an FPS Arcade, ‘Semi-Roguelite’ game made within 5 days. The game was developed in UE4 4.18, with a mixture of C++ and Blueprint.
images:
    - https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718822/10dung1_jr6i3t.png
    - https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718822/10dung3_itas2n.png
    - https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718823/10dung2_s9wksk.png
bgImg: https://res.cloudinary.com/dwwy1fzms/image/upload/e_blur:500/v1718718822/10dung3_itas2n.png
frontImg: https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718822/10dung3_itas2n.png
class: Tensecdung
---

{% include pageButton.html buttonName="View On Github" url="https://github.com/hubba368/10SecondDungeon" %}

##### Features
* FPS Character movement and shooting, inspired by fast paced shooters like Dusk.
* A ‘Modifier’ system that can affect the player, enemies and the game itself.
* A State Machine implementation that controls the enemies of the game.
* Interactable objects that can be picked up and used as weapons by throwing them.
* Randomly selected enemy and item locations with increasing difficulty over time.


##### Postmortem

##### What went right
###### **Player Character Movement and Shooting**
* I think the controls for the player are sound, in that they closely match my original ideas, which was inspired by fast-paced shooters such as Dusk and Quake

##### What went... mostly right
###### **Modifier system**
* I think the implementation I initially went for here works well, in that modifiers are checked and applied from a singleton class, and are also applied at the start of each level. However, I should’ve sticked to a more top Down approach, as I should’ve had some kind of Manager class for handling the AI enemies, which currently have no modifiers applied to them, and all of the player’s potential modifiers, which are split between ‘static’ modifiers, i.e. Health and move speed, and the bullet modifiers.

###### **Interactable objects**
* Interactable Objects was probably the section of the development of the game that took me the longest. They work like this:
~~~ C#
Check if player is hovering over it with the mouse by tracing a line.
    If player is hovering and not already holding something, 
    attach it to the players character object.
        If player throws the item, detach it from the player 
        and set its velocity to straight ahead.
Destroy on contact with anything (and call TakeDamage on enemy if hit).
~~~
* Although they work as intended in the psuedocode above, they also had bugs I was unable to fix on time, such as destroying itself if an enemy gets too close if the player is holding an item already.

##### What went wrong
###### **Random generation of levels**
* Random generation does not work very well, mainly because I decided to make it so objects and enemies are spawned at specific spawn points, chosen at random on creation time of the level. I went for this approach to save time for the Game Jam itself. It went wrong because the levels are very similar each time, with only minor differences in enemy placement when you advance to later levels.