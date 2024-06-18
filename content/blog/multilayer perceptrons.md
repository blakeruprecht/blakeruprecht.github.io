---
date: 2020-08-29
title: Multilayer Perceptrons are the basic unit of a NN
description: '"Multilayer Perceptrons are the foundational algorithm at the basis of all modern neural networks. Here, I describe them simply using a few basic equations."'
---


A type of NN that implements multiple layers of the [[Perceptron]]. 

- $\mathbf{x}$ = input vector of length $N$

- $\mathbf{w}$ = weight vector of length $N$

- $\sigma$ = activation function (typically ReLU, tanh, sigmoid, etc.)

- $y$ = output scalar

- $\hat{y}$ = label scalar

- $e$ = error or loss scalar function (typically 1/2e^2)

$$ y = \sigma(w^T \cdot x) $$
$$ e = \frac{1}{2}(\hat{y} - y)^2$$