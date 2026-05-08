---
tags:
  - CS456
---
The halting problem is the problem of determining, from a description of an arbitrary computer program and an input, whether the program will finish running, or continue to run forever. The halting problem is undecidable, meaning that no general algorithm exists that solves the halting problem for all possible program-input pairs.

The problem is to determine, given a program and an input to the program, whether the program will eventually halt when run with that input.

For example, in pseudocode, the program

```c
while (true) continue`
```

does not halt; rather, it goes on forever in an infinite loop. On the other hand, the program

```c
[print "Hello, world!"]
```

does halt.

While deciding whether these programs halt is simple, more complex programs prove problematic. One approach to the problem might be to run the program for some number of steps and check if it halts. However, as long as the program is running, it is unknown whether it will eventually halt or run forever. Turing proved no algorithm exists that always correctly decides whether, for a given arbitrary program and input, the program halts when run with that input. The essence of Turing's proof is that any such algorithm can be made to produce contradictory output and therefore cannot be correct.