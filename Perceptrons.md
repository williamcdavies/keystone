---
tags:
  - CS658
---
The perceptron is an algorithm for [[Supervised learning]] of binary classifiers. A binary classifier is a function that can decide whether or not an input, represented by a vector of numbers, belongs to some specific class. It is a type of linear classifier, i.e., a classification algorithm that makes it predictions based on a linear predictor functions combining a set of weights with the feature vector.

## Definition
In the modern sense, the perceptron is an algorithm for learning a binary classifier called a threshold function: a function that maps its input $\vec{x}$ (a real-valued vector) to an output value $f(x)$ (a single binary value):
$$f( \vec{x} ) = h( \vec{w} \cdot \vec{x} + b)$$

where $h$ is the Heaviside step-function (where an input of $> 0$ outputs $1$; otherwise $0$ is the output), $\vec{w}$ is a vector of real-valued weights, $\vec{w} \cdot \vec{x}$ is the [[Dot products|Dot product]] $\sum_{i = 1}^m{w_ix_i}$, where $m$ is the number of inputs to the perceptron, and $b$ is the bias. The bias shifts the [[Decision boundaries|Decision boundary]] away from the origin and does not depend on any input value.

In the context of neural networks, a perceptron is an artificial neurone using the Heaviside step function as the [[Activation functions|Activation function]].

## Learning Algorithm for a Single-layer Perceptron
Below is an example of a learning algorithm for a single-layer perceptron with a single output unit. For a single-layer perceptron with multiple output units, since the weights of one output unit are completely separate from all the others', the same algorithm can be run for each output unit.

### Definitions
We first define some variables:
- $r$ is the learning rate of the perceptron. Learning rate is a positive number usually chosen to be less than $1$. The larger the value, the greater the chance for volatility in the weight changes.
- $D = \{ ( \vec{x}_1, d_1), \dots, ( \vec{X}_s, d_s) \}$ is the training set of $s$ samples, where:
	- $\vec{x}_j$ is the $j$th input vector from the $n$-dimensional Euclidean space $\mathbb{R}^n$.
	- $d_j \in \{ 0, 1 \}$ is the desired output value of the perceptron for that input.

We show the values of the features as follows
- $x_{j, i}$ is the value of the $i$th feature of the $j$th training input vector.
- $x_{j, 0} = 1$

To represent the weights:
- $w_i$ is the $i$th value in the weight vector, to be multiplied by the value of the $i$th input feature.
- Because $x_{j, 0} = 1$, the $w_0$ is effectively a bias that we use instead of the bias constant $b$.

To show the time-dependence of $\vec{w}$, we use:
- $w_i(t)$ is the weight $i$ at time $t$.

### Steps
1. Initialise the weights. Weights may be initialised to $0$ or to a small random value. In the example below, we use $0$. Set the time counter $t$ to $0$.
2. For each example $j$ in our training set $D$, perform the following steps over the input $\vec{x}_j$ and desired output $d_j$:
	1. Calculate the output with the current weight vector $$\vec{w}(t) = (w_0(t), w_1(t), \dots, w_n(t)): y_j(t) = h[w_0(t)x_{j, 0} + w_1(t)x_{j, 1} + w_2(t)x_{j, 2} + \dots + w_n(t)x_{j, n}]$$
	2. Update the weights: $$w_i(t + 1) = w_i(t) + r \cdot (d_j - y_i(t))x_{j, i} = w^{k + 1} = w^k + \lambda[y_i - f(w^k, x_i)]x_i$$, for all features $0 \leq i \leq n$, $r$ is the learning rate.
	3. Increment the time counter: $t := t+ 1$