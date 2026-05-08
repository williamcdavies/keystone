---
tags:
  - MATH487
---
EOQ or economic order quantity, is the order quantity that minimises total cost in inventory management.

The single-item EOQ formula is
$$Q^* = \sqrt{ \frac{2aK}{h} \times \frac{p + h}{p} }$$

The single-item RPD formula is
$$S^* = \sqrt{ \frac{2aK}{h} \times \frac{p}{p + h} }$$

where $a$ is the demand per unit time, $K$ is the fixed order cost, $h$ is the holding cost per unit, and $p$ is the penalty cost per unit.

The difference $S^* - Q^*$ is the inventory deficit at $\frac{Q^*}{a}$.

```
Suppose you're running a water-supply depot for forces in Saudi-Arabia circa 1991. Water is needed at a rate of 10,000 gallons per day. It costs 10 cents per gallon plus a $500 surcharge to haul any amount of water from the desalination plant to your depot. In addition, it costs 2.5 cents per gallon per day to store water. What should your ordering policy be?
```

> [!example]
Given $a = 10000$, $K = 500$, $h = 0.025$, and $p = \infty$, the optimal order quantity is 
$$Q^* = \sqrt{ \frac{2 \cdot 10000 \cdot 500}{0.025} \times \frac{ \infty + 0.025}{ \infty } } = 20000$$ 
>
The optimal order frequency is then 
$$\frac{Q^*}{a} = \frac{20000}{10000} = 2$$
>
Therefore, we should order $20000$ gallons of water from the desalination plant every $2$ days.