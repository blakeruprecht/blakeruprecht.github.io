---
date: 2022-12-15
title: ANFIS has gradient problems
description: '"The Adaptive Neuro Fuzzy Inference System (ANFIS) suffers from dead, zero, and non-changing gradients during neural network style machine learning."'
---

## It's a Neural Network that incorporates Fuzzy Sets
The first major project I worked on was coding up the Adaptive Neuro Fuzzy Inference System (ANFIS) in [Python](/blog/python), specifically utilizing the [PyTorch](/blog/python-scipy) package to calculate the gradients. I calculated the gradients by hand to validate PyTorch, but wouldn't you know it, PyTorch knows what it's doing. 

ANFIS is a type of artificial [neural network](/blog/neural-network) that combines the antecedent and consequent logic (fuzzy IF-THEN rules) of fuzzy logic with the backpropagation learning techniques of [multilayer perceptrons](/blog/multilayer-perceptron). Similar to a typical neural network, the input, $x_n(k)$, is a vector of scalars of length $n$ with features $k$. 

## It's only three equations
The antecedent, $w$, represents the fuzzy logic statement "If $x$ fits this rule well, then the rule matching strength, $w$, should be high." In this equation, the $A$ term is a function that takes in $x$ and returns $A(x)$, the membership value of the fuzzy set, which I called the rule-matching strength. ANFIS learns the $A(x)$ membership functions.
$$ w_n^r = \prod_{k=1}^K A_k^r (x_n(k)) $$

The next part of ANFIS is the consequent step, $z$, which can be run in parallel with the antecedent step. This is a simple first-order linear equation with a bias term that fits a line to all of the $x$ input values. ANFIS learns the $\rho$ values.
$$ z_n^r = \rho_{bias}^r + \sum_{k=1}^K \rho_k^r (x_n(k)) $$

The final step is called aggregation. This performs the fuzzy logic. As you can see, it's a weighted sum of all the consequent terms, weighted and normalized by the antecedent terms. So for each rule, how well did the inputs match that rule, $w$, and what was the consequent of that rule, $z$. There is a unique output, $y^r$, for every rule, $r$, in the system
$$ y^r = \frac{\sum_{n=1}^N w_n^r \cdot z_n^r}{\sum_{n=1}^N w_n^r} $$

## Learning
ANFIS learns the functions $A(x)$ and the values $\rho$ using backpropagation from the error. The error function can be anything you choose, but let's just use mean-squared error.
$$e = \frac{1}{2}(\hat{y} - y)^2$$


## Gradient Problems
For more technical details, see my [research](/research). Basically, after setting up this system, we found that ANFIS doesn't do it's job very well. It's supposed to learn using backpropagation of gradients, but there are many scenarios where the gradient is close to 0, causing no learning to happen. So wherever ANFIS gets initialized, it will often stay.

Gradient problems:
- Once dead, always dead
- If only one rule fires, zero gradient
- Once big, no way to get smaller

---
# References
- **B. Ruprecht**. “EXPLAINABLE PARTS-BASED CONCEPT MODELING AND REASONING”. University of Missouri, 2023. [PDF](https://blakeruprecht.com/research/ruprecht_ms_thesis.pdf)
- **B. Ruprecht**, W. Wu, M. Islam, D. T. Anderson, J. Keller, G. Scott, C. Davis, F. Petry, P. Elmore, K. Nock, E. Gilmour, “Possibilistic Clustering Enabled Neuro Fuzzy Logic,” WCCI 2020. [PDF](https://blakeruprecht.com/research/ruprecht_wcci2020.pdf). [code](https://github.com/blakeruprecht/ANFIS-SP1M).
- **B. Ruprecht**, C. Veal, A. Cannaday, D. T. Anderson, F. Petry, J. Keller, G. Scott, C. Davis, C. Norsworthy, P. Elmore, K. Nock, E. Gilmour, “Neuro-fuzzy logic for parts-based reasoning about complex scenes in remotely sensed data”, SPIE 2020. [PDF](https://blakeruprecht.com/research/ruprecht_spie2020.pdf). [code](https://github.com/blakeruprecht/Fuzzy-Fusion).
- *Note*: It always feels nice to be recognized for your work, especially by such as esteemed blogger as yourself.
