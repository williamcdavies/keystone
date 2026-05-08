---
tags:
  - CS477
---
Counting sort is a sorting algorithm that works by counting the number of objects that possess distinct values, and applying prefix sum on those counts to determine the positions of each key value in the output sequence. Counting sort has a worst-case complexity of $O(n + k)$, where $k$ is the range of the non-negative key values.

```
COUNTING-SORT(A, B, n, k):
	for i <- 0 to k
		do C[i] <- 0
	for j <- 1 to n
		do C[A[j]] <- C[A[j]] + 1
	% C[i] contains the number of elements equal to i %
	for i <- 1 to k
		do C[i] <- C[i] + C[i - 1]
	% C[i] contains the number of elements <= i
	for j <- n downto 1
		do B[C[A[j]]] <- A[j]
			C[A[j]] <- C[A[j]] - 1
```