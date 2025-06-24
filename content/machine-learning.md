---
title: Machine Learning
date: 2023-05-15
description: '"Machines learn by correlating input to output. In supervised learning, this output is an array of numbers. In unsupervised learning, this output is a group of sets. In reinforcement learning, this output is one reward value and tons of negative rewards."'
---

At the highest level, machines learn very similarly to how humans learn. Data is given to the [neural network](neural-network.md), and then the robot does some calculations and tests it's performance against the environment.

## Supervised Learning (SL)
Data comes with labels. The network makes an initial random guess at what the labels should be. Then, it compares the guesses to the actual labels, and determines how off it was (total error). It updates the network according to this error. If it's really wrong, it updates a lot; similarly, if it's close, not so much update. Every time it makes a guess, it updates the network. Well, roughly, but that's TMI.

The network in times learns correlations between the data and the labels. This is why NNs are statistical in nature -- they're just making guesses based on averages. The more data, the better. It works pretty well if you actually cover all of the possible scenarios with your data and labels. Otherwise, expect a lot of false positives (FP) and false negatives (FN).

*Examples*: The o.g. GOAT Multilayer Perceptron, Linear Regression, Logistic Regression, Decision Trees (there are a lot of methods of each of these that are much more efficient and easier to get running than Neural Networks, so don't start thinking NNs are the end-all be-all of math/stats)

## Unsupervised Learning (UL)
This is basically a whole different branch of math. These include a bunch of different algorithms that use some crazy math to guess at the underlying structure of the data. That is, if the data has multiple different variables (like height, position, mass, intensity, etc.), which could be coming from sensors, all of the variables are treated mathematically as different axis, or dimensions. So sometimes we're talking about data that has an input of length 50, and you're doing high-dimensional math to try to figure out its structure. 

The problem with this is true underlying structure probably doesn't exist, so we're still just correlating to data.

*Examples*: K-Means Clustering, Autoencoders, Hidden Markov Models, Neural Gas

## Self-supervised Learning (SSL)
This is a great combo of the two above. SSL enables a NN to learn from the data itself about the data by using some creative methods. For example, with an image dataset, you can "mask off", or cover up, parts of the image, and have the network try to predict what is covered up. If you can imagine, after viewing thousands of images of similar scenes, the network gets pretty good at predicting missing parts from images. 

Similarly, modern large language models (LLM) do something similar. Big ones like ChatGPT go through huge collections of text, like all of [Wikipedia](https://wikipedia.org), and try to predict missing words from sentences (knowing all along what the words are, just quizzin itself on the data it has).

*Examples*: ChatGPT, Claude, BERT (2018)

## Reinforcement Learning (RL)
I saved the best for last. This one is awesome, and is literally about learning from your experiences ([growth mindset!](/growth-mindset)). 

This paradigm considers:
- an Agent: e.g. a neural network controlling a robot
- an Environment: a video game, simulation, or the real world

An Agent senses information from the Environment, giving it information about the current *state* (of the environment).

An Agent then takes action in the Environment. This could be anything from waiting, to moving forward, to using it's hands, whatever this agent has access to.

The agent keeps record of all of these (state, action) events in a thing called a *trajectory*, which can be thought of as the agent's memory. Eventually, at some time in the future, the agent may get a reward. It then uses RL math to associate that reward with particular (state,action) pairs, thus valuing those pairs higher than other ones.

Done enough times, and the Agent learns how to get more Reward from the Environment.


A technique to learn an approximation of an optimal policy to achieve rewards in a game environment. The environment is a game, which basically just means a subset of the universe, which includes states that can change over time. We have a robot in the environment, and it can perform actions to change the state of the environment. Eventually, some states in the environment can be defined as a "reward". The whole point of RL is to find some policy that maps states and actions to figure out how to get more reward by being in the "reward state" as much as possible.

For example, if you train a robot to play basketball, you can reward it only after it successfully plays a game and wins (robot score > opponent score). The robot will probably lose a thousand times first, and most likely will only win by random chance, but hey, that's how most of us get our first wins in anything.
