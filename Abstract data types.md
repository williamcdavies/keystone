---
tags:
  - CS302
---
Abstract data types enable us to separate how we use [[Data structures]] in a program from the particular implementation of the data structures themselves.

Abstract data types address a particularly dangerous problem: clients making assumptions about the type's internal representation.

## What Abstraction Means
Abstract data types are an instance of a general principle in [[Software engineering]], which goes my many names with different shades of meaning:
- [[Abstraction]]: Omitting or hiding low-level details with a simpler, higher-level idea. 
- [[Modularity]]: Dividing a system into components or modules, each of which can be designed, implemented, tested, reasoned about, and reused separately from the rest of the system.
- [[Encapsulation]]: Building walls around a module to restrict the modules responsibility to its own internal behaviour so that unrelated behaviour cannot damage its integrity.
- [[Information hiding]]: Hiding details of a module's implementation from the rest of the system, so that those details can be changed later without changing the rest of the system.
- [[Separation of concerns]]: Making a feature (or "concern") the responsibility of a single module, rather than spreading it across multiple modules.

## Classifying Types & Operations
Types, whether built-in or user-defined, can be classified as mutable or immutable.

The operations of an abstract type are classified as follows:
- [[Creators]] create new objects of the type. A creator may take an object as an argument, but not an object of the type being constructed.
- [[Producers]] create new objects from old objects of the type. The concat method of String, for example, is a producer; it takes two strings and produces a new one representing their concatenation.
- [[Observers]] take objects of the abstract type and return objects of a different type. The size method of List, for example, returns an int.
- [[Mutators]] change objects. The add method of List, for example, mutates a list by adding an element to the end.

---
## References
[Software Construction | Reading 8: Abstract Data Types](https://web.mit.edu/6.005/www/fa14/classes/08-abstract-data-types/#reading_8_abstract_data_types)