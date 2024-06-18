---
date: 2023-02-15
title: AIs learn through a variety of learning paradigms.
description: '"Machines learn by correlating input to output. In supervised learning, this output is an array of numbers. In unsupervised learning, this output is a group of sets. In reinforcement learning, this output is one reward value and tons of negative rewards."'
---

date
+++

## Supervised
Data comes with labels. The network learns the labels associated with the data. It works pretty well, given the labels actually fit the data, otherwise you get lots of False Positives and False Negatives, semantically. 

## Unsupervised
Different techniques are used to learn structure from data. Problem, is there any true underlying structure to data? Do clusters actually exist? It's useful to cluster often, but hard to prove validity.

## Self-supervised
A learning paradigm for training a [[neural networks]]. Utilizes training data to learn things about the image. Example, David Lowe in "Unsupervised Learning from Depth..." uses and image and the one before and ahead of it, uses a U-net to create a depth estimation, and uses a pose estimator network to learn poses of the three images to predict the depth map. Uses the pose predictor network to predict the pose of image I and calculates error between the real image and the predicted image. 

## Reinforcement Learning
A technique to learn an approximation of an optimal policy to achieve rewards in a game environment. The environment is a game, which basically just means a subset of the universe, which includes states that can change based on actions. We have a robot in the environment, and it can perform actions to change the state of the environment. Eventually, some states in the environment can be defined as a "reward". The whole point of RL is to find some policy that maps states and actions to figure out how to get more of this reward. 





---
# References