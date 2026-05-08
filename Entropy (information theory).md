---
tags:
  - CS658
---
The entropy of a [[Random variables|Random variable]] quantifies the average level of uncertainty or information associated with the variable's potential states or possible outcomes. This measures the expected amount of information needed to describe the state of the variable, considering the distribution of probabilities across all potential states. Given a discrete random variable $X$, which may be any member $x$ within the set $\mathcal{X}$ and is distributed according to $p: \mathcal{X} \rightarrow [0, 1]$, the entropy is
$$H(X) := -\sum_{x \in \mathcal{X} }{p(x) \log{p(x)} }$$

The choice of base for the logarithm, varies for different applications. Base $2$ gives the unit of bits (or "shannons"), while base $e$ gives "natural units" nat, and base $10$ gives units of "dits", "bans", or "hartleys".