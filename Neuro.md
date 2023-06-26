---
layout: default
title: Neuroevolved agents in Hearthstone
preface: |
    For my MSc Comp Sci & AI thesis, I designed and developed a Neuroevolution program that could train and test agents for the game Hearthstone, with multiple designed agent opponents.
startImg: assets/images/msc1.png
images:

bgImg: assets/images/mscbackground.png
class: msc
---

{% include pageButton.html buttonName="View On Github" url="https://github.com/hubba368/mscproj" %}

{% include pageButton.html buttonName="View Dissertation PDF" url="assets/mscDiss.pdf" %}

This project centered around Neuroevolution, an adjacent field of unsupervised machine learning, in a similar vein to more well known methods such as Monte Carlo Tree Search or Q Learning. How Neuroevolution differs is that it combines neural network implementations with Genetic Algorithms to allow the network to reconfigure its structure over time, instead of learning through using pre-made datasets.

With this in mind, and the fact that at the time, I could not find any published examples of Neuroevolution being used in Hearthstone, this project was born. A combination of Fireplace, an open source emulator of Hearthstone, and NEAT-Python, a Neuroevolution framework, I was able to develop a small program that would train and test Neuroevolved agents against pre-designed bots.

My thesis was attempting to see whether a trained agent could successfully play the game, while also adhering to a 'strategy' as defined by the deck it uses, i.e. instead of learning to play cards with no discernable playstyle, it should play as the developers 'intended' e.g. aggro, midrange etc.

##### Features

* Capable of training bots for any desired number of generations that can be saved as Pickles and reused later.
* Dynamically selects heuristics that the bot should focus on based on the deck the bot uses.
* Multiple hand-designed opponent bots that use scoring methods based upon the actual implementation in Hearthstone.
* Allows for bots to play against each other and outputs their entire game statistics to csv files for later processing.


##### Results

My thesis showed that Neuroevolved bots could play Hearthstone extremely well, while also adhering to a certain playstyle that was expected of them, with some interesting areas of exploration.