---
tags:
  - CS658
---
Support vector machines are supervised max-margin models with associated learning algorithms that analyse data for classification and regression analysis.

## Linear SVM
We are given a training dataset of $n$ points of the form
$$( \vec{x}_1, y_1), \dots, ( \vec{x}_n, y_n)$$

where the $y_i$ are either $1$ or $-1$, each indicating the class to which the point $x_i$ belongs. Each $\vec{x}_i$ is a $p$-dimensional real vector. We want to find the maximum-margin hyperplane that divides the group of points $\vec{x_i}$ for which $y_i = 1$ from the group of points for which $y_i = -1$, which is defined so that the distance between the hyperplane and the nearest point $\vec{x}_i$ from either group is maximised.

Any hyperplane can be written as the set of points $\vec{x}$ satisfying
$$\vec{w}^\top \vec{x} - b = 0$$

where $\vec{w}$ is the normal vector to the hyperplane. This is much like Hesse normal form, except that $\vec{w}$ is not necessarily a unit vector. The parameter $\frac{b}{ \text{ || } \vec{w} \text{ || } }$ determines the offset of the hyperplane from the origin along the normal vector $\vec{w}$. 

## Hard-margin
If the training data is [[Linear seperability|Linearly separable]], we can select two parallel hyperplanes that separate the two classes of data, so that the distance between them is as large as possible. The region bounded by these two hyperplanes is called the margin, and the maximum-margin hyperplane is the hyperplane that lies halfway between them. With a normalised or standardised dataset, these hyperplanes can be described by the equations
$$\vec{w}^\top \vec{x} - b = 1$$ (anything on or above this boundary is of one class, with label $1$)

and 
$$\vec{w}^\top \vec{x} - b = -1$$ (anything on or below this boundary is of the other class with label $-1$)

Geometrically, the distance between these two hyperplanes is $\frac{b}{ \text{ || } \vec{w} \text{ || } }$, so to maximise the distance between the planes we want to minimise $\text{ || } \vec{w} \text{ || }$. The distance is computed using the distance from a point to a plane equation. We also have to prevent data points from falling into the margin, we add the following constraint: for each $i$ either
$$\vec{w}^\top \vec{x}_i - b \geq 1, \text{ if } y_i = 1$$

or 
$$\vec{w}^\top \vec{x}_i - b \leq -1, \text{ if } y_i = -1$$

These constraints state that each data point must lie on the correct side of the margin.

This can be rewritten as
$$y_i( \vec{w}^\top \vec{x} - b) \geq 1, \forall 1 \leq i \leq n$$