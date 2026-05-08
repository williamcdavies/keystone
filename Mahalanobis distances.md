---
tags:
  - CS658
---
Mahalanobis distance is a measure of the distance betwen a point $P$ and a probability distribution $D$.

Given a probability distribution $Q$ on $\mathbb{R}^N$, with mean $\vec{u} = (u_1, u_2, \dots u_N)^T$ and positive semi-definite covariance matrix $\sum$, the Mahalanobis distance of a point $\vec{x} = (x_1, x_2, \dots, x_N)^T$ from $Q$ is
$$d_M( \vec{x}, Q) = \sqrt{( \vec{x} - \vec{u} )^T \sum^{-1}{( \vec{x} - \vec{u} )} }$$