---
tags:
  - MATH283
---
A line integral is an integral where the function to be integrated is evaluated along a curve. The function to be integrated may be a scalar field or a vector field.

For some scalar field, the line integral along a piecewise smooth curve is defined as
$$\int_C{f(x, y) \space ds} = \int_a^b{f(h(t), g(t)) \sqrt{( \frac{dx}{dt} )^2 + ( \frac{dy}{dt} )^2} \space dt}$$

For a vector field, the line integral along a piecewise smooth curve is defined as
$$\int_C{ \vec{F}( \vec{r} ) \cdot d \vec{r} } = \int_a^b{ \vec{F}( \vec{r}(t) ) \cdot \vec{r}'(t) \space dt}$$