---
tags:
  - STAT352
---
Bayes' theorem gives a mathematical rule for inverting a [[Conditional probability]]. It is stated mathematically as the following equation:
$$P(A \text{ | } B ) = \frac{P(B \text{ | } A) \cdot P(A)}{P(B)}$$

where $A$ and $B$ are [[Statistical independence|Statistically independent]] events and $P(B) \neq 0$.

```
If 20% of all messages are spam messages, the word 'free' appears in 60% of all spam messages, and 13% of all messagse contain the word 'free', what is the probability that a message containing the word 'free' is a spam message?
```

> [!example]
Since $P( \text{ spam } ) = 0.2$, $P( \text{ free | spam } ) = 0.6$, and $P( \text{ free } ) = 0.13$,
> $$\begin{align}
P( \text{ spam | free } ) &= \frac{P( \text{ free | spam } ) \cdot P( \text{ spam } )}{P( \text{ free } )} \\\\
&= \frac{0.6 \cdot 0.2}{0.13} \\\\
&\approx 0.923
\end{align}$$

```
Suppose P(A | B) = 0.78, P(A | B') = 0.72, and P(B) = 0.21. Determien P(B | A).

Round your answer to trhee decimal places (e.g. 0.987).
```

> [!example]
> $$\begin{align}
P(B | A) &= \frac{P(A \text{ | } B) \cdot P(B)}{P(A)} \\\\
&= \frac{P(A \text{ | } B) \cdot P(B)}{P(A \text{ | } B) \cdot P(B) + P(A \text{ | } B^C) \cdot P(B^C)} \\\\
&= \frac{0.78 \cdot 0.21}{0.78 \cdot 0.21 + 0.72 \cdot 0.79} \\\\
&= 0.224
\end{align}$$

