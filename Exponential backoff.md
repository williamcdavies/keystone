---
tags:
  - CPE400
---
Exponential backoff is an algorithm that uses feedback to multiplicatively decrease the rate of some process, in order to gradually find an acceptable rate.

## Algorithm
An exponential backoff algorithm is a form of closed-loop control system that reduces the rate of a controlled process in response to adverse events. For example, if a smartphone app fails to connect to its server, it might try again 1 second later, then if it fails again, 2 seconds later, then 4, etc. Each time the pause of multiplied by a fixed amount. Other examples of adverse events include collisions of network traffic, an error response from a service, or an explicit request to reduce the rate.

The rate reduction can be modelled as an exponential function:
$$t = b^c$$

or
$$f = \frac{1}{b^c}$$

Here, $t$ is the time delay applied between actions, $b$ is the multiplicative factor or base, $c$ is the number of adverse events observed, and $f$ is the frequency of the process. The value of $c$ is incremented each time an adverse event is observed, leading to an exponential rise in delay and, therefore, an inversely proportional rate. An exponential backoff algorithm where $b = 2$ is referred to as a binary exponential backoff algorithm.