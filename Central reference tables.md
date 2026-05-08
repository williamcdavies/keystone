---
tags:
  - CS326
---
A central reference table is a linked [[Lists|List]] in which each list element comprises a key and multiple linked values. When used as a referencing environment, a central reference table subscribes to the following ruleset:
- When entering a scope, push an entity descriptor onto each chain corresponding to each name defined in the scope.
- When leaving a scope, pop the relevant entity descriptors.
- When looking up a name, do constant-time hashtable lookup.