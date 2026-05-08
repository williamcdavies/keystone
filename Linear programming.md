---
tags:
  - MATH487
---
Linear programming is the optimisation of a linear function subject to linear constraints. Linear programming is conceptually closer to linear optimisation than computer programming.

```
The Furniture Problem:

Suppose you are the director of a furniture plant which makes tables and chairs out of iron and wood. A table can be made from 1 pound of iron and 20 pounds of wood at a labour cost of 16 hours. A chair can be made from 2 pounds of iron and 15 pounds of wood at a labour cost of 5 hours. A table can be sold at a profit of $80. A chair can be sold at a profict of $40.

Suppose the plant has access to 100 pounds of iron, 1000 pounds of wood, and 640 labour hours per day. What quantity of tables and chairs should you produce to maximise profit?
```

> [!example]
Determine the decision variables:
> - $T = \text{ \# Tables / Day }$
> - $C = \text{ \# Chairs / Day }$
>
Determine the object function:
> - $\text{ Maximise } f \mid f(T, C) = 80T + 40C$
>
Determine the constraints:
> - $1T + 2C \leq 100$
> - $20T + 15C \leq 1000$
> - $16T + 5C \leq 640$
> - $T, C \geq 0$
>
Since the number of decision variables is $\leq 3$, the linear program can be solved graphically. By representing each constraint as a linear equation we obtain the feasible region, which is the set of all $(T, C)$ pairs which satisfy the given constraints. The optimal solution to the linear program is found at the point where the objective function is tangent to the boundary of the feasible region. In this case, the optimal solution to the linear program is determined to be the point $(T, C) = ( \frac{230}{7} , \frac{160}{7} )$.

## General Form
A linear program is said to be in general form if it is written as:
$$\text{ max \text{ | } min } \quad c_1x_1 + \dots + c_nx_n = Z$$
$$\begin{align}
\text{ S.T. } &\quad a_{11}x_1+ a_{12}x_2 + \dots + a_{1n}x_n &\quad \geq \text{ | } \leq \text{ | } = &\quad b_1 \\\\
&\quad a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n &\quad \geq \text{ | } \leq \text{ | } = &\quad b_2 \\\\
&\quad a_{31}x_1 + a_{32}x_2 + \dots + a_{3n}x_n &\quad \geq \text{ | } \leq \text{ | } = &\quad b_3 \\\\
\vdots \\\\
&\quad a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n &\quad \geq \text{ | } \leq \text{ | } = &\quad b_m \\\\
\end{align}$$

## Standard Form
A linear program is said to be in standard form if it is written as:
$$\text{ min } \quad c_1x_1 + \dots + c_nx_n = Z$$
$$\begin{align}
\text{ S.T. } &\quad a_{11}x_1+ a_{12}x_2 + \dots + a_{1n}x_n &\quad = &\quad b_1 \\\\
&\quad a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n &\quad = &\quad b_2 \\\\
&\quad a_{31}x_1 + a_{32}x_2 + \dots + a_{3n}x_n &\quad = &\quad b_3 \\\\
\vdots \\\\
&\quad a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n &\quad = &\quad b_m \\\\
&\quad x_1, x_2, \dots , x_n &\quad \geq &\quad 0 \\\\
&\quad b_1, b_2, \dots , b_m &\quad \geq &\quad 0 \\\\
\end{align}$$

Any linear program in general form can be rewritten in standard form. The steps of this procedure can be performed in any order, and are as follows:
1. If the linear programming problem is formulated as a maximisation problem, cast it into an equivalent minimisation problem by multiplying the objective function by $-1$.
2. For each inequality constraint, introduce a slack variable to cast it into an equality constraint. Specifically, for a constraint of the form $a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n \leq b_1$, introduce a slack variable $s_1 \geq 0$ to cast the constraint into $a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n + s_1 = b_1$.
3. If any constraint has a negative right-hand side, multiply both sides of the constraint by $-1$ to ensure that all right-hand sides are non-negative
4. If any variable $x_i$ is required to be non-positive, replace it with a new variable $x_i' = -x_i$, where $x_i' \geq 0$.
5. If any variable is unrestricted in sign (i.e., it can take both positive and negative values), express it as the difference between two non-negative variables. Specifically, for an unrestricted variable $x_i$, replace it with two new variables $x_i' \geq 0$ and $x_i'' \geq 0$ such that $x_i = x_i' - x_i''$​.

## Canonical Form
A linear program is said to be in canonical form if it is written as:
$$\text{ min } \quad c_1x_1 + \dots + c_nx_n = Z$$
$$\begin{align}
\text{ S.T. } &\quad a_{11}x_1+ a_{12}x_2 + \dots + a_{1n}x_n + s_1 &\quad = &\quad b_1 \\\\
&\quad a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n + s_2 &\quad = &\quad b_2 \\\\
&\quad a_{31}x_1 + a_{32}x_2 + \dots + a_{3n}x_n + s_3 &\quad = &\quad b_3 \\\\
\vdots \\\\
&\quad a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n + s_m &\quad = &\quad b_m \\\\
&\quad x_1, x_2, \dots , x_n &\quad \geq &\quad 0 \\\\
&\quad s_1, s_2, \dots , s_m &\quad \geq &\quad 0 \\\\
&\quad b_1, b_2, \dots , b_m &\quad \geq &\quad 0 \\\\
\end{align}$$