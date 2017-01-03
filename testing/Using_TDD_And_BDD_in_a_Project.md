## Using TDD and BDD in a Project

#### Top Down Design

* Write BDD Gherkin files to describe the expected functionality of the product. This will give a help level understanding of what a product should do.
* Write low level unit tests for a feature/functionality to drive development following TDD approach.

#### Bottom Up Implementation

* Develop the feature/functionality using `Red-Green-Refactor` approach and make all the written tests pass.
* Once the feature/functionality is implemented, write the implementation for the BDD scenarios and check the expected behavior is met.
* Iterate the same for all other features.