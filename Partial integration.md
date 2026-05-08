---
tags:
  - MATH182
---
Partial integration is a process that finds the integral of product of functions in terms of the integral of the product of their derivative and antiderivative.

The partial integration formula states: 
$$\begin{align}
\int_a^b{u(x)v'(x) \space dx} &= \left[u(x)v(x) \right]_a^b - \int_a^b{u'(x)v(x) \space dx} \\\\
&= u(b)v(b) - u(a)v(a) \int_a^b{u'(x)v \space dx}
\end{align}$$

Or, letting $u = u(x)$ and $du = u'(x) \space dx$ while $v = v(x)$ and $dv = v'(x) \space dx$, the formula can be written more compactly:
$$\int{u \space dv} = uv - \int{v \space du}$$

The theorem can be derived as follows. For two continuously differentiable functions $u(x)$ and $v(x)$, the product rule states: 
$$\left((u(x)v(x) \right)' = v(x)u'(x) + u(x)v'(x)$$ 

Integrating both sides with respect to $x$, 
$$\int{ \left(u(x)v(x) \right)' \space dx} = \int{u'(x)v(x) \space dx} + \int{u(x)v'(x) \space dx}$$ 

and noting that an indefinite integral is an antiderivative gives 
$$u(x)v(x) = \int{u'(x)v(x) \space dx} + \int{u(x)v'(x) \space dx}$$ 

where we neglect writing the constant of integration. This yields the formula for partial integration:
$$\int{u(x)v'(x) \space dx} = u(x)v(x) - \int{u'(x)v(x) \space dx}$$ 

or in terms of the differentials $du = u'(x) \space dx$, $dv = v'(x) \space dx$, 
$$\int{u(x) \space dv} = u(x)v(x) - \int{v(x) \space du}$$ 

This is to be understood as an equality of function with an unspecified constant added to each side. Taking the difference of each side between two values $x=a$ and $x=b$ and applying the fundamental theorem of calculus gives the definite integral version: 
$$\int_a^b{u(x)v'(x) \space dx} = u(b)v(b) - u(a)v(a) - \int_a^b{u'(x)v(x) \space dx}$$ 

The original integral $\int{uv' \space dx}$ contains the derivative $v'$; to apply the theorem, one must find $v$, the antiderivative of $v'$, then evaluate the resulting integral 
$$\int{vu' \space dx}$$

