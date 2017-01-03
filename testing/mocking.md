## Test Doubles

There are four types of test doubles

* Dummy Object
* Stubs
* Mocks
* Fake Object

#### Dummy Objects

* The Dummy Objects are used when there is a requirement for a object(will call it first object) to exist to create a different object(Will call it second object). The only purpose of the first object is for creating the second object. If instantiating the first object is expensive, then a `Dummy Object` can be used in its place. The `Dummy Objects` act as `placeholders`.

#### Stubs

* The inputs to a SUT can come from other forms different from the input parameters. They can be from other objects. If the SUT calls another object and decides the next action based on the outcome of the call to the other object, then the SUT is said to be getting input from the other object. If instantiating the other object is a expensive operation, then you can use `stubs`.

* `Test Spy` can be used to spy an object and verify a certain operation is performed on a object. It can be used to verify `indirect outputs`.

#### Mocks

* The `Mocks` can perform both operations which `Stubs` and `Test Spys` perform.

#### Fake Object

* `Fake Object` can be used to instantiate a simpler version of a object rather than a real expsenive one.


## Mocking

### Mockito

* [A Mocking Framework in Java](http://site.mockito.org/)

### Mock Server

* [A Mocking Framework for http/https servers.](http://www.mock-server.com/)

