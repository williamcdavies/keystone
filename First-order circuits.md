---
tags:
  - EE220
---
First-order circuits are circuits which contain either $1$ inductor or $1$ capacitor. First-order circuits can be represented by a first-order differential equation.

## First-Order RC Circuits
The complete response of a Thévenin (RC) circuit connected by a [[Capacitors|Capacitor]] over its terminals can be represented by a first-order differential equation of the form
$$v(t) = V + (v(0) - V)e^{ \frac{-t}{RC} }$$

where $V$ is the steady state response and $(v(0) - V)e^{ \frac{-t}{RC} }$ is the transient response.

A capacitor in a DC circuit behaves like an open circuit in steady state.

## First-Order RL Circuits
The complete response of a Norton (RL) circuit connected by an [[Inductors|Inductor]] over its terminals can be represented by a first-order differential equation of the form
$$i(t) = I + (i(0) - I)e^{ \frac{-Rt}{L} }$$

where $I$ is the steady state response and $(i(0) - I)e^{ \frac{-Rt}{L} }$ is the transient response.

An inductor in a DC circuit behaves like a short circuit in a steady state.