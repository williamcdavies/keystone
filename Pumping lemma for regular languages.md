---
tags:
  - CS456
---
Let $L$ be a regular language. Then there exists an integer $p \geq 1$ depending only on $L$ such that every string $w$ in $L$ of length at least $p$ ($p$ is called the "pumping length") can be written as $w = xyz$ (i.e., $w$ can be divided into three substrings), satisfying the following conditions:
1. $\text{ | } y \text{ | } \geq 1$
2. $\text{ | } xy \text{ | } \leq p$
3. $( \forall n \geq 0)(xy^nz \in L)$

$y$ is the substring that can be pumped (removed or repeated any number of times, and the resulting string is always in $L$). ($1$) means the loop $y$ to be pumped must be of at least one, that is not any empty string; ($2$) means the loop must occur within the first $p$ characters. $\text{ | } x \text{ | }$ must be smaller than $p$ (conclusion of ($1$) and $(2)$), but apart from that, there is no restriction on $x$ and $z$.

In simple words, for any regular language $L$, any sufficiently long string $w$ (in $L$) can be split into $3$ parts, i.e., $w = xyz$, such that all strings $xy^nz$ for $n \geq 0$ are also in $L$.

Below is the formal expression of the pumping lemma.
$$\begin{align}
\forall L \subseteq \Sigma^*, \text{ regular } (L) &\rightarrow \exists p \geq 1, \forall w \in L, \text{ | } w \text{ | } \geq p \\ \space \\
&\rightarrow \exists x, y, z \in \Sigma^*, (w = xyz) \land ( \text{ | } y \text{ | } \geq 1) \land ( \text{ | } xy \text{ | } \leq p) \land ( \forall n \geq 0, xy^nz \in L)
\end{align}$$

## Use of the Lemma to Prove Non-regularity
The pumping lemma is often used to prove that a particular language is non-regular: a proof by contradiction may consist of exhibiting a string (of the required length) in the language that lacks the property outlined in the pumping lemma.

Example: The language $L = \{ a^nb^n \text{ | } n \geq 0 \}$ over the alphabet $\Sigma = \{ a, b \}$ can be shown to be non-regular as follows
1. Assume that some constant $p \geq 1$ exists as required by the lemma.
2. Let $w$ in $L$ be given by $w = a^pb^p$, which is a string longer that p.
3. By the pumping lemma, there must exist a decomposition $w = xyz$ with $\text{ | } xy \text{ | } \leq p$ and $\text{ | } y \text{ | } \geq 1$ such that $xy^iz$ in $L$ for every $i \geq 0$.
4. Since $\text{ | } xy \text{ | } \leq p$, the string $y$ only consists of instances of $a$.
5. Because $\text{ | } y \text{ | } \geq 1$, it contains at least once instance of the letter $a$.
6. Pumping $y$ to give $xy^2z$ gives a word with more instances of the letter $a$ than the letter $b$, since some instances of $a$ but none of $b$ were added.
7. Therefore, $xy^2z$ is not in $L$ which contradicts the pumping lemma.
8. Therefore, $L$ cannot be regular.