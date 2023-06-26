---
layout: default
title: Hearthstone Genetic Algorithm
preface: |
    For my final year undergraduate dissertation, I decided to develop a Genetic Algorithm that would have the ability to generate valid decks for the game Hearthstone, with the end goal of the algorithm generating solutions with an increasing number of wins over time, along with a secondary goal of the decks being balanced and varied, much like a human-designed deck would be.
startImg: 
images:

bgImg: assets/images/hsgabackground.png
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