# POC for Manual Setup of Infra 
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Shantanu | 12-01-2024 | 13-01-2024   |         v1     |     Shantanu    |
***

# Table of Content
[1. Introduction](#introduction)

[2. Pre-requisites](#pre-requisites)

[3. POC](#poc)

[4. Conclusion](#conclusion)

[5. Contact Information](#contact-information)

[6. Refrences](#references)
***

# Introduction
This Proof of Concept (POC) guide outlines the step-by-step process for creating an EC2 (Elastic Compute Cloud) instance in Amazon Web Services (AWS). EC2 instances serve as virtual servers in the AWS cloud, providing scalable compute capacity.
***

# Pre-requisites

| **Prerequisite**                    | **Description**                                                                                     |
|-------------------------------------|-----------------------------------------------------------------------------------------------------|
| AWS Account                         | Ensure you have an active AWS account.                                                              |
| AWS CLI                             | Install the [AWS Command Line Interface](https://aws.amazon.com/cli/).                              |
| Access Key and Secret Key           | Obtain your AWS access key and secret key.                                                          |
***

# POC
## Creating an EC2 Instance in AWS
### Step 1: Configure AWS CLI
Open a terminal and run the following command to configure the AWS CLI with your access key and secret key.
```
aws configure
```
You will be prompted to enter your AWS Access Key ID, Secret Access Key, default region name, and default output format.

### Step 2: Create a Key Pair
You need a key pair to securely connect to your EC2 instance. Run the following command to create a new key pair.
```
aws ec2 create-key-pair --key-name MyKeyPair --query 'KeyMaterial' --output text > MyKeyPair.pem
```
Make sure to set appropriate permissions on the key file.
```
chmod 400 MyKeyPair.pem
```

### Step 3: Launch an EC2 Instance
Now, let's launch an EC2 instance. You can choose an Amazon Machine Image (AMI) based on your requirements. Replace **ami-xxxxxxxxxxxxxxxxx** with your desired AMI.
```
aws ec2 run-instances --image-id ami-xxxxxxxxxxxxxxxxx --instance-type t2.micro --key-name MyKeyPair --tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=MyInstance}]'
```
This command launches a t2.micro instance with the specified AMI, associates the key pair, and tags the instance with a name.

### Step 4: Check Instance Status
You can check the status of your instance using the following command.
```
aws ec2 describe-instances --instance-ids <instance-id>
```
Replace <instance-id> with the actual instance ID obtained from the previous step.

### Step 5: Connect to the Instance
Use SSH to connect to your instance. Replace <instance-public-ip> with the public IP of your instance.
```
ssh -i MyKeyPair.pem ec2-user@<instance-public-ip>
```
You are now connected to your EC2 instance.
***

# Conclusion
This POC demonstrates the process of creating an EC2 instance in AWS using the AWS CLI. Adjustment of parameters and settings based on specific requirements and preferences cpuld be made.
***

# Contact Information
| Name | Email Address |
| ---- | ------------- |
| Shantanu  | shantanu.chauhan.snaatak@mygurukulam.co |
***

# References
| Source | Description  | 
| -------- | ------- | 
| https://devopscube.com/use-aws-cli-create-ec2-instance/ | AWS CLI to Create an EC2 instance |







