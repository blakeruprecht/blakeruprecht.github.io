---
date: 2020-08-29
title: Multilayer Perceptrons are the basic unit of a NN
description: '"Multilayer Perceptrons are the foundational algorithm at the basis of all modern neural networks. Here, I describe them simply using a few basic equations."'
---


A type of NN that implements multiple layers of the basic perceptron. 

- $\mathbf{x}$ = input vector (e.g. $\mathbf{x}=[0.3, 5.4, 156.1]$) of length $N$ ($N=3$ in this e.g.), $\mathbf{x} \in [-\infty,\infty]$, can be normalized to [-1,1]$ or $[0,1]$

- $\mathbf{w}$ = weight vector of length $N$ in the range $[0,1]$

- $\sigma$ = activation function (typically ReLU, tanh, sigmoid, etc.)

- $y$ = output scalar

- $\hat{y}$ = label scalar

- $e$ = error or loss function (typically Mean Squared Error as shown here)

$$ y = \sigma(w^T \cdot x) $$
$$ e = \frac{1}{2}(\hat{y} - y)^2$$
