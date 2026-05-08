---
tags:
  - CS326
---
Scheme is primarily a [[Functional programming]] language. It shares many characteristics with other members of the [[Lisp]] programming language family. Scheme's simple syntax is based on s-expressions, parenthesised lists in which a prefix operator is followed by its arguments. Scheme programs consist of sequences of nested [[Lists]]. Lists are also the main [[Data structures|Data structure]] in Scheme, leading to a close equivalence between source code and data formats.

The reliance on lists as data structures is shared by all Lisp dialects. Scheme inherits a rich set of list-processing primitives such as `cons`, `car`, and `cdr` from its Lisp progenitors.

## `cons`
Returns a newly allocated pair whose car is *obj1* and whose `cdr` is *obj2*. The pair is guaranteed to be strictly different from every existing object. If the `cdr` is a list then the return value is also considered to be a list.

```Scheme
Ex.

> (cons 'a '())
(a)
> (cons '(a) '(b c d))
((a) b c d)
> (cons "a" '(b c))
("a" b c)
> (cons 'a 3)
(a . 3)
> (cons '(a b) 'c)
((a b) . c)
```

## `car`
Returns the contents of the `car` field of a pair. This procedure can also be used with lists, which in Scheme are linked lists of pairs. The *car* procedure returns the head of a list.

```Scheme
Ex.

> (car '(a b c))
a
> (car '((a) b c d))
(a)
> (car '(1 . 2)) 
1
> (car '())
&assertion exception
```

## `cdr`
Returns the contents of the `cdr` field of pair. This procedure can also be used with lists, which in Scheme are linked lists of pairs. The *cdr* procedure returns the tail of a list.

```Scheme
Ex.

> (cdr '((a) b c d))
(b c d)
> (cdr '(1 . 2))
2
> (cdr '())
&assertion exception
```

## `reverse`
Returns a newly allocated list consisting of the elements of *list* in reverse order.

```Scheme
Ex.

> (reverse '(a b c))
(c b a)
> (reverse '(a (b c) d (e (f))))
((e (f)) d (b c) a)
```

## `append`
Returns a single value. An improper lists results if *obj* is not a proper list.

```Scheme
Ex.

> (append '(x) '(y))
(x y)
> (append '(a) '(b c d))
(a b c d)
> (append '(a (b)) '((c)))
(a (b) (c))
> (append '(a b) '(c . d))
(a b c . d)
> (append '() 'a)
a
> (append)
()
> (append 'a)
a
```

## Evaluation
- Constant atoms (num, string, bool id) evaluate to themselves:

```Scheme
> 1
1
```

- Identifiers evaluate to their bound value:

```Scheme
> (define a 1)
> a
1
```

- Lists evaluate as recursive function calls where the first element of the list must evaluate to a function:

```Scheme
> (- 2 1)
1
```

## Special Forms
Special forms are functions defined with unique rulesets. 
- The `define` keyword does not have a return value.
- The `quote` and `'` keywords do not evaluate the elements of their arguments.

## Functions

### `factorial`
Returns $n!$.

```Scheme
Ex.

> (define (factorial n)
	(if (or (= n 0) (= n 1))
		1
		(* n (factorial (- n 1)))
	)
)
```

### `len`
Returns the length of *list*. 

```Scheme
Ex.

> (define (len L)
	(if (null? L)
		0
		(+ 1 (len (cdr L)))
	)
)
```

### `member?`
Returns true if *element* in *list*, false otherwise.

```Scheme
Ex.

> (define (member? x L)
	(cond ((null? L) #f)
		((equal? x (car L)) #t)
		(else (member? x (cdr L))
		)
	)
)
```

### `deep_member?`
Returns true if *element* in *list*, false otherwise.

```Scheme
Ex.

> (define (deep_member? x L)
	(cond ((null? L) #f) 
		((list? (car L)) (or (deep_member? x (car L)) (deep_member? x (cdr L)))) 
		((equal? x (car L)) #t) 
		(else (deep_member? x (cdr L))
		)
	)
)
```

### `append`
Returns the appendment of *list* to *list*.

```Scheme
Ex.

> (define (append L1 L2)
	(cond ((null? L1) L2)
		(else (cons (car L1) (append (cdr L1) L2)))
	)
)
```

### `reverse`
Returns the reverse of *list*.

```Scheme
Ex.

> (define (reverse L)
	(if (null? L) '()
		(append (reverse (cdr L)) (list (car L)))
	)
)
```

### `conj`
Returns the conjunction of *element* and *list*.

```Scheme
Ex.

> (define (conj f L)
	(cond ((null? L) #t)
		(else (and (f (car L))) (conj f (cdr L)))
	)
)
```

### `filter`
Returns *list* excluding *element*.

```Scheme
Ex.

> (define (filter f L) 
	(cond ((null? L) '()) 
		((f (car L)) (cons (car L) (filter f (cdr L)))) 
		(else (filter f (cdr L))
		)
	)
)
```

### `set-car`
Assigns *list* head to *element*.

```Scheme
Ex.

> (define x '(a b c))
> (set-car! x 'm)
> 'x
(m b c)

> (define x '(a b c))
> (set-car! (cdr x) 'm)
> 'x
(a m c)
```

### `set-cdr`
Assigns *list* tail to *element*

```Scheme
Ex.

> (define x '(a b c))
> (set-cdr! x '(m n))
> 'x
'(a m n)

> (define x '(a b c))
> (set-cdr! x (cons 'm (cdr x)))
> 'x
'(a m b c)
```

## Sequencing

### `begin`
Evaluates listed expressions. Returns the value returned by the last expression. Useful for procedure sequencing.

```Scheme
Ex.

(begin
	 (display "Hello, ")
	 (display "world!")
	 (+ 1 2)
)
```