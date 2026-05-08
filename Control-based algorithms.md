---
tags:
  - CPE400
---
## Original Algorithm

We begin with the simple algorithm that was originally describes in the [[Transmission control protocol (TCP)]]  specification. The idea is to keep a running average of the RTT and then compute the timeout as a function this RTT. Specifically, every time TCP sends a data segment, it records the time. When an ACK for that segment arrives, TCP reads the time again, and then takes the difference between these two times as a `SampleRTT`. TCP then computes an `EstimatedRTT` as a weighted average between the previous estimate and this new sample. That is,
$$\text{ EstimatedRTT } = \alpha \cdot \text{ EstimatedRTT } + (1 - \alpha ) \cdot \text{ SampleRTT }$$

The parameter $\alpha$ is selected to smooth the `EstimatedRTT`. A small $\alpha$ tracks changes in the RTT but is perhaps too heavily influence by temporary fluctuations. On the other hand, a large $\alpha$ is more stable but perhaps not quick enough to adapt to real changes. The original TCP specifications recommended a setting of $\alpha$ between $0.8$ and $0.9$. TCP then uses `EstimatedRTT` to compute the timeout in a rather conservative way:
$$\text{ TimeOut } 2 \cdot \text{ EstimatedRTT }$$

## Jacobson/Karels Algorithm
The main problem with the original computation is that it does not take the variance of the sample RTTs into account. Intuitively, if the variation among samples is small, then the `EstimatedRTT` can be better trusted and there is no reason for multiplying this estimate by $2$ to compute the timeout. On the other hand, a large variance in the sample suggests that the timeout value should not be too tightly coupled to the `EstimatedRTT`.

In the new approach the sender measures a new `SampleRTT` as before. it then folds this new sample into the timeout calculation as follows:
$$\begin{align}
\text{ Difference } &= \text{ SampleRTT } - \text{ EstimatedRTT } \\ \space \\
\text{ EstimatedRTT } &= \text{ EstimatedRTT } + ( \delta \cdot \text{ Difference } ) \\ \space \\
\text{ Deviation } &= \text{ Deviation } + \delta ( \text{ | } \text{ Difference } \text{ | } - \text{ Deviation } )
\end{align}$$

where $\delta$ is between $0$ and $1$. That is, we calculate both the weighted moving average of the RTT and the weighted moving average of its variation. TCP then computes the timeout value as a function of both `EstimatedRTT` and `Deviation` as follows:
$$\text{ TimeOut } = \mu \cdot \text{ EstimatedRTT } + \phi \cdot \text{ Deviation }$$

where based on experience, $\mu$ is typically set to $1$ and $\phi$ is set to $4$, Thus, when the variance is small, `TimeOut` is close to `EstimatedRTT`; a large variance causes the `Deviation` term to dominate the calculation.