---
layout: default
title: Hearthstone Genetic Algorithm
type: Uni Project
featured: false
tags:
    - Json
    - C#
preface: |
    For my BSc dissertation, I developed a Genetic Algorithm with the ability to generate valid and competent decks for the game Hearthstone.
images:
    - https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718853/hsga2_yzcqzs.png
    - https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718851/hsga3_e4bbrd.png
bgImg: https://res.cloudinary.com/dwwy1fzms/image/upload/e_blur:500/v1718718853/hsga2_yzcqzs.png
frontImg: https://res.cloudinary.com/dwwy1fzms/image/upload/v1718718852/hsga1_tpc3w6.png
class: HSGA
---

{% include pageButton.html buttonName="View On Github" url="https://github.com/hubba368/HSGA" %}

{% include pageButton.html buttonName="View Dissertation PDF" url="assets/DissertationCurrentFINAL.pdf" %}

The algorithm itself, along with it's various GUI components, were developed in C#. In order to retrieve the results, I used an open source Java implementation of the game, developed by Github user demilich1. My final results showed promise, with some 'runs' of the algorithm gaining a decent number of wins over time. However, there would need to be further improvements to the algorithm and the approach, to see if more refined results could be reached.

##### Features
* A simple GUI to make editing of algorithm inputs and parameters easy.
* A fully developed genetic algorithm, with multiple implementations of Crossover and Selection stages.
* Transfer of JSON card schema into a useable format for the genetic algorithm.
* Complete automation of entire process, including retrieval of required values from the simulation program.