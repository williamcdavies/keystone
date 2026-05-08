---
tags:
  - CS326
---
A non-strict evaluation order is an evaluation order that is not strict, that is, a function may return a result before all of its arguments are fully evaluated. The prototypical example is normal order evaluation, which does not evaluate any of the arguments until they are needed in the body of the function. Normal order evaluation has the property that it terminates without error whenever any other evaluation order would have terminated without error.