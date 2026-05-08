---
tags:
  - MATH182
aliases:
  - Infinite series
---
Any ordered infinite sequence of terms defines a series, which is the operation of adding the $a_i$ one after the other. To emphasise that there are an infinite number of terms, a series may be called an infinite series.

The infinite repetition of operations implied by a series cannot be carried on in a finite amount of time. However, if the summation of a set of terms in a series approaches a limit, it may be possible to determine its finite sum.

## Convergent Series
A series $\sum{a_n}$ is said to be convergent when the sequence ($s_k$) of partial sums has a finite limit. If the limit of $s_k$ is infinite or does not exist, the series is said to be divergent. When the limit of partial sums exists, it is called the value (or sum) of the series 
$$\sum_{n = 0}^{ \infty }{a_n} = \lim_{k \to \infty }{s_k} = \lim_{k \to \infty }{ \sum_{n = 0}^{k}{a_n} }$$

### [[Geometric series]]
A geometric series is one where each successive term is produced by multiplying the previous term by a constant known as the common ratio: 
$$1 + \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + \dots = \sum^{ \infty }_{n = 0}{ \frac{1}{2^n} } = 2$$

In general, the geometric series $\sum^{ \infty }_{n = 0}{ar^n}$ converges if and only if $\text{ | } r \text{ | } < 1$, in which case it converges to $\frac{a}{1 - r}$.

### [[Harmonic series]]
The harmonic series is the series: 
$$1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \frac{1}{5} + \dots = \sum^{ \infty }_{n = 0}{ \frac{1}{n} }$$ 

The harmonic series is divergent.

### [[Alternating series]]
An alternating series is a series where terms alternate signs: 
$$1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \frac{1}{5} - \dots = \sum^{ \infty }_{n = 1}{ \frac{(-1)^{n - 1}}{n} } = \ln{2}$$
