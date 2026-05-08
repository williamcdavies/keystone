---
tags:
  - CS326
---
The scope of a [[Name binding]] is the part of a program where the name binding is valid; that is, where the name can be used to refer to the entity. In other parts of the program, the name may refer to a different entity, or to nothing at all. Scope helps prevent name collisions by allowing the same name to refer to different objects provides the names have different scopes. The scope of a name binding is also known as the visibility of an entity.

## Static Scoping
Static scoping is determined by the structure of the source code. The general rule us that bindings are determined by finding the innermost declaration, searching outward through the enclosing scopes if needed.

### Scope Holes
In static scoping inner declarations shadow outer declarations of the same identifier, causing a hole in the scope of the out identifier's binding.

## Dynamic Scoping
With dynamic scoping, the current binding for a name is the one most recently encountered during execution. That is, scope becomes temporal rather than spatial.

Dynamic scopes tend to require significant run time overhead since the runtime system has to keep track of names in a structure (referencing environment) that can be searched at run time to find the desired entity. There are two kinds of structure typically used to manage such scoping:
- [[Association lists]]
- [[Central reference tables]]