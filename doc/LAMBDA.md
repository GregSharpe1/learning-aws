### What is AWS Lambda?

AWS Lambda, is a Serverless concept, that allows developers to upload their code and AWS will take care of the provisioning and managing of the servers that are used to run the code. AWS use a what they call a micro-vm (firecracker) to spin up instances with the correct binaries and so on to create and execute the lambda function. Scaling and patching is also handled by AWS. You can execute a Lambda function in the following ways:

* In response to an event, event-driven compute/architecture is becoming the norm recently. There are a number of services which can trigger a lambda function, placing items into an S3 bucket, changes to a DynamoDB table and via external sources such as an API being hit through AWS API Gateway.

#### What languages are supported with AWS Lambda? (As of July 2019)

* .Net Core 2.1 (C# / Powershell)
* Go 1.x
* Python 3.7
* Python 3.6
* Python 2.7
* Ruby 2.5
* Java 8
* Node.js 8.10
* Node.js 10.x

#### Pricing

* Number of requests
  * First 1 million requests are free. $0.20 per 1 million requests thereafter.

* Duration
  * Duration is calculated from the time your code begins executing until it returns or otherwise terminates, rounded up to the nearest 100ms. Price will also differ depending on the amount of resource given to the Lambda function
  * Charged $0.00001667 for every GB-second used.

#### Why Lambda? Over traditional, always on resources

* No servers to manage
* Continuous scaling
* Cheap!

#### Top tips

* Lambda function cannot execute over 5 minutes in length. (300 seconds)
* If Lambda function does go over the 300 second HARD limit, then the function will have to be split up into multiple functions. Remember functions can call other functions.
* Lambda scales out, not up
* Services that can trigger Lambda function (the ones I know of any way)
  * Lambda (*)
  * CloudWatch
  * SNS
  * S3
  * SQS
  * DynamoDB
  * API Gateway
  * AWS IoT
  * CodeCommit
  * Kinesis
