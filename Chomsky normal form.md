---
tags:
  - CS456
---
A [[Context-free grammars|Context-free grammar]], $G$, is said to be in Chomsky normal form if all of its production rules are of the form:
$$\begin{align}
A &\rightarrow BC, \text{ or } \\ \space \\
A &\rightarrow a, \text{ or } \\ \space \\
S &\rightarrow \epsilon
\end{align}$$

where $A$, $B$, and $C$ are nonterminal symbols, the letter $a$ is a terminal symbol, $S$ is the start symbol, and $\epsilon$ denotes the empty string. Also, neither $A$ nor $C$ may be the start symbol, and the third production rule can only appear if $\epsilon$ is in $L(G)$, the language produced by the context-free grammar $G$.

## CFG to CNF

> [!example]
Let $G$ be a context-free grammar of the form:
> $$\begin{align}
S &\rightarrow AB \text{ | } aB \\ \space \\
A &\rightarrow aab \text{ | } \epsilon \\ \space \\
B &\rightarrow bbA
\end{align}$$
>
> 1. Remove $\epsilon$ productions ($A \rightarrow \epsilon$):
>
> $$\begin{align}
S &\rightarrow AB \text{ | } B \text{ | } aB \\ \space \\
A &\rightarrow aab \\ \space \\
B &\rightarrow bbA \text{ | } bb
\end{align}$$
>
> 2. Remove unit productions ($A \rightarrow B$):
>
> $$\begin{align}
S &\rightarrow AB \text{ | } bbA \text{ | } bb \text{ | } aB \\ \space \\
A &\rightarrow aab \\ \space \\
B &\rightarrow bbA \text{ | } bb
\end{align}$$
>
> 3. Remove useless productions ($A \rightarrow A$)
>
No changes
>
> 4. C1.
>
> $$\begin{align}
S &\rightarrow AB \text{ | } X_bX_bA \text{ | } X_bX_b \text{ | } X_aB \\ \space \\
A &\rightarrow X_aX_aX_b \\ \space \\
B &\rightarrow X_bX_bA \text{ | } X_bX_b \\ \space \\
X_a &\rightarrow a \\ \space \\
X_b &\rightarrow b
\end{align}$$
> 
> 5. C2.
>
> $$\begin{align}
S &\rightarrow AB \text{ | } X_{bb}A \text{ | } X_bX_b \text{ | } X_aB \\ \space \\
A &\rightarrow X_{aa}X_b \\ \space \\
B &\rightarrow X_{bb}A \text{ | } X_bX_b \\ \space \\
X_{aa} &\rightarrow X_aX_a \\ \space \\
X_{bb} &\rightarrow X_bX_b \\ \space \\
X_a &\rightarrow a \\ \space \\
X_b &\rightarrow b
\end{align}$$
