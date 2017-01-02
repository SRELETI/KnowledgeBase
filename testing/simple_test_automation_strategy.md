
## Test Automation Strategy

Below is a simple test automation strategy with core principles, practices and smells that can be applied to your project. This is obtained from `Xunit Test Patterns` book. The strategy is divided into five parts:

* How the process followed for development affects the testing
* Customers Tests: It will give a clear representation of how the product should like
* Unit Tests: Helps to develop the design incrementally and helps to tests the code thoroughly.
* Design for Testability: The patterns that make the design easy to test and reduce the cost for test automation.
* Test Organization: How the testmethods and testclasses can be organized?

### Development Process:

* `Writing tests first` has many advantages. It gives us a agreed upon definition of what success looks like
* It helps to develop the design of the software incrementally.
* It also helps to test the business logic without depending on the database layer.

### Customer Tests:

* Writing customer tests will gives us a definition of how the product should look like.
* Then they can be automated using `scripted tests` or `data-driven tests`. `Scripted tests` are hand written scripts to test the functionality of SUT. `Data-driven tests` are used to avoid duplication. When you have a set of tests which differ only with the input passed to it, then you can use `data-driven tests`. `Recorded tests` can also be used for automating the tests, if you are refactoring a existing application.
* Customers tests can become too long and `obscure` and tend to not provide very good `Defect localization`. Well written tests can also act as documentation for the product.
* Every tests should have a `Fresh Fixture` before its run, which will avoid `Interacting tests`.
* The dependency of tests on other applications can be removed by using `Test doubles`.


