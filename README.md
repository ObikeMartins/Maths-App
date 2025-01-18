# AWS Web Application for Simple Maths Calculations

## Overview
This project demonstrates how to build and deploy a serverless AWS web application for performing simple mathematical calculations using various AWS services.

## AWS Services Used
- **AWS Amplify** – Hosts the static web page.
- **AWS Lambda** – Executes mathematical operations.
- **Amazon API Gateway** – Invokes the Lambda function.
- **Amazon DynamoDB** – Stores calculation results.
- **AWS IAM** – Manages permissions.

## Project Steps

### 1. Hosting the Web Page with AWS Amplify
1. Create an `index.html` file with basic HTML for the web app.
2. Zip the `index.html` file.
3. Navigate to **AWS Amplify** on the AWS Console.
4. Create a new Amplify app.
5. Upload the zipped `index.html` file and deploy.
6. Open the hosted link to verify successful deployment.

### 2. Creating the Lambda Function
1. Navigate to **AWS Lambda**.
2. Create a new function and select **Python 3.9** as the runtime.
3. Paste the Python script for performing mathematical operations.
4. Save and test the function with a sample event.
5. If the response includes a status code `200`, the function is working correctly.

### 3. Integrating API Gateway
1. Navigate to **Amazon API Gateway**.
2. Create a **REST API**.
3. Add a new method and select **POST**.
4. Link it to the Lambda function.
5. Enable **CORS** (Cross-Origin Resource Sharing).
6. Deploy the API and copy the **Invoke URL**.
7. Test the API by sending a request with a sample mathematical operation.

### 4. Storing Results in DynamoDB
1. Navigate to **Amazon DynamoDB**.
2. Create a new table with `ID` as the partition key.
3. Copy the **Table ARN**.
4. Update the Lambda function permissions:
   - Go to the **Configuration** tab.
   - Select **Permissions** and edit the **Execution Role**.
   - Add an **Inline Policy** granting access to the DynamoDB table.
5. Modify the Lambda function to store results directly in DynamoDB.
6. Test the Lambda function and verify results in DynamoDB.

### 5. Connecting API to Frontend
1. Update the `index.html` file to call the API Gateway.
2. Zip the updated `index.html` file.
3. Redeploy the zipped file via **AWS Amplify**.
4. Open the hosted web page and test the application.

## Testing the Application
1. Enter a mathematical expression in the web page.
2. Submit the request to invoke the API Gateway.
3. The Lambda function computes the result and stores it in DynamoDB.
4. The response is displayed on the web page.

## Conclusion
This project demonstrates how to build an end-to-end AWS web application using a serverless architecture. The app leverages AWS Amplify for hosting, AWS Lambda for execution, API Gateway for routing, and DynamoDB for storage. The result is a scalable, cost-effective, and fully managed cloud solution for performing simple mathematical operations.
