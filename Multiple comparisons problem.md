---
tags:
  - CS658
---
The multiple comparisons problem occurs when many statistical tests are performed on the same dataset. Each test has its own chance of a [[Type I errors|Type I error]], so the overall probability of making at least one false positive increases as the number of tests grows. 

For example, if one test is performed at the 5% level and the corresponding null hypothesis is true, there is only a 5% risk of incorrectly rejecting the null hypothesis. However, if 100 tests are each conducted at the 5% level and all corresponding null hypotheses are true, the expected number of incorrect rejections (also known as false positives) is 5. If the tests are statistically independent from each other (i.e. are performed on independent samples), the probability of at least one incorrect rejection is approximately 99.4%.