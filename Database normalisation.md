---
tags:
  - CS457
---
Database normalisation is the process of structuring a [[Relational databases|Relational database]] in accordance with a series of so-called normal forms in order to reduce data redundancy and improve data integrity.

## 1NF: First Normal Form
A relation can be said to be in the first normal form if each field is atomic, containing a single value rather than a set of values or a nested table.

## 2NF: Second Normal Form
A relation is in 2NF if it is in 1NF and contains no partial dependencies. A partial dependancy occurs when a non-prime attribute (that ism one not part of any candidate key) is functionally dependent on only a proper subset of the attributes making up a candidate key. To be in 2NF, a relation must have every non-prime attribute depend on the whole set of attributes of every candidate key.

## 3NF: Third Normal Form
A relation is in 3NF if it is in 2NF and also lacks non-key dependencies, meaning that no non-prime attribute is functionally dependent on any other non-prime attribute.