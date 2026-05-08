---
tags:
  - MATH182
---
Riemann sums are certain kind of approximations of integrals by finite sums.

## Definition
A Riemann sum $S$ of $f$ over the interval $[a,b]$ is defined as
$$S = \sum_{i = 1}^n{f(x_i) \space \Delta x_i}$$

where $\Delta x_i = x_i - x_{i - 1}$ and $x_i \in [x_{i - 1}, x_i]$.

## Riemann Summation Methods
The four Riemann summation methods are best approached with subintervals of equal size. The interval $[a,b]$ is therefore divided into $n$ subintervals, each of length
$$\Delta x = \frac{b - a}{n}$$

### Left Rule
For the left rule, the function is approximated by its values at the left end points of the subintervals. This gives multiple rectangles with base $\Delta x$ and height $f(a + i \Delta x)$.  Doing this for $i = 0, 1, \dots , n - 1$, and summing the resulting areas gives
$$\int_a^b{f(x) \space dx} \approx L_n = \sum_{i = 1}^n{f(x_{i - 1}) \space \Delta x}$$

### Right Rule
For the right rule, the function is approximated by its values at the right end points of the subintervals. This gives multiple rectangles with base $\Delta x$ and height $f(a + i \Delta x)$.  Doing this for $i = 1, \dots , n$, and summing the resulting areas gives
$$\int_a^b{f(x) \space dx} \approx R_n = \sum_{i = 1}^n{f(x_i) \space \Delta x}$$

### Midpoint Rule
For the midpoint rule, the function is approximated by its values at the midpoints of the subintervals. This gives $f(a + \frac{ \Delta x}{2})$ for the first subinterval, $f(a + \frac{3 \Delta x}{2})$ for the next one, and so on until $f(b - \frac{ \Delta x}{2})$. Summing the resulting areas gives
$$\int_a^b{f(x) \space dx} \approx M_n = \Delta x[f( \overline{x}_1 ) + f( \overline{x}_2 ) + \dots + f( \overline{x}_n )]$$

### Trapezoidal Rule
For the trapezoid rule, the function is approximated by the average of its values at the left and right endpoints of the subintervals, Using the area formula $\frac{1}{2} h(b_1 + b_2)$ for a trapezium with parallel sides $b_1$ and $b_2$, and height $h$, and summing the resulting areas gives
$$\int_a^b{f(x) \space dx} \approx T_n = \frac{ \Delta x }{2}[f(x_0) + 2f(x_1) + 2f(x_2) + \dots + 2f(x_{n - 1}) + f(x_n)]$$