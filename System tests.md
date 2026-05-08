---
tags:
  - CS426
---
These are automated tests that execute against the entire integrated system. They are the ultimate [[Integration tests]]. They do not test business rules directly. Rather, they test that the system has been wired together correctly and its parts interoperate according to plan. We would expect to see throughput and performance tests in this suite.

These tests are written by the system architects and technical leads. Typically they are written in the same language and environment as integration tests for the UI. They are executed relatively infrequently depending on their duration, but the more frequently the better.

System tests cover perhaps 10% of the system. This is because their intent is not to ensure correct system behavior, but correct system construction. The correct behavior of the underlying code and components have already been ascertained by the lower layers of the pyramid.