# POC for Manual Setup of Instance for Employee API 
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Shantanu | 12-01-2024 | 13-01-2024   |         v1     |     Shantanu    |
***

# Table of Content
[1. Introduction](#introduction)

[2. Pre-requisites](#pre-requisites)

[3. Setting Up Instance](#setting-up-instance)

[4. Conclusion](#conclusion)

[5. Contact Information](#contact-information)

[6. Refrences](#references)
***

# Introduction
This Proof of Concept (POC) guide outlines the step-by-step process for creating an EC2 (Elastic Compute Cloud) instance in Amazon Web Services (AWS) for hosting Employee API. EC2 instances serve as virtual servers in the AWS cloud, providing scalable compute capacity. Below is a high-level guide to help you get started. Please note that the specifics may vary based on your application requirements and preferences.
***

# Pre-requisites

| **Prerequisite**                    | **Description**                                                                                     |
|-------------------------------------|-----------------------------------------------------------------------------------------------------|
| AWS Account                         | Ensure you have an active AWS account for creating instance.                                        |

***

# Setting Up Instance
### AWS Account Setup

* If you don't have an AWS account, sign up for one on the AWS Console.
* Create an IAM user with the appropriate permissions for managing resources.

### Network Setup Overview

* Create a VPC to isolate your network resources with a specific CIDR. In this case, the CIDR for the VPC is 10.0.0.0/24.
* Next, create public and private subnets with the specified CIDRs as mentioned in the diagram.
* Then, create public and private route tables to route traffic into the subnets, and configure security groups to restrict traffic to the instances.
* Proceed to create an Internet Gateway (IGW) and attach it to the VPC to allow traffic into the VPC and public subnet through the public route table.
* Finally, create a Network Address Translation (NAT) gateway and attach it to the public subnet to allow traffic into the subnet through the private route table.

![Screenshot 2024-02-14 at 10 19 42 PM](https://github.com/avengers-p7/Documentation/assets/156056364/35f34a5a-2501-4d43-86ba-a3ae7b480411)


### Set Up EC2 Instances

* Launch EC2 instances for Employee API servers in side a private subnet and choose the appropriate instance type, such as t2-micro or t2-medium.
* Configure security groups to restrict traffic to the EC2 instances, and create key pairs for accessing the EC2 instances.

![Screenshot 2024-02-14 at 10 27 35 PM](https://github.com/avengers-p7/Documentation/assets/156056364/9dbc90bc-e8f9-4e6b-8eb1-6bd7cbc644f8)

***

# Conclusion
This POC demonstrates the process of creating an EC2 instance in AWS for hosting Employee API. Adjustment of parameters and settings based on specific requirements and preferences could be made.
***

# Contact Information
| Name | Email Address |
| ---- | ------------- |
| Shantanu  | shantanu.chauhan.snaatak@mygurukulam.co |
***

# References
| Source | Description  | 
| -------- | ------- | 
| https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Employee_API/README.md| Employee API |







