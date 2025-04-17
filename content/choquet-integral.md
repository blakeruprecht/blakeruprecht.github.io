---
date: 2021-08-04
title: The Choquet Integral generalizes metric functions
description: "The Choquet Integral generalizes many metric functions, include maximum, minimum, order weighted average (OWA), linear-order statistics (LOS), and more."
---

This is a really cool integral that basically maps any metric function on sets like the MAXIMUM, MINIMUM, MEDIAN


## Choquet Integral: The Math
Where $\pi(j)$ sorts the inputs based on their output values, $h_{\pi(j)}$, which is the output for input $x_j$. Little g is a measure such that $g(A) < g(B)$ if $A \subseteq B$, $g(\emptyset) = 0$, $g(\mathbf{X}) = 1$. ChI adheres to monotonicity, idempotency, subcontinuity, etc. This includes the Linear Order Statistic (LOS) the Order Weighted Average (OWA), Maximum, Minimum, etc.
$$ \int h \odot g = C_g(h) = \sum_{j=1}^N h_{\pi(i)} \left( g(A_{\pi(j)}) - g(A_{\pi(j-1)}) \right) $$
$\pi$ is the function that sorts the inputs according to their values $h(x_j)$
$A_{\pi(j)}$ is the sorted vector = $\{x_{\pi(1)}, x_{\pi(2)}, ...\}$
$g$ is the learned measure (subsumes LOS, OWA, etc.)

## LOS/OWA
Also known as LOS or Ordered Weighted Average (OWA), LOS sorts the inputs based on their magnitude, and has a vector of weights the same dimension as the input. Inputs are sorted in descending order, and all the weights sum to 1. This is differentiable, so we can use *Pytorch*, and the integral basically acts as a [Multilayer perceptron](multilayer-perceptron.md) (another thing that can represent linear statistics on data). 

Example with three inputs (sort them first in descending order, largest first)
$w = [1,0,0]$ is the maximum operator
$w = [0,0,1]$ is minimum
$w = [0,1,0]$ is median
$w=[\frac{1}{3},\frac{1}{3},\frac{1}{3}]$ is average
$w = [0.7,0.3,0]$ is a soft-max
