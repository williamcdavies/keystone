---
tags:
  - CS456
---
A deterministic finite automaton $M$ is represented by a $5$-tuple, $(Q, \Sigma, \delta, q_0, F)$ consisting of
- a finite set of states $Q$
- a finite set of input symbols called the alphabet $\Sigma$
- a transition function $\delta : Q \times \Sigma \rightarrow Q$
- an initial (or start) state $q_0 \in Q$
- a set of accepting (or final) states $F \subseteq Q$

There are three classes of states that can be removed or merged from the original DFA without affecting the language it accepts.
- Unreachable states are states that are not reachable from the initial state of the DFA, for any input string. These states can be removed.
- Dead states (trap states) are the states from which no final state is reachable. These states can be removed unless the automaton is required to be complete.
- Non-distinguishable states are those that cannot be distinguished form one another for any input string. These states can be merged.

If a language $L$ is regular then $L^n \text{ | } n \geq 2$ are regular.