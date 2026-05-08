---
tags:
  - CS326
---
A regular expression specifies a set of strings required for a particular purpose. Most formalisms provide the following operations to construct regular expressions:
- Boolean "or" separates alternatives. For example $\text{ gray } \text{ | } \text{ grey }$ can match "gray" or "grey".
- Grouping is used to define the scope and precedence of the operators. For example, $\text{ gray } \text{ | } \text{ grey }$ and $\text{ gr } ( \text{ a } \text{ | } \text{ e } ) \text{ y }$ are equivalent patterns.
- Quantification specifies how many times the preceding element is allowed to repeat. The most common quantifiers are the question mark $?$ (indicates $0 \text{ | } 1$ occurrences), the asterisk $*$ (indicates $\geq 0$ occurrences), and the plus sign $+$ (indicates $> 0$ occurrences). 

To maintain associativity and precedence in [[Formal grammars]], recursive components of regular expressions are limited to the left-most side of the listed expressions. This eliminates the ambiguity of regular expressions and resulting parse trees.

Regular expressions consist of constants, which denote sets of strings, and operator symbols, which denote operations over these sets.

Given a finite alphabet $\Sigma$, the following constants are defined as regular expressions:
- $\emptyset$ denoting the set $\emptyset$
- $\lambda$ denoting the set containing only the empty string
- $a \in \Sigma$ denoting the set containing only the character $a$

Given regular expressions $R$ and $S$, the following operations over them are defined to produce regular expressions (closed):
- (concatenation) $(RS)$ denotes the set of strings that can be obtained by concatenating a string accepted by $R$ and a string accepted by $S$ (in that order). For example, let $R$ denote $\{ ab, c \}$ and $S$ denote $\{ d, ef \}$. Then $(RS)$ denotes $\{ abd, abef, cd, cef \}$.
- (alternation) $(R \text{ | } S)$ denotes the set union of sets described by $R$ and $S$. For example, if $R$ describes $\{ ab, c \}$ and $S$ describes $\{ ab, d, ef \}$, expression $(R \text{ | } S)$ describes $\{ ab, c, d, ef \}$.
- (Kleene star) ($R*$) denotes the smallest superset of the described by $R$ that contains $\lambda$ and is closed under string concatenation. This is the set of all strings that can be made by concatenating any finite number (including $0$) of strings from the set described by $R$. For example, if $R$ denotes $\{ 0, 1 \}$, $(R*)$ denotes the set of all finite binary strings (including the empty string). If $R$ denotes $\{ ab, c \}$, $(R*)$ denotes $\{ \lambda, ab, c, abab, abc, cab, cc, ababab, abcab, \dots \}$.

```
Given r_1 = (a + b \cdot c)^* \cdot (c + \emptyset ) and r_2 &= (a + b \cdot c)^* \cdot (c + \lambda ), prove or disprove r_1 = r_2.
```

> [!example]
> $$\begin{align}
L(r_1) &= L((a + b \cdot c)^* \cdot (c + \emptyset )) \\ \space \\
&= L((a + (b \cdot c))^* \cdot (c + \emptyset )) \\ \space \\
&= (L(a) \cup L(bc))^*(L(c) \cup L( \emptyset )) \\ \space \\
&= ( \{ a \} \cup \{ bc \} )^*( \{ c \} \cup \emptyset ) \\ \space \\
&= \{ a, bc \}^* \{ c \} \\ \space \\
&= \{ \lambda, a, aa, bc, bcbc, abc, bca, \dots \} \{ c \} \\ \space \\
&= \{ c, ac, aac, bcc, bcbcc, abcc, \dots \} \\ \space \\
L(r_2) &= L(a + bc)^*L(c + \lambda ) \\ \space \\
&= (L(a) \cup L(bc))^*(L(c) \cup L( \lambda )) \\ \space \\
&= \{ a, bc \}^* ( \{ c \} \cup \{ \lambda \} ) \\ \space \\
&= \{ a, bc \}^* \{ c, \lambda \} \\ \space \\
&= \{ \lambda, a, bc, abc, bca, \dots \} \{ c, \lambda \} \\ \space \\
&= \{ c, ac, bcc, abcc, bcac, \dots, \lambda, a, bc, abc, bca, \dots \}
\end{align}$$
