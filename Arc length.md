---
tags:
  - MATH182
---
Arc length is defined as the distance between two points along a section of a curved line.

Determining the length of an irregular arc segment by approximating the arc segments as connected line segments is also called [[Curve rectification]]. A rectifiable curve has a finite number of segments in its rectification.

## General Approach
The length of a curve in the [[Euclidean plane]] can be approximated by connecting a finite number of points on a given curve using linear line segments to create a polygonal path. The total length of the approximation can be found as the summation of the lengths of each linear segment. This approximation is knows as the [[Chordal distance]].

## Finding Arc Lengths by Integration
If a planar curve in $\mathbb{R}^2$  is defined by the equation $y = f(x)$, where $f$ is continuously differentiable, then it is simply a special case of a parametric equation where $x = t$ and $y = f(t)$. The euclidean distance of each infinitesimal segment of the arc can be given by: 
$$\sqrt{dx^2 + dy^2} = \sqrt{1 + \left( \frac{dy}{dx} \right)^2} \space dx$$

The arc length is then given by: 
$$s = \int{ \sqrt{1 + \left( \frac{dy}{dx} \right)^2} \space dx}$$

## Finding Surface Areas by Integration
The area of a surface defined by $z = f(x, y), (x, y) \in D$, where $f_x$ and $f_y$ are continuous, is
$$A(S) = \int \int_D \sqrt{[f_x(x, y)]^2 + [f_y(x, y)]^2 + 1} \space dA$$

Using the alternative notation for [[Partial derivation|Partial derivatives]], this can be rewritten as follows:
$$A(S) = \int \int_D \sqrt{1 + ( \frac{ \partial z}{ \partial x} )^2 + ( \frac{ \partial z}{ \partial y} )^2} \space dA$$