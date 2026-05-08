---
tags:
  - CS326
---
Name binding is the association of entities with identifiers. An identifier bound to an object is said to reference that object. Machine languages have no built-in notion of identifiers, but name-object bindings as a service and notation for the programmer is implemented by programming languages. Binding is intimately connected with [[Scoping]], as scope determines which names bind to which objects - at which locations in the program code (lexically) and in which one of the possible execution paths (temporally).

## Binding Time
- Static binding (or early binding) is name binding performed before the program is run.
- Dynamic binding (or late binding/virtual binding) is name binding performed as the program is running. 

An example of a static binding is a direct c function callL the function referenced by the identifier cannot change at runtime.

An example of dynamic binding is dynamic dispatch, as in a c++ [[Virtual functions|Virtual function]] call. Since the specific type of a polymorphic object is not known before runtime, the executed function is dynamically bound.

## Shallow Binding
When a function is called, the current referencing environment is used.

## Deep Binding
When a function is passed/returned/stored, the current referencing environment and the function itself are packed together and called a closure.