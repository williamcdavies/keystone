---
tags:
  - MATH283
---
For functions of more than one variable, the chain rule has several versions, each of them giving a rule for differentiating a composite function.

## Case 1
Suppose that $z = f(x, y)$ is a differentiable function of $x$ and $y$, where $x = g(t)$ and $y = h(t)$ are both differentiable functions of $t$. Then
$$\frac{dz}{dt} = \frac{ \partial f}{ \partial x} \frac{dx}{dt} + \frac{ \partial f}{ \partial y} \frac{dy}{dt}$$

## Case 2
Suppose that $z = f(x, y)$ is a differentiable function of $z$ and $y$, where $x = g(s, t)$ and $y = h(s, t)$ are differentiable functions of $s$ and $t$. Then
$$\frac{ \partial z}{ \partial s} = \frac{ \partial z}{ \partial x} \frac{ \partial x}{ \partial s} + \frac{ \partial z}{ \partial y} \frac{ \partial y}{ \partial s}$$
$$\frac{ \partial z}{ \partial t} = \frac{ \partial z}{ \partial x} \frac{ \partial x}{ \partial t} + \frac{ \partial z}{ \partial y} \frac{ \partial y}{ \partial t}$$