---
tags:
  - CS456
aliases:
  - Turing machine
---
A Turing machine can be formally defined as a $7$-tuple $M = (Q, \Sigma, \Gamma, \delta, q_0, B, F)$ where


- $Q$ is a finite, non-empty set of states;
- $\Sigma \subseteq \Gamma \setminus \{ B \}$ is the set of input symbols, that is, the set of symbols allowed to appear in the initial tape contents;
- $\Gamma$ is a finite, non-empty set of tape alphabet symbols;
- $\delta: (Q \setminus F) \times \Gamma \rightarrow Q \times \Gamma \times \{ L, R \}$ is a partial function called the transition function, where $L$ is left shift, $R$ is right shift. If $\delta$ is not defined on the current state and the current tape symbols, then the machine halts; intuitively, the transition function specified the next state transited from the current state, which symbol to overwrite the current symbol pointed by the head, and the next head movement;
- $q_0 \in Q$ is the initial state;
- $B \in \Gamma$ is the blank symbol (the only symbol allowed to occur on the tape infinitely often at any step during the computation);
- $F \subseteq Q$ is the set of final states or accepting states. The initial tape contents is said to be accepted by $M$ if it eventually halts in the state from $F$.

```
Determine a Turing machine for the the language L = \{ n_a(w) = 2n \text{ | } n \geq 0 \}.
```
> [!example] 
> $$\begin{align}
M &= (Q, \Sigma, \Gamma, \delta, q_0, B, F) \\ \space \\
&= ( \{ q_0, q_1, q_2, q_3 \}, \{ a, b \}, \{ a, b, \# \}, \delta, q_0, \#, \{ q_3 \} ) \text{ | } \\ \space \\
\delta &= ( \\ \space \\
% go to leftmost symbol
&(q_0, a, a, L, q_0) \\ \space \\
&(q_0, b, b, L, q_0) \\ \space \\
&(q_0, \#, \#, R, q_1) \\ \space \\
% saw 1st 'a'
&(q_1, a, a, R, q_2) \\ \space \\
% do nothing for 'b'
&(q_1, b, b, R, q_1) \\ \space \\
% saw 2nd 'a'
&(q_2, a, a, R, q_1) \\ \space \\
% do nothing for 'b'
&(q_2, b, b, R, q_2) \\ \space \\
% halt accept
&(q_1, \#, \#, L, q_3) \\ \space \\
)
\end{align}$$

