# Running AWS Services Locally 

## Overview:

LocalStack provides an easy-to-use test/mocking framework for developing Cloud applications.

## Background:

LocalStack is based on moto library and kinesalite/dynalite (For kinesis/dynamodb resp). So, will talk about them first. 

### Boto Library:

Boto is the AWS Python SDK. 

### Moto Library:

It Mocks boto library. Provides a local implementation of the supported AWS services. Let's take an example to explain this.
import boto3

```python
class MyModel(object):
    def __init__(self, name, value):
        self.name = name
        self.value = value

    def save(self):
        s3 = boto3.client('s3', region_name='us-east-1')
        s3.put_object(Bucket='mybucket', Key=self.name, Body=self.value)
```

Let's say, we want to test the above block of code locally or in CI env.

```python
import boto3
from moto import mock_s3
from mymodule import MyModel


@mock_s3
def test_my_model_save():
	# This will make a call to moto's mock implementation
    conn = boto3.resource('s3', region_name='us-east-1')
    # We need to create the bucket since this is all in Moto's 'virtual' AWS account
    conn.create_bucket(Bucket='mybucket')

    model_instance = MyModel('steve', 'is awesome')
    model_instance.save()

    body = conn.Object('mybucket', 'steve').get()['Body'].read().decode("utf-8")

    assert body == b'is awesome'
```

@mock_s3 is the decorator here. Once, you declare the decorator, everything after it will be automatically mocked and local implementation of AWS services(moto) will be called. 
This is very useful if we want to test python code that uses boto library to access AWS cloud. 

### Language Agnostic Access:

The moto library exposes the mocked implementation using a web server(Flask Server). So, the mocks can be used with the existing aws clients by setting the endpoint to the local implementation.

## LocalStack: 

LocalStack builds on existing best-of-breed mocking/testing tools, most notably kinesalite/dynalite and moto. LocalStack combines the tools, makes them interoperable, and adds important missing functionality on top of them: This page explains the functionality it adds. 

LocalStack has integration with JUnit. It has a JunitTestRunner which will download all the dependencies and setup local AWS env. 

```java
import cloud.localstack.LocalstackTestRunner;
import cloud.localstack.TestUtils;

@RunWith(LocalstackTestRunner.class)
public class MyCloudAppTest {

  @Test
  public void testLocalS3API() {
    AmazonS3 s3 = TestUtils.getClientS3()
    List<Bucket> buckets = s3.listBuckets();
    ...
  }

}
```

```
<dependency>
    <groupId>cloud.localstack</groupId>
    <artifactId>localstack-utils</artifactId>
    <version>0.1.4</version>
</dependency>
```

More Info: https://github.com/localstack/localstack#integration-with-javajunit


### Accessing LocalStack using Existing AWS clients:


#### AWS CLI:

You can point your aws CLI to use the local infrastructure using

```
aws --endpoint-url=http://localhost:4568 kinesis list-streams
{
    "StreamNames": []
}
```
