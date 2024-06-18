---
date: 2022-12-15
title: ANFIS has gradient problems
description: '"The Adaptive Neuro Fuzzy Inference System (ANFIS) suffers from dead, zero, and non-changing gradients during neural network style machine learning."'
---

See my [research](/research) for more info!

ANFIS has gradient problems during backpropagation. ANFIS is a type of [[neural networks]] trying to learn logical fuzzy rules. It is completely described using the three following equations. These equations are differentiable (mostly), so can be learned using neural techniques. The ws represent antecedents, the zs represent consequents, and the ys represent rule outputs.

$$ w_n^r = \prod_{k=1}^K A_k^r (x_n(k)) $$
$$ z_n^r = \rho_{bias}^r + \sum_{k=1}^K \rho_k^r (x_n(k)) $$
$$ y^r = \frac{\sum_{n=1}^N w_n^r \cdot z_n^r}{\sum_{n=1}^N w_n^r} $$

Gradient problems:
	- once dead, always dead
	- if only one rule fires, zero gradient
	- once big, no way to get smaller

---
# References
- Me