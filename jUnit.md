## jUnit Test Framework


### jUnitCore:

* Parse the arguments passed in
* Create a listener and add it to notifier object
* Call to jUnitCommandLineParseResult Class to parse command line arguments
* call to jUnitCommandLineParseResult Class to create a request.
* Call to Request class to get a runner
* After getting a runner object, the run method is called with the runner object.

jUnitCommandLineParseResult Class:

* Parses the command line arguments and gets the list of classes to run.
* A request is created using all the classes to test.
* Filters are applied to run only specific tests

Request Class:

* A runner class is returned by the getRunner() method in Request class




### Annotations:

Interface: TestClassValidator

Methods in it: validateTestClass(TestClass)


Implementations of Interface:

PublicClassValidator

* Checks if the class is a public class

AnnotationsValidator:

* Has a private variable with testclass, testmethod and testfield validators.


Abstract class: AnnotationValidator

Methods in it: validateAnnotatedClass(TestClass), validateAnnotatedField(FrameworkField), validateAnnotatedMethod(FrameworkMethod)
