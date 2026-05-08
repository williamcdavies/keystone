---
tags:
  - CS365
---
Quantification is used to create [[Propositions]] from [[Propositional functions]]. Quantification expresses the extent to which a predicate is true over a range of elements.

## Universal quantification
Many mathematical statements assert that a property is true for all values of a variable in a particular domain, called the domain of discourse, often just referred to as the domain. Such a statement is expressed using universal quantification. The universal quantification of $P(x)$ for a particular domain is the proposition that asserts that $P(x)$ is true for all values of $x$ in this domain.

## Existential quantification
Many mathematical statements assert that there is an element with a certain property. Such statements are expressed using existential quantification. With existential quantification, we form a proposition that is true if and only if $P(x)$ is true for at least on value of $x$ in the domain.

## Binding variables
When a quantifier is used on the variable $x$, we say that this occurrence of the variable is bound. An occurrence of a variable that is not bound by a quantifier or set equal to a particular value is said to be free.

---
## References
Discrete Mathematics and Its Applications Sec. 1.4.3 - Kenneth H. Rosen
> "The *universal quantification* of $P(x)$ is the statement - "$P(x)$ for all values of $x$ in the domain." - The notation $\forall xP(x)$ denotes the universal quantification of $P(x)$. Here $\forall$ is called the universal quantifier. We read $\forall xP(x)$ as "for all $xP(x)$" or "for every $xP(x)$." An element for which $P(x)$ is false is called a counterexample to $\forall xP(x)$."

> "Generally, an implicit assumption is made that all domains of discourse for quantifiers are nonempty. Note that if the domain is empty, then $\forall xP(x)$ is true for any propositional function $P(x)$ because there are no elements $x$ in the domain for which $P(x)$ is false."

> "The *existential quantification* of $P(x)$ is the proposition - "There exists an element $x$ in the domain such that $P(x)$." - We use the notation $\exists xP(x)$ for the existential quantification of $P(x)$. Here $\exists$ is called the *existential quantifier*."

> "Generally, an implicit assumption is made that all domains of discourse for quantifiers are nonempty. If the domain is empty, then $\exists xQ(x)$ is false whenever $Q(x)$ is a propositional function because when the domain is empty, there can be no element $x$ in the domain for which $Q(x)$ is true."

Discrete Mathematics and Its Applications Sec. 1.4.8 - Kenneth H. Rosen
> "Statements involving predicates and quantifiers are *logically equivalent* if and only if they have the same truth value no matter which predicates aer substituted into these statements and which domain of discourse is used for the variables in these propositional functions. We use the notation $S \equiv T$ to indicate that two statements $S$ and $T$ involving predicates and quantifiers are logically equivalent."