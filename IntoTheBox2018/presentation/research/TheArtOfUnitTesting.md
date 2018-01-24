# "The Art of Unit Testing with examples in C#, Second Edition" by Roy Osherove (Manning, 2014)

## Preface
Unit Tests should be
1. maintainable
2. readable
3. trustworthy

## Chapter 1 - The Basics of Unit Testing
1.2 - Properties of a good unit test
* automated and repeatable
* easy to implement
* relevant tomorrow
* run w/button push
* run quickly
* consistent in results
* have full control of unit under test
* fully isolated and independent of other tests
* when it fails, expectation and how to debug should be clear

1.3 - Integration Tests are tests of a unit w/o having full control over it and using external dependencies such as database or file system

1.3.1 
* Many developers fear changing Legacy Code for fear of not knowing what other code depends on what they're changing ... If you knew you weren't breaking anything, you'd be much less afraid of changing unfamiliar code because you have the safety net of unit tests.
* Legacy Code is "code that has no tests" - "Working Effectively with Legacy Code" by Michael Feathers (Prentice Hall, 2004)
