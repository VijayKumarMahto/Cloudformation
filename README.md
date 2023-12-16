# 1. AWS Cloudformation using S3 and EC2 instance

**Introduction**
This README provides comprehensive guidance for setting up an AWS CloudFormation stack to create an S3 bucket and an EC2 instance.
AWS CloudFormation is a vital tool in the AWS arsenal, offering Infrastructure as Code (IaC) capabilities. This service enables the seamless creation and management of AWS resources through code, enhancing consistency and automation. In this overview, we'll delve into using CloudFormation to set up an S3 bucket and an EC2 instance.

#  **Prerequisites**
+ AWS Account:
+ Ensure you have an active AWS account with the necessary permissions to create resources.
+ AWS CloudFormation:
+ Utilize the AWS CloudFormation service for infrastructure provisioning.
  
**New Stack Creation:**

+ Initiate the creation of a new stack to manage resources efficiently.
+ Template Upload:
+ Upload the provided YAML template file to define the infrastructure.
#  Stack Creation Steps
1. Choose CloudFormation
Log in to your AWS account and navigate to the AWS Management Console.
Access the CloudFormation service.
2. Create new Stack
Click on "Create Stack" to start the stack creation process.
Choose "With new resources (standard)" for this setup.
Click "Next" to proceed.
3. Use Template Ready
Select "Upload a template file" and upload the YAML template provided.
4. Create Stack ID
After successfully  template upload, a unique stack ID will be generated, for example:
ruby
Copy code
'[arn:aws:cloudformation:us-east-2:185994111:stack/cf-vijay/48408830-9ade-11ee--0691b6c95ecb]'
**YAML Template Overview**
**S3 Bucket**
```
Type: 'AWS::S3::Bucket'
Properties:
BucketName: 'dev-cloud-formation-bucket'
```
This section defines the creation of an S3 bucket with the specified name.

**EC2 Instance**
```
Type: 'AWS::EC2::Instance'
Properties:
InstanceType: t2.micro
ImageId: ami-06d4b7182ac3480fa
SecurityGroupIds:
sg-0b13d0c6b576a5666
SubnetId: subnet-010c9c784f67e5867
```
This part outlines the configuration of an EC2 instance, specifying its type, Amazon Machine Image (AMI), security groups, and subnet.

# **Stack Initialization and Resource Access**
Upon initiating the stack creation, AWS CloudFormation will orchestrate the provisioning of the S3 bucket and EC2 instance.

To access resources:

# Navigate to the AWS CloudFormation service.
Go to the "Resources" tab to find the URL (physical ID) alongside the logical ID.


# 2. GitLab CI/CD YAML Configuration Explanation:
yaml code
```
stages:
    - build
    - test
    - deploy
```
In this section, we define the stages of your CI/CD pipeline. The stages keyword specifies the order in which the jobs will be executed. In this case, it's build first, then test, and finally deploy.

yaml code
```
build-my-first-internship-job:
    stage: build
    script:
        - echo "this is first build job."
```
Here, we define a job named build-my-first-internship-job within the build stage. The script section contains the commands that will be executed during this job. In the provided example, it simply echoes a message, but in a real-world scenario, you would include commands to install dependencies, compile code, or generate artifacts.

yaml code
```
test-my-first-internship-job:
    stage: test
    script:
        - echo "this is first test job."
```
Similar to the build job, this configuration sets up a job named test-my-first-internship-job within the test stage. The script section contains commands related to testing our application. we should replace the echo statement with actual commands to run your test suite.

yaml code
```
deploy-first-internship-job:
    stage: deploy
    script:
        - echo "this is deploy first job."
```
In the deploy stage, we have a job named deploy-first-internship-job. This job's script section contains commands that are executed during the deployment process. Replace the echo statement with the actual deployment commands, such as copying files to a server, updating configurations, and restarting services.

This project employs GitLab CI/CD to automate the development workflow. The CI/CD pipeline comprises three stages: `build`, `test`, and `deploy`.

<img width="1161" alt="image" src="https://github.com/VijayKumarMahto/Devops-SCH/assets/98145692/2ed030f1-684b-484b-af5d-569ea445c617">

**Build Jobs**

+ Running with gitlab-runner 16.6.0~beta.105.gd2263193 (d2263193)
  on blue-3.saas-linux-small-amd64.runners-manager.gitlab.com/default zxwgkjAP, system ID: s_d5d3abbdfd0a
  feature flags: FF_USE_IMPROVED_URL_MASKING:true
+ Preparing the "docker+machine" executor
00:19
+ Preparing environment
00:05
+ Getting source from Git repository
00:01
+ Executing "step_script" stage of the job script
00:01
+ Cleaning up project directory and file based variables

****


# 3. AWS Lambda Function Configuration:
+ Go to the AWS Lambda Console.
+ Create a new Lambda function.
+ Upload the deployment_package.zip as the deployment package.
+ Set the handler to lambda_function.lambda_handler (assuming your function is in a file named lambda_function.py).
Now, your Lambda function is configured with the required dependencies. When triggered, it will execute the lambda_handler function from your lambda_function.py file.


**AWS Lambda Console:**

Access the AWS Lambda Console from the AWS Management Console.
Create Function:

Create a new Lambda function.
Specify the runtime as Python and upload the deployment package (ZIP file) when prompted.
Handler Configuration:

Set the handler to the entry point of your code. For a Python Lambda function, it is specified as filename.function_name.
**Event Sources:**

Invocation:

Lambda functions can be invoked synchronously or asynchronously based on the type of event source.
The handler function specified during configuration is the entry point for Lambda execution.
By following these steps, you create a scalable and serverless architecture using AWS Lambda for your Python code. The serverless approach allows you to focus on your code and application logic without managing infrastructure.
```
import json

def lambda_handler(event, context):
    return {
        'statusCode': 200,
        'body': json.dumps('my first internship')
    }
```

<img width="1282" alt="image" src="https://github.com/VijayKumarMahto/Devops-SCH/assets/98145692/c01be571-b0ae-4898-b5ca-327578c33b82">

