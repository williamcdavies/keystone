---
tags:
  - CS658
---
Gradient descent is a method for unconstrained optimisation. It is a first-order iterative algorithm for minimising a differentiable multivariate function.

The idea is to take repeated steps in the opposite direction of the gradient of the function at the current point, because this is the direction of steepest descent.

## Description
Gradient descent is based on the observation that if the multi-variable function $f( \vec{x} )$ is defined and differentiable in a neighbourhood of a point $\vec{a}$, then $f( \vec{x} )$ decreases fastest if one goes from $\vec{a}$ in the negative gradient of $f$ at $\vec{a}$, $- \nabla f( \vec{a} )$. It follows that, if
$$\vec{a}_{n + 1} = \vec{a}_n - \eta \nabla f( \vec{a}_n )$$

for a small enough learning rate $\eta \in \mathbb{R}_+$, then $f( \vec{a}_n ) \geq f( \vec{a}_{n + 1} )$.