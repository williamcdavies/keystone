---
tags:
  - MATH181
---
For functions $f$ and $g$ which are differentiable on an open interval $I$ except possibly at point c contained in $I$, if $\lim_{x \to c}f(x) = \lim_{x \to c}g(x) = 0 \; \| \; \pm \infty$ and $g'(0) \ne 0$ for all $x$ in $I$ with $x \ne c$, and $\lim_{x \to c} \frac{f'(x)}{g'(x)}$ exists, then 
$$\lim_{x \to c} \frac{f(x)}{g(x)} = \lim_{x \to c} \frac{f'(x)}{g'(x)}$$

## Other Indeterminate Forms 

| Indeterminate Form            | Conditions                                                   | Transformations to $\frac{0}{0}$                                                                                |
|:----------------------------- |:------------------------------------------------------------ |:--------------------------------------------------------------------------------------------------------------- |
| $$\frac{0}{0}$$               | $$\lim_{x \to c}f(x) = 0, \lim_{x \to c}g(x) = 0$$           | $$-$$                                                                                                           |
| $$\frac{ \infty }{ \infty }$$ | $$\lim_{x \to c}f(x) = \infty, \lim_{x \to c}g(x) = \infty$$ | $$\lim_{x \to c} \frac{f(x)}{g{x}} = \lim_{x \to c} \frac{ \frac{1}{g(x)} }{ \frac{1}{f(x)} }$$                 |
| $$0 \cdot \infty$$            | $$\lim_{x \to c}f(x) = 0, \lim_{x \to c}g(x) = \infty$$      | $$\lim_{x \to c}f(x)g(x) = \lim_{x \to c} \frac{f(x)}{ \frac{1}{f(x)} }$$                                       |
| $$\infty - \infty$$           | $$\lim_{x \to c}f(x) = \infty, \lim_{x \to c}g(x) = \infty$$ | $$\lim_{x \to c}(f(x) - g(x)) = \lim_{x \to c} \frac{ \frac{1}{g(x) } - \frac{1}{f(x)}}{ \frac{1}{f(x)g(x)} }$$ |
| $$0^0$$                       | $$\lim_{x \to c}f(x) = 0^+, \lim_{x \to c}g(x) = 0$$         | $$\lim_{x \to c}f(x)^{g(x)} = \text{ exp } \lim_{x \to c} \frac{g(x)}{ \frac{1}{ \ln{f(x)} } }$$                |
| $$1^{ \infty }$$              | $$\lim_{x \to c}f(x) = 1, \lim_{x \to c}g(x) = \infty$$      | $$\lim_{x \to c}f(x)^{g(x)} = \text{ exp } \lim_{x \to c} \frac{ \ln{f(x)} }{ \frac{1}{g(x)} }$$                |
| $$\infty^0$$                  | $$\lim_{x \to c}f(x) = 0, \lim_{x \to c}g(x) = 0$$           | $$\lim_{x \to c}f(x)^{g(x)} = \text{ exp } \lim_{x \to c} \frac{g(x)}{ \frac{1}{ \ln{f(x)} } }$$                |
