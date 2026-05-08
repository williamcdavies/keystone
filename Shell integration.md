---
tags:
  - MATH182
---
Shell integration, also known as the shell method, is a method for calculating the volume of a [[Solids of revolution|Solid of revolution]], when integrating along an axis perpendicular to the axis of revolution. This is in contrast to [[Disc integration]] which integrates along the axis parallel to he axis of revolution.

## Definition
Consider a volume in three dimensions obtained by rotating a cross-section in the $xy$-plane around the $y$-axis. Suppose the cross-section is defined by the graph of the positive function $f(x)$ on the interval $[a,b]$. Then the formula for the volume will be:
$$2 \pi \int_a^b{(x - h)f(x) \space dx} , \text{ if } h \leq a < b$$
$$2 \pi \int_a^b{(h - x)f(x) \space dx} , \text{ if } a < b \leq h$$

If the function is of the $y$ coordinate and the axis of rotation is the $x$-axis then the formula becomes:
$$2 \pi \int_a^b{(y - k)f(y) \space dy} , \text{ if } k \leq a < b$$
$$2 \pi \int_a^b{(k - y)f(y) \space dy} , \text{ if } a < b \leq k$$