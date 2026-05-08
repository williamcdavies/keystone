---
tags:
  - CS365
---
Trivial proofs are [[Proofs]] that demonstrate the validity of the conditional statement $p \rightarrow q$ when $q$ is true. Vacuous proofs are often important when special cases of theorems are proved and in [[Mathematical induction]].

```
Let P(n) be "If a and b are positive integers with a >= b, then a^n >= b^n," where the domain consists of all nonnegative integers. Show that P(0) is true.
```

> [!example]
The proposition $P(0)$ is "If $a \geq b$, then $a^0 \geq b^0$." Because $a^0 = b^0 = 1$, the conclusion of the conditional statement "If $a \geq b$, then $a^0 \geq b^0$" is true. Hence, this conditional statement, which is $P(0)$, is true. This is an example of a trivial proof. Note that the hypothesis, which is the statement "$a \geq b$," was not needed in this proof.