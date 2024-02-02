# Cloud Infra Design Dev

| **Author**           | **Created On** | **Last Updated** | **Document Version** |
| -------------------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 29-01-2024     | 29-01-2024       | V1                   |
***
# Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Bottom-Up Approach](#bottom-up-approach)
4. [Cloud Infra Design Dev Details](#cloud-infra-design-dev-details)
5. [Infrastructure Diagram](#infrastructure-diagram)
6. [Contact Information](#contact-information)
7. [Resources and References](#resources-and-references)

***
# Introduction

The Cloud Infra Design Dev documentation provides an in-depth overview of the development infrastructure hosted on AWS for the OT-Microservices project. This modern and modular architecture prioritizes scalability and efficiency, utilizing AWS services to establish a reliable, scalable, and high-performance foundation.

***
# Prerequisites
| Tool                  | Description                                  |
|-----------------------|----------------------------------------------|
| AWS Management Console | Required for provisioning AWS resources.     |

***
# Bottom-Up Approach

**Bottom-Up Approach Overview:**

The bottom-up approach involves starting with individual components and gradually building up to the complete system. It's like assembling pieces of a puzzle, focusing on the details and functionalities of each element before combining them into a coherent whole. In our Cloud Infra Design, the bottom-up approach entails understanding the specifics of security groups, subnets, and services before zooming out to see the overall structure.

***
# Cloud Infra Design Dev Details

Here's a flow summary of the infrastructure:

| Aspect                                      | Details                                                                                     |
|---------------------------------------------|-----------------------------------------------------------------------------------------------|
| **User Access**                             | Users connect to the infrastructure through the internet.                                   |
| **Public Subnets**                          | - Public subnets host components that need direct internet access.                           |
|                                             | - The Bastion Host resides in the public subnet to facilitate secure access.                 |
| **Private Subnets**                         | - Frontend application components are hosted in one private subnet.                           |
|                                             | - Attendance, Employee, and Salary APIs are hosted in separate private subnets.               |
|                                             | - PostgreSQL, Scylla, and Redis databases are hosted in another private subnet.              |
| **Security Groups**                         | - Different security groups are defined for various components.                              |
|                                             |   - Bastion-sg for the Bastion Host.                                                        |
|                                             |   - Frontend-sg for Frontend components.                                                     |
|                                             |   - ATT-sg, EMP-sg, and Sal-sg for respective APIs.                                          |
|                                             |   - PSql-sg, Scylla-sg, and Redis-sg for database components.                                |
| **NACLs (Network Access Control Lists)**    | - NACLs are associated with specific private subnets to control inbound and outbound traffic at the subnet level. |
| **Internet Gateway & NAT Gateway**         | - Internet Gateway (Igw) facilitates internet access for the VPC.                            |
|                                             | - NAT Gateway allows instances in private subnets to initiate outbound traffic to the internet. |
| **Route Tables**                            | - Public-rt is associated with the public subnet for internet access.                        |
|                                             | - Private-rt is associated with private subnets, allowing communication within the VPC.      |
| **ALB (Application Load Balancer)**        | - ALB is configured for distributing frontend traffic across multiple targets, ensuring high availability. |
| **Auto Scaling Group (ASG)**               | - ASG dynamically adjusts the number of instances for frontend and API services based on demand. |
| **Region and Availability Zone**           | - The infrastructure is deployed in the Europe region, specifically in the Frankfurt (eu-central-1) region. |
|                                             | - Availability zones (eu-central-1a) are utilized for redundancy and fault tolerance.        |
|                                             | - Availability zones (eu-central-1b) are utilized for redundancy and fault tolerance.        |
| **VPC (Virtual Private Cloud)**            | - Separate VPCs are created for Development, Production, and Quality Assurance environments.  |
|                                             | - This flow summary outlines the path of user access, the organization of components in public and private subnets, the role of security groups, NACLs, internet and NAT gateways, routing, and the use of load balancing and auto-scaling for ensuring scalability and availability of services. |

***
# Infrastructure Diagram

![Cloud-Infra-30k feet - Page 1 (1)](https://github.com/avengers-p7/Documentation/assets/156056709/cb77bbe7-3aab-4b12-81db-a107e11f16ab)

***
# Contact Information

| Name               | Email Address                               |
| ------------------ | ------------------------------------------- |
| Parasharam Desai   | parasharam.desai.snaatak@mygurukulam.co     |

***
# Resources and References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| Documentation Template           | [Documentation Template](https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template) |
| Autoscaling with NGINX on AWS Blog| [NGINX Autoscaling on AWS](https://www.nginx.com/blog/announcing-new-autoscaling-support-with-nginx-plus-on-aws-cloud-quick-start/) |
