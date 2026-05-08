---
tags:
  - CS326
---
An association [[Lists|List]] is a linked list in which each list element comprises a key and a value. When used as a referencing environment, an association list subscribes to the following ruleset:
- When entering a scope, push its bindings on the list.
- When leaving a scope, pop its bindings off the list.
- When looking up a name, traverse the list.