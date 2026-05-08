---
tags:
  - CS477
aliases:
  - Prefix code
---
A prefix code is a type of code system distinguished by its possession of the "prefix property" which requires that there is no whole code word in the system that is a prefix of any other code word in the system. It is trivially true for fixed-length codes, so only a point of consideration for variable-length codes.

For example, a code with code $\{ 9, 55 \}$ has the prefix property; a code consisting of $\{ 9, 5, 59, 55 \}$ does not, because "$5$" is a prefix of "$59$" and also of "$55$".