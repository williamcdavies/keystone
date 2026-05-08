---
tags:
  - CS326
aliases:
  - Compiler
---
Compilation is the process in [[High-level programming languages]] are translated to [[Low-level programming languages]].

Regardless of the exact number of phases in compiler design, the phases can be assigned to one of three stages.
- The front end scans the input and verifies syntax and semantics according to a specific source language. For [[Statically types languages]] it performs [[Type checking]] by collecting type information. If the input program is syntactically incorrect or has a type error, it generates error messages. Aspects of the front end include [[Lexical analysis]], [[Syntax analysis]], and [[Semantic analysis]]. The front end transforms the input program into an intermediate representation for further processing by the middle end. This intermediate representation is usually a lower-level representation of the program with respect to the source code.
- The middle end performs optimisations on the intermediate representation that are independent of the CPU architecture being targeted. This source code independence is intended to enable generic optimisations to be shared between versions of the compiler supporting different languages and target processors.
- The back end takes the optimised intermediate representation form the middle end. It may perform more analysis, transformations, and optimisations that are specific for the target CPU architecture. The back end generates the target-dependent assembly language, performing register allocation in the process. The back end performs instruction scheduling, which re-orders instructions to keep parallel execution units buys by filling delay slots. Although most optimisation problems are NP-hard, heuristic techniques for solving them are well-developed and implemented in production-quality compilers. Typically the output of a back end is machine code specialised for a particular processor and operating system.