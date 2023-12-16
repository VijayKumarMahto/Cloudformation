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
