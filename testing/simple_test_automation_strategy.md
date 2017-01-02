
## Test Automation Strategy

Below is a simple test automation strategy with core principles, practices and smells that can be applied to your project. This is obtained from `Xunit Test Patterns` book. The strategy is divided into five parts:

* Development Process: How the process followed for development affects the testing
* Customers Tests: It will give a clear representation of how the product should like
* Unit Tests: Helps to develop the design incrementally and helps to tests the code thoroughly.
* Design for Testability: The patterns that make the design easy to test and reduce the cost for test automation.
* Test Organization: How the testmethods and testclasses can be organized?

### Development Process:

* `Writing tests first` has many advantages. It gives us a agreed upon definition of what success looks like
* `TDD` helps to develop the design of the software incrementally.
* It also helps to test the business logic without depending on the database layer.

### Customer Tests:

* Writing customer tests first will gives us a definition of how the product should look like.
* Then they can be automated using `scripted tests` or `data-driven tests`. `Scripted tests` are hand written scripts to test the functionality of SUT. `Data-driven tests` are used to avoid duplication. When you have a set of tests which differ only with the input passed to it, then you can use `data-driven tests`. `Recorded tests` can also be used for automating the tests, if you are refactoring a existing application.
* Customers tests can become too long and `obscure` and tend to not provide very good `Defect localization`. This should be avoided.
* Well written tests can also act as documentation for the product.
* Every tests should have a `Fresh Fixture` before its run, which will avoid `Interacting tests`.
* The dependency of tests on other applications can be removed by using `Test doubles`.

### Unit Tests:

* Unit tests can be effective only if it is fully automated.
* A Test case should only test a single condition in the SUT to provide `Defect Localization`.
* A Test case should clearly describe the four phases(Setup, Exercise, Verify, Teardown) to act as documentation for the product.
* A delegated setup or teardown should have descriptive names for the methods.
* Each test should be self checking test. In-built assertion checks can be used to do self-checking. If multiple tests share the same assertion check, it can be delegated to a method with a descriptive name.
* `Indirect inputs` to a SUT can be tested using `Stubs` and `indirect outputs` to a SUT can be tested using `Mocks`.

### Design for testability

* Using TDD, you can develop a design which can be easily testable. Following a layered architecture will help to test the product in a much better way. The dependencies can be replaced with `Test Doubles` to avoid slow tests because of Disk I/O or Network requests.

### Test Organization

* When the number of tests become very large, it becomes very difficult to maintain the tests properly. The tests can be organized using a `Test Class per fixture` or `Test Class per feature`. `Test class per feature` will allow to declare the setup for the fixture at one place.