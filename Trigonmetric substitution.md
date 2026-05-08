---
tags:
  - MATH182
---
In calculus, trigonometric substitution is a technique for evaluating integrals. Moreover, one may use the trigonometric identities to simplify certain integrals containing radical expressions. 

## Case I: Integrands Containing $a^2 - x^2$
Let $x = a \sin{ \theta }$, and use the identity $1 \sin^2{ \theta } = \cos^2{ \theta }$.

Example 1:
In the integral 
$$\int{ \frac{dx}{ \sqrt{a^2 - x^2} } }$$ 

we may write 
$$x = \sin{ \theta } , \space dx = a \cos{ \theta } \space d \theta, \space \theta = \arcsin{ \frac{x}{a} }$$

Then, 
$$\begin{align}
\int{ \frac{dx}{ \sqrt{a^2 - x^2} } } &= \int{ \frac{a \cos{ \theta } \space d \theta}{ \sqrt{a^2 - a^2 \sin^2{ \theta } } } } \\\\
&= \int{ \frac{ a \cos{ \theta } \space d \theta}{ \sqrt{a^2(1 - \sin^2{ \theta }) } } } \\\\
&= \int{ \frac{ a \cos{ \theta } \space d \theta}{ \sqrt{a^2 \cos^2{ \theta } } } } \\\\
&= \int{ d \theta } \\\\
&= \theta + C \\\\
&= \arcsin{ \frac{x}{a} } + C
\end{align}$$

The above step requires that $a > 0$ and $\cos{ \theta } > 0$. We can choose $a$ to be the principal root of $a^2$, and impose the restriction $-\pi / 2 < \theta < \pi / 2$ by using the inverse sine function.

For a definite integral, one must figure out how the bounds of integration change. For example, as $x$ goes from $0$ to $a / 2$, then $\sin{ \theta }$ goes from $0$ to $1 / 2$, so $\theta$ goes from $0$ to $\pi / 6$. Then, 
$$\int_0^{a / 2}{ \frac{dx}{ \sqrt{a^2 - x^2} } } = \int_0^{ \pi / 6}{ d \theta} = \frac{ \pi }{6}$$

Some care is needed when picking the bounds. Because integration above requires that $-\pi / 2 < \theta < \pi / 2, \space \theta$ can only go from $0$ to $\pi / 6$. Neglecting this restriction, one might have picked $\theta$ to go from $\pi$ to $5 \pi / 6$, which would have resulted in the negative of the actual value.

## Case II: Integrands Containing $a^2 + x^2$
Let $x = a \tan{ \theta }$, and use the identity $1 + \tan^2{ \theta } = \sec^2{ \theta }$.

Example:
In the integral 
$$\int{ \frac{dx}{a^2 + x^2} }$$

we may write 
$$x = a \tan{ \theta } , \space dx = a \sec^2{ \theta } \space d \theta, \space \theta = \arctan{ \frac{x}{a} }$$

so that the integral becomes
$$\begin{align}
\int{ \frac{dx}{a^2 + x^2} } &= \int{ \frac{a \sec^2{ \theta } \space d \theta}{a^2 + a^2\tan^2{ \theta} } } \\\\
&= \int{ \frac{a \sec^2{ \theta } \space d \theta}{a^2(1 + \tan^2{ \theta }) } } \\\\
&= \int{ \frac{a \sec^2{ \theta } \space d \theta}{a^2 \sec^2{ \theta } } } \\\\
&= \int{ \frac{d \theta}{a} } \\\\
&= \frac{ \theta }{a} + C \\\\
&= \frac{1}{a} \arctan { \frac{x}{a} } + C,
\end{align}$$

provided $a \neq 0$.

For a definite integral, the bound change once the substitution is performed and are determined using the equation $\theta = \arctan { \frac{x}{a} }$, with the values in the range $\frac{-\pi}{2} < \theta < \frac{\pi}{2}$. Alternatively, apply the boundary terms directly to the formulae for the antiderivative.

## Case II: Integrands Containing $x^2 - a^2$
Let $x = a \sec{ \theta }$, and use the identity $\sec^2{ \theta } - 1 = tan^2{ \theta }$.

Integrals like 
$$\int{ \frac{dx}{x^2 - a^2} }$$

can also be evaluated by partial fractions rather than trigonometric substitutions. However, the integral 
$$\int{ \sqrt{x^2 - a^2} \space dx}$$ 

cannot. In this case, an appropriate substitution is: 
$$x = a \sec{ \theta } , \space dx = a \sec{ \theta } \tan{ \theta } \space d\theta, \space \theta = \arcsin{ \frac{x}{a} }$$ 

where $a > 0$ so that $\sqrt{a^2} = a$, and $0 \leq \theta < \frac{\pi}{2}$ by assuming $x > 0$, so that $\tan{ \theta } \geq 0$ and $\sqrt{ \tan^2{ \theta} } = \tan{ \theta }$.

Then, 
$$\begin{align}
\int{ \sqrt{x^2 - a^2} \space dx} &= \int{ \sqrt{a^2 \sec^2{ \theta } - a^2} \cdot a \sec{ \theta } \tan{ \theta } \space d \theta} \\\\
&= \int{ \sqrt{a^2( \sec^2{ \theta } - 1) } \cdot a \sec{ \theta } \tan{ \theta } \space d \theta} \\\\
&= \int{ \sqrt{a^2 \tan^2{ \theta} } \cdot a \sec{ \theta } \tan{ \theta } \space d \theta} \\\\
&= \int{a^2 \sec{ \theta } \tan^2{ \theta } \space d \theta} \\\\
&= \int{a^2 \sec{ \theta } \tan^2{ \theta } \space d \theta} \\\\
&= a^2\int{( \sec{ \theta })( \sec^2{ \theta } - 1) \space d \theta} \\\\
&= a^2\int{( \sec^3{ \theta } - \sec{ \theta }) \space d \theta}
\end{align}$$