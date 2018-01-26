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

1.4 
* Unit Test definition - "A unit test is an automated piece of code that invokes the unit of work being tested, and then checks some assumptions about a single end result of that unit. A unit test is almost always written using a unit testing framework. It can be written easily and runs quickly. It's trustworthy, readable, and maintainable. It's consistent in its results as long as production code hasn't changed."
* Control Flow Code is any piece of code that has some sort of logic in it, small as it may be. It has one or more of the following: an if statement, a loop, a switch, or case statement, calculations, or any other type of decision making code. Properties (getters/setters) are good examples of code that usually don't contain any logic and so don't require specific trageting by tetsts.

1.6 Test Driven Development (TDD)
* Refactoring means changing a piece of code without changing its functionality.

## Chapter 2 - A First Unit Test

2.3.2 
* Test every method with logic even if it simple. Logic can fail and you want to know when it does.
* Since MXUnit and TestBox both require "test" in the name, we should use the following:  
> test[UnitOfWork]_[Scenario]_[ExpectedBehavior]  
for example, for the method isValidFileName(), we could have the following test:
> testIsValidFilename_badExtension_returnsFalse
* The book suggests isolating your tests from your code in a separate project. My experience is that it is easy to keep your tests encapsulated in a tests folder alongside your code which allows you to run your tests as part of a build process and only deploy if all the tests run. And only the code gets deployed, not the tests folder to keep your application clean.

2.3.3 
* MXUnit and TestBox do not have the attribute scheme described in the book that NUnit has, instead, they simply require the keyword "test" in the test name.
* Like NUnit, MXUnit and TestBox both require tests to be public methods

2.4 A unit test usually comprises three main actions:
1. Arrange objects, creating and setting them up as necessary
2. Act on an object
3. Assert that something is expected

2.4.1 The Assert class contains methods you can use to test your code. If the assertion fails, your framework will let you know with a message. Optionally you can tell the Assert class what message to display, but I would highly discourage doing this as the framework's messages are all very good and using it provides a standardized way failures are reported to the developer running the tests. The book makes a strong case discouraging custom messages and suggests if you feel you need to, you probably haven't written a clear enough test name.
