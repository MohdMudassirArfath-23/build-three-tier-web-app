# Fetch Data with AWS Lambda

A serverless AWS project that demonstrates how to fetch user data from an Amazon DynamoDB table using AWS Lambda and expose the data through an Amazon API Gateway REST API.

##  Project Overview

This project demonstrates the implementation of a serverless data-fetching workflow using AWS services. A user sends a request to an API Gateway endpoint, which triggers an AWS Lambda function. The Lambda function retrieves the requested user data from an Amazon DynamoDB table and returns the response through the API.

The project helped me gain practical experience in building and connecting serverless AWS components and understanding how API-driven applications work in a cloud environment.

##  Architecture

```text
                  ┌─────────────────────┐
                  │       Client        │
                  │  Browser / API Tool │
                  └──────────┬──────────┘
                             │
                             │ GET Request
                             ▼
                  ┌─────────────────────┐
                  │    API Gateway      │
                  │     REST API        │
                  └──────────┬──────────┘
                             │
                             │ Triggers
                             ▼
                  ┌─────────────────────┐
                  │    AWS Lambda       │
                  │  Fetch Data Logic   │
                  └──────────┬──────────┘
                             │
                             │ Query
                             ▼
                  ┌─────────────────────┐
                  │   Amazon DynamoDB   │
                  │    User Data        │
                  └──────────┬──────────┘
                             │
                             │ Returns Data
                             ▼
                  ┌─────────────────────┐
                  │    API Response     │
                  └─────────────────────┘
```

##  AWS Services Used

| Service                | Purpose                                                    |
| ---------------------- | ---------------------------------------------------------- |
| **AWS Lambda**         | Executes the serverless function and retrieves user data   |
| **Amazon DynamoDB**    | Stores user information in a NoSQL database                |
| **Amazon API Gateway** | Provides a REST API endpoint to invoke the Lambda function |

## How the Application Works

1. The client sends a **GET request** to the API Gateway endpoint.
2. API Gateway receives the request and invokes the Lambda function.
3. The Lambda function processes the request and identifies the requested user.
4. Lambda queries the user data stored in the DynamoDB table.
5. DynamoDB returns the requested item to Lambda.
6. Lambda sends the retrieved data back through API Gateway.
7. The client receives the user data as an API response.

##  Implementation Steps

### 1. Create a DynamoDB Table

An Amazon DynamoDB table was created to store sample user information.

The table contains user data that can be retrieved using a unique user ID.

### 2. Add Sample User Data

Sample user records were added to the DynamoDB table for testing the application.

### 3. Create an AWS Lambda Function

An AWS Lambda function was created to:

* Receive the user request.
* Retrieve the user ID from the request.
* Query DynamoDB for the requested user.
* Return the retrieved data as a response.

### 4. Create an API Gateway REST API

An Amazon API Gateway REST API was created to provide an HTTP endpoint for accessing the Lambda function.

A **GET method** was configured to handle user data requests.

### 5. Deploy the API

The API was deployed to a production stage, making the endpoint accessible for testing.

### 6. Test the Application

The API was tested by sending a GET request with a user ID and verifying that the correct user data was returned from DynamoDB through Lambda.

##  Project Structure

```text
fetch-data-with-lambda/
│
├── lambda/
│   └── lambda_function.py
│
├── screenshots/
│   ├── dynamodb.png
│   ├── lambda.png
│   ├── api-gateway.png
│   └── api-response.png
│
├── documentation/
│   └── project-documentation.pdf
│
└── README.md
```
##  Project Screenshots

### Amazon DynamoDB

Shows the DynamoDB table containing sample user data.

### AWS Lambda

Shows the Lambda function responsible for retrieving data from DynamoDB.

### Amazon API Gateway

Shows the REST API and GET method used to invoke the Lambda function.

### API Response

Shows the returned user data after successfully calling the API endpoint.

##  Key Learnings

Through this project, I gained practical experience in:

* Building serverless applications using AWS.
* Creating and configuring AWS Lambda functions.
* Working with Amazon DynamoDB and NoSQL data.
* Creating REST APIs using Amazon API Gateway.
* Connecting API Gateway with Lambda.
* Retrieving database data through serverless functions.
* Testing API endpoints and validating responses.
* Understanding event-driven and serverless application architecture.

##  Security Considerations

No AWS credentials, access keys, passwords, or other sensitive information are stored in this repository.

##  Future Improvements

* Add authentication and authorization using Amazon Cognito.
* Implement additional API methods such as POST, PUT, and DELETE.
* Add input validation and improved error handling.
* Add monitoring and logging using Amazon CloudWatch.
* Build a frontend interface to interact with the API.

##  Project Outcome

Successfully built and tested a serverless data-fetching application using **AWS Lambda, Amazon DynamoDB, and Amazon API Gateway**. This project demonstrates how cloud services can be integrated to create a scalable and event-driven application without managing traditional servers.

---

 **If you found this project useful, feel free to explore the repository and connect with me.**
