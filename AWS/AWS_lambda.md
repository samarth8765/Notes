## AWS lambda server
- Amazon Web Services (AWS) Lambda is a serverless computing platform that allows you to run code without having to provision or manage servers. With AWS Lambda, you can upload your code, and the platform takes care of the operational aspects, such as server infrastructure and capacity planning. You only pay for the compute time that you consume, making it cost-effective for small, infrequent, or unpredictable workloads.

- It's a Platform as a service.

- Here serverless does not mean that we do not need a server. Rather now we don't have to maintain the server.

- AWS Lambda supports several programming languages, including Node.js, Java, Python, and C#, and it integrates with other AWS services, such as Amazon S3, Amazon DynamoDB, and Amazon API Gateway, to build serverless applications. You can also use AWS Lambda to run custom logic in response to events, such as changes to data in an S3 bucket or a new record in a DynamoDB table. This allows you to build scalable and highly available systems that respond to events in real-time.

- Some advantages of AWS lambda server -
    - Sever and OS maintainence.
    - High availability and automatic scaling
    - Deployment of code.

- You pay only for the compute time you consume - No charge when your code is not running.

-  We cannot log into compute instances or customize the OS or language runtime. If a user wants to manage their compute, they can use EC2 or Elastic Beanstalk.

## Lambda function in Lamdba server
- A Lambda function is the code that runs on an AWS Lambda server. It is the basic building block of a serverless application on the AWS platform. You write a Lambda function in one of several supported programming languages, such as Node.js, Python, Java, or C#. You then upload the code to the AWS Lambda service, where it can be executed in response to specific events or triggers.

- AWS Lambda triggers are events that cause your Lambda function to run. When a trigger event occurs, AWS Lambda executes your function and provides it with the event data. There are several types of triggers that you can use with AWS Lambda, including:

    - API Gateway: You can trigger your Lambda function to run when a client makes a request to an API Gateway endpoint.

    - S3: You can trigger your Lambda function to run when an object is created or deleted in an Amazon S3 bucket.

    - DynamoDB: You can trigger your Lambda function to run when an item is added, updated, or deleted in a DynamoDB table.

    - Kinesis: You can trigger your Lambda function to run when data is added to a Kinesis stream.
 
    - CloudWatch Events: You can trigger your Lambda function to run based on events from Amazon CloudWatch, such as a scheduled event or a change to the state of another AWS resource.

    - SNS: You can trigger your Lambda function to run when a message is published to an Amazon SNS topic.

- By using triggers, you can build event-driven applications that automatically respond to events as they occur, without the need for manual intervention. This makes it easier to build scalable, highly available, and responsive systems.

- Lambda functions can be triggered by a variety of events, such as a new file uploaded to an Amazon S3 bucket, a new record added to a DynamoDB table, or a request to an API Gateway endpoint. When a trigger event occurs, AWS Lambda runs your function, passing it the event data. Your function can then use the event data to perform some action, such as reading or writing data to a database, processing data, or sending an email.

- AWS Lambda automatically manages the underlying server infrastructure, including the deployment and scaling of servers, so you can focus on writing and deploying your code. With AWS Lambda, you only pay for the compute time that your code actually consumes, making it a cost-effective solution for small, infrequent, or unpredictable workloads.

- Lambda functions can be used to build complex, event-driven applications that integrate with other AWS services, such as Amazon S3, Amazon DynamoDB, and Amazon API Gateway, to provide scalable, highly available, and responsive systems.

## Need of Lambda functions in Lambda server
- Lambda functions are an essential part of the AWS Lambda serverless computing platform. They provide a way to execute code in response to specific events or triggers, without having to manage the underlying server infrastructure. The need for Lambda functions in the AWS Lambda server can be summarized as follows:

    - Event-driven computing: With Lambda functions, you can build event-driven applications that automatically respond to events as they occur, without the need for manual intervention. This makes it easier to build scalable, highly available, and responsive systems.

    - Cost savings: By using Lambda functions, you only pay for the compute time that your code actually consumes, so you can save money compared to traditional server-based computing, which often requires you to pay for provisioned capacity even when it's not being used.

    - Scalability: AWS Lambda automatically scales your application to meet demand, so you don't have to worry about capacity planning or resource allocation.

    - Flexibility: You can run your code in response to many different types of events and triggers, and you can use it to build complex applications that integrate with other AWS services.

    - Simplicity: By eliminating the need to manage servers, serverless computing with AWS Lambda can simplify your application development and deployment process, allowing you to focus on writing and deploying code, rather than managing infrastructure.

    - Overall, Lambda functions are a key component of the AWS Lambda serverless computing platform, providing a flexible and cost-effective way to execute code in response to events and triggers.

## Important terms used in Lambda server -
- __Lambda Function__ (discussed above)

- __Runtime__ - Lambda runtime allows functions in different languages to run in execution enviroment. It sits between the lambda service and your function code.

- __Event__ - It is a JSON formatted document that contain data to process.An "event" in AWS Lambda refers to the input data that triggers a Lambda function execution. The data can come from various sources, including an HTTP request, changes to a file in AWS S3, a message from Amazon SNS, and many others. The event is passed to the Lambda function as an argument, which the function can then use to process the event and return a response. The event object contains information about the triggering event, including any associated data and metadata.

- __Event source/ trigger__ - An "event source" in AWS Lambda refers to the service or application that invokes a Lambda function. Some examples of event sources in AWS Lambda include:

    - Amazon S3 bucket: a Lambda function can be triggered when a new object is added to an S3 bucket
    - Amazon API Gateway: a Lambda function can be used to process HTTP requests from an API Gateway
    - Amazon SNS: a Lambda function can be triggered when a message is sent to an SNS topic
    - Amazon DynamoDB: a Lambda function can be triggered when an item is added, updated, or deleted in a DynamoDB table
    - Amazon Kinesis: a Lambda function can be triggered when new data is added to a Kinesis stream
    - By using different event sources, you can create a variety of serverless applications and microservices with AWS Lambda.

- Let us understand event and event source with an example - 
    - Event source: Amazon S3 bucket
    - Event: An object creation event, which is generated when a new object is added to an S3 bucket.

    - The S3 bucket is the event source, and when a new object is created, it generates an event. The event is then passed to the Lambda function, which processes the event and performs its operations.

    - Here's how it works:
    - A user uploads a new file to an S3 bucket
    - The S3 bucket generates an object creation event
    - The event is passed to the Lambda function as an argument
    - The Lambda function processes the event and performs its operations, such as resizing the image, creating a thumbnail, or storing the data in a database.
    - In this example, the event source is Amazon S3, and the event is the object creation event that is triggered when a new object is added to the S3 bucket. The Lambda function processes the event and performs its operations.

- __Downstream resource__ - a downstream resource is any resource that is dependent on the output of a Lambda function. For example, a Lambda function might write data to an S3 bucket or write a message to an SNS topic, both of which would be considered downstream resources. These resources can be impacted by the execution of the Lambda function and may require additional permissions or configurations in order to function properly.

- __Concurrency__ - Concurrency in AWS Lambda refers to the number of instances of a Lambda function that are executing simultaneously. By default, Lambda automatically scales the number of instances based on incoming requests. If your function is processing a high volume of requests, multiple instances of the function can be executing in parallel.

- Concurrency can be managed in several ways in Lambda:

- You can set a concurrent execution limit to control the maximum number of instances of your function that can run at the same time.
- You can reserve concurrency, which allows you to ensure that a specified number of instances of your function are available to process requests, even if the default limit would otherwise prevent it.
- You can also adjust the default account-level concurrency limit if necessary.
Managing concurrency in Lambda can help you control costs, ensure predictable performance, and avoid overloading dependent resources (such as databases).

- To understand more about Lambda server, let us discuss some differences between AWS Lambda and AWS EC2 - 

<table>
  <tr>
    <th>AWS EC2</th>
    <th>AWS LAMBDA</th>
  </tr>
  <tr>
    <td>1- AWS lamda is a PaaS.</td>
    <td>1- AWS EC2 is a IaaS.</td>
  </tr>
  <tr>
    <td>2- It supports Limited Languages like 
    NodeJs, GO, Java etc</td>
    <td>2- No enviroment resriction, you can run any code or language.</td>
  </tr>
    <tr>
    <td>3- We can directly push our code in lambda function</td>
    <td>3- In EC2, first we have to select the OS, install all dependencies and then we can run our code.</td>
  </tr>
    <tr>
    <td>4- In lambda server, we only have to pay for the time the code is executed.</td>
    <td>4- In EC2 we have to pay until our instance is stopped or terminated. Suppose, our code is not running on our instance but instance is running on AWS, so we pay charge for running the instance. </td>
  </tr>
</table>


