---
date: 2022-02-27
title: Neural gas learns a self-organizing map
description: "\"This algorithm learns a self-organizing map using neural network techniques. They're really cool to look at in simulation.\""
---
Similar to [[Kohonen map]], a Self-organing Map, but the topology is *learned*. Goal is to learn a topological structure to relate "close" datapoints to each other. Winner-takes-*most*. Growing neural gas starts with two-neurons and keeps adding a bisecting neuron until the stopping criteria is met (e.g. performance measure below threshold)

## Algorithm
- Given an input dataset $x \in \mathbb{R}^n$
- Init "weights" $w_i \in \mathbb{R}^n$
- Pick a datapoint $v$ from $x$, 
	- For each weight $w_i$, calculate the distance to $v$
	- For each weight, determine the number (cardinality?) of how many other weights are closer to $v$ than $w_i$, which is $k_i$ -> closest weight is $w_{i0}$
	- Then, update the weights to better match the data
		- $w^{new}_i = w^{old}_i + (\epsilon) (exp(-k_i/\lambda)(v-w^{old}_i )$
		- basically, the new position is the old position moved closer to $v$, decreased by $\epsilon$, decreased by the number of weights ahead of it in line, $\exp(-k_i/\lambda)$, in the direction of the point$v$, -> $(v-w_i^{old})$
	- Create an edge between the two closest points to $v$, $C_{i0,i1} = 1$ set the timer to 0 for this edge
		- If the edge is already there, reset the timer to 0
	- Add 1 to each timer of all connections to $w_{i0}$ 
	- Remove old connections with time over threshold $T$


---
# References
- Fritzke, B. *A Growing Neural Gas Network Learns Topologies*. NeurIPS. 1994.
- T. Martinetz, S. Berkovich, and K. Schulten. *"Neural-gas" Network for Vector Quantization and its Application to Time-Series Prediction*. IEEE-Transactions on Neural Networks, 4(4):558-569, 1993.