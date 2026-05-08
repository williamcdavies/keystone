---
tags:
  - CS426
---
These are some of the acceptance tests mentioned in the previous chapter. Generally they are written against individual components of the system. The components of the system encapsulate the business rules, so the tests for those components are the acceptance tests for those business rules.

A component test wraps a component. It passes input data into the component and gathers output data from it. It tests that the output matches the input. Any other system components are decoupled from the test using appropriate mocking and test-doubling techniques.

Component tests are written by QA and Business with assistance from develop- ment. They are composed in a component-testing environment such as FitNesse, JBehave, or Cucumber. (GUI components are tested with GUI testing environ- ments such as Selenium or Watir.) The intent is that the business should be able to read and interpret these tests, if not author them.

Component tests cover roughly half the system. They are directed more towards happy-path situations and very obvious corner, boundary, and alternate-path cases. The vast majority of unhappy-path cases are covered by [[Unit tests]] and are meaningless at the level of component tests.