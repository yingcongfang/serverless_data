# Serverless Data Pipeline with AWS

This project builds a serverless data pipeline using the AWS Lambda function. 

## Workflow
* the CloudWatchEvents will call the producer function every minute.
The producer function is going to extract the data from the DynamoDB. This project 
will extract the names of companies. 
* The producer will send the data to AWS SQS. 
* The SQS will invoke the consumer function. The consumer function
will get the data from SQS and send the AWS Comprehend service. This service will
identify the critical information for the data and get the sentiment of the data. 
* The consumer function will save the results from the Comprehend service to S3.

## Diagram
![alt text](https://camo.githubusercontent.com/bb29cd924f9eb66730bbf7b0ed069a6ae03d2f1a/68747470733a2f2f757365722d696d616765732e67697468756275736572636f6e74656e742e636f6d2f35383739322f35353335343438332d62616537616638302d353437612d313165392d393930392d6135363231323531303635622e706e67)

## Reference
Source code:https://github.com/noahgift/awslambda

## Common Pitfalls
* AWS Educate Account can't do this project. There is limit permission for that account.
* Create IAM role for Lambda function before creating the function
* Before deploy the Lambda function, download all the requirements in the venv.
