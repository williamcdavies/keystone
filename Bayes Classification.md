---
tags:
  - CS658
---
Bayes classification is a probabilistic framework for solving classification problems.

## Bayesian Classifier
Bayesian inference is a method of statistical inference in which Bayes’ theorem is used to update the probability for a hypothesis as more evidence or information becomes available. Bayesian updating is particularly important in the dynamic analysis of a sequence of data.

Bayesian inference derives the posterior probability as a consequence of two antecedents, a prior probability and a “likelihood function” derived from a statistical model for the observed data. Bayesian inference computes the posterior probability according to [[Bayes' theorem]]:
$$P(A \text{ | } B ) = \frac{P(B \text{ | } A) \cdot P(A)}{P(B)}$$

Where $A$ is the unknown record’s hypothesis of class to be tested, $B$ is the evidence associated with $A$ (attributes of the unknown record), and $P(A \text{ | } B )$ is the posterior probability of $A$ conditioned on $B$.

## Naive Bayes Classifier
In machine learning, naive Bayes classifiers are a family of simple probabilistic classifiers based on applying Bayes’ theorem with strong (naive) independence assumptions between the features.

Characteristics of Naïve Bayes Classifier
- Handle missing values by ignoring the instance during probability estimate calculations
- Robust to isolated noise points
- Robust to irrelevant attributes
- Independence assumption may not hold for some attributes

### Approach
Consider each attribute and class label as random variables, given a record with attributes $(A_1, A_2, \dots, A_n)$, our goal is to predict class $C$. More specifically, we want to find the value of $C$ that maximises $P(C \text{ | } A_1, A_2, \dots, A_n)$.

- Step 1. Compute the posterior probability $P(C \text{ | } A_1, A_2, \dots, A_n)$ for all values of $C$ using the Bayes theorem
$$P(C = C_j \text{ | } A_1, A_2, \dots, A_n) = \frac{P(A_1, A_2, \dots, A_n \text{ | } C)P(C)}{P(A_1, A_2, \dots, A_n)}$$

- Step 2. Estimate $P(A_1, A)2, \dots, A_n \text{ | } C)$ for all values of $C$ by assuming independence among attributes $A_i$ when class is given
$$P(A_1, A_2, \dots, A_n \text{ | } C = C_j) = P(A_1 \text{ | } C)P(A_2 \text{ | } C) \dots P(A_n \text{ | } C)$$

	- But how to compute conditional probability $P(A_i \text{ | } C)$? (Note that if one of the conditional probability is zero, then the entire expression becomes zero)
	- Original
	    - $N_c$: The number of records that belong to class $C$
		- $N_{ic}$: The number of records that consist of attribute value $A_i$ and belong to class $C$
$$P(A_i \text{ | } C) = \frac{N_{ic}}{N_c}$$

	- Laplace
		- $N_c$: The number of records that belong to class $C$
		- $N_{ic}$: The number of records that consist of attribute value $A_i$ and belong to class $C$
		- $l_C$: The number of classes
$$P(A_i \text{ | } C) = \frac{N_{ic} + 1}{N_c + l_C}$$


	- M-Estimate
		- $N_c$: The number of records that belong to class $C$
		- $N_{ic}$: The number of records that consist of attribute value $A_i$ and belong to class $C$
		- $p$: Prior probability, which is usually set as uniform priors
		- $m$: A parameter, which is also known as pseudocount (virtual examples) and is used for additive smoothing. It prevents the probabilities form being $0$. $m$ is generally chosen to be small
$$P(A_i \text{ | } C) = \frac{N_{ic} + m}{N_c + mp}$$

- Step 3. Choose value of $C$ that maximises $P(A_1, A_2, \dots, A_n \text{ | } C)P(C)$ is equivalent to choosing value of $C$ that maximises $P(C \text{ | } A_1, A_2, \dots, A_n)$