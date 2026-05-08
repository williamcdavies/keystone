---
tags:
  - CS456
---
A pushdown automaton is formally defines as a $7$-tuple:
$$M = (Q, \Sigma, \Gamma, \delta, q_0, Z, F)$$ where
- $Q$ is a finite set of states
- $\Sigma$ is a finite set which is called the input alphabet
- $\Gamma$ is a finite set which is called the stack alphabet
- $\delta$ is a finite subset of $Q \times ( \Sigma \cup \{ \epsilon \} ) \times \Gamma \times Q \times \Gamma^*$, the transition relation
- $q_0 \in Q$ is the start state
- $Z \in \Gamma$ is the initial stack symbol
- $F \subseteq Q$ is the set of accepting states

```
Determine the machine M = (Q, Sigma, Gamma, delta, q_0, $, F) that accepts the Language L = { a^nb^n | n \geq 0 }
```

> [!example]
> $$\begin{align}
M &= (Q, \Sigma, \Gamma, \delta, q_0, Z, F) \\ \space \\
Q &= \{ q_0, q_1, q_f \} \\ \space \\
\Sigma &= \{ a, b \} \\ \space \\
\Gamma &= \{ a, b, \$ \} \\ \space \\
\delta &= \{ (q_0, \lambda, \$ ) = (q_f, \lambda ) \\ \space \\
&= (q_0, a, \$ ) = (q_0, a \$ ) \\ \space \\
&= (q_0, a, a) = (q_0, aa) \\ \space \\
&= (q_0, b, a) = (q_1, \lambda ) \\ \space \\
&= (q_1, \lambda, \$ ) = (q_f, \lambda ) \\ \space \\
&= (q_1, b, a) = (q_1, \lambda ) \} \\ \space \\
q_0 &= q_0 \\ \space \\
Z &= \$ \\ \space \\
F &= \{ q_f \}
\end{align}$$