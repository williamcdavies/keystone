---
tags:
  - MATH487
---
Consider an $x_0$ and $y_0$, feasible in the primal and dual respectively. That is, $Ax_0 \leq \vec{b}$ and $A^Ty_0 = \vec{c}$. The complementary slackness theorem states $\vec{c}^Tx_0 = y_0^T \vec{b}$ if and only if $(y_0)_i > 0 \rightarrow A_ix_0 = \vec{b}_i$. In other words, the complementary slackness theorem states that if a dual variable is greater than zero (slack) then the corresponding primal constraint must be an equality (tight). It also states that if the primal constraint is slack then the corresponding dual variable is tight (or zero).