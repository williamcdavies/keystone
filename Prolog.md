---
tags:
  - CS326
---
```prolog
> membership(X, L)
member(X, [X | _])
member(X, [_ | T]) :- member(X,  T)
```

```prolog
> sorted(L)
sorted([])
sorted([_])
sorted([A,  B | T]) :- A < B, sorted([B | T])
```

```prolog
> append(L1, L2, L)
append([], L2, L2)
append(L1, [], L1)
append([H | T], L2, [H | L]) :- append(T, L2, L)
```