---
tags:
  - CS491
---
$$\text{ Lie Factor } = \frac{ \text{ size of effect shown in graphic } }{ \text{ size of effect in data } }$$

If the Lie Factor is equal to one, then the graphic might be doing a reasonable job of accurately representing the underlying numbers. Lie Factors greater than $1.05$ or less than $0.95$ indicate substantial distortion (for $\alpha = 0.05$), far beyond minor inaccuracies in plotting. The logarithm of the Lie Factor can be taken in order to compare overstating ($\log{ \text{LF} } > 0$) with understating ($\log{ \text{ LF } } < 0$) errors. In practice almost all distortion involve overstating, and Lie Factors of two to five are not uncommon.

```
A newspapaer reported that the U.S. Congress and the Department of Transportation had set a series of fuel economy standards to be met by automobile manufacturers, beginning with 18 miles per gallon in 1978 and moving in steps up to 27.5 by 1985, an increase of 53 percent: 
```

> [!example]
> $$\frac{27.5 - 18.0}{18.0} \times 100 = 54\%$$

```
The magnitude of the change from 1978 to 1985 is shown in the graph by the relative lengths of the two lines:
```

> [!example]
> $$\frac{5.3 - 0.6}{0.6} \times 100 = 783\%$$

```
Thus the numerical change of 53 percent is presented by some lines that changed 783 percent, yielding
```

$$\text{ Lie Factor } = \frac{783}{53} = 14.8$$

