---
tags:
  - CS456
---
A nondeterministic finite automaton is represented formally by a $5$-tuple, $(Q, \Sigma, \delta, q_0, F)$ consisting of
- a finite set of states $Q$
- a finite set of input symbols called the alphabet $\Sigma$
- a transition function $\delta: Q \times ( \Sigma \cup \{ \lambda \} ) \rightarrow 2^Q$
- an initial (or start) state $q_0 \in Q$
- a set of accepting (or final) states $F \subseteq Q$

## Theorem 2.2
Let $L$ be the language accepted by a nondeterministic finite accepter $M_n = (Q_n, \Sigma, \delta_N, q_0, F_N)$. Then there exists a deterministic finite accepter $M_D = (Q_D, \Sigma, \delta_D, \{ q_0 \}, F_D)$ such that
$$L = L(M_D)$$

**Proof:** Given $M_N$, we use the procedure *nfa-to-dfa* below to construct the transition graph $G_D$ for $M_D$. To understand the construction, remember that $G_D$ has to have certain properties. Every vertex must have exactly $\text{ | } \Sigma \text{ | }$ outgoing edges, each labeled with a different element of $\Sigma$. During the construction, some of the edges may be missing, but the procedure continuous until they are all there.

**procedure: nfa-to-dfa**
1. Create a graph $G_D$ with vertex $\{ q_0 \}$. Identify this vertex as the initial vertex.
2. Repeat the following steps until no more edges are missing. Take any vertex $\{ q_i, q_j, \dots, q_k \}$ of $G_D$ that has no outgoing edge for some $a \in \Sigma$. Compute $\delta_N^*{(q_i, a)}, \delta_N^*{(q_j, a)}, \dots, \delta_N^*{(q_k, a)}$. If $$\delta_N^*{(q_i, a)} \cup \delta_N^*{(q_j, a)} \cup \dots \cup \delta_N^*{(q_k, a)} = \{ q_l, q_m, \dots, q_n \}$$ create a vertex for $G_D$ labeled $\{ q_l, q_m, \dots, q_n \}$ if it does not already exist. Add to $G_D$ an edge from $\{ q_i, q_j, \dots, q_k \}$ to $\{ q_l, q_m, \dots, q_n \}$ and label it with $a$.
3. Every state of $G_D$ whose label contains any $q_f \in F_N$ is identified as a final vertex.
4. If $M_N$ accepts $\lambda$, the vertex $\{ q_0 \}$ in $G_D$ is also made a final vertex.