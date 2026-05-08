---
tags:
  - CS477
---
Radix sort is a sorting algorithm that works by creating and distributing elements into buckets according to their radix. For elements with more than one significant digit, this bucketing process is repeated for each digit, while preserving the ordering of the prior step, until all digits have been considered. Radix sort has a worst-case complexity of $O(w \cdot n)$, where $w$ is the key length.

```
RADIX-SORT(A, d)
	for i <- 1 to d
		do use a stable sort to sort array A on digit i
```