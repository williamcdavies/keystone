---
tags:
  - STAT352
---
## Discrete Random Variables
The variance of a [[Discrete random variables|Discrete random variable]] is defined as the [[Expected values|Expected value]] of the squared deviation from the mean. This is stated mathematically as
$$V[X] = \sum_{i = 1}^{ \infty }{(x_i - E[X])^2} \cdot p_i$$

where $x_1, x_2, \dots , x_i$ are the possible outcomes of the random variable, $p_1, p_2, \dots , p_i$ are their corresponding probabilities, and $E[X]$ is the expected value of the random variable.

## Continuous Random Variables
The variance of a [[Continuous random variables|Continuous random variable]] is defined as the expected value of the squared deviation from the mean. This is stated mathematically as
$$V[X] = \left( \int_{ -\infty }^{ \infty }{x^2 \cdot f(x) \space dx} \right) - E[X]^2$$

where $f(x)$ is the [[Probability mass functions|Probability mass function]] of the distribution of the continuous random variable, and $E[X]$ is the expected value of the random variable.