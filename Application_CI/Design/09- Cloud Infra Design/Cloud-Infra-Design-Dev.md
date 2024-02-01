# Cloud Infra Design Dev

| **Author**           | **Created On** | **Last Updated** | **Document Version** |
| -------------------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 29-01-2024     | 29-01-2024       | V1                   |

# Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Cloud Infra Design Dev Details](#cloud-infra-design-dev-details)
4. [Infrastructure Diagram](#infrastructure-diagram)
5. [Contact Information](#contact-information)
6. [Resources and References](#resources-and-references)

***
# Introduction

The Cloud Infra Design Dev documentation provides an in-depth overview of the development infrastructure hosted on AWS for the OT-Microservices project. This modern and modular architecture prioritizes scalability and efficiency, utilizing AWS services to establish a reliable, scalable, and high-performance foundation.

***
# Prerequisites
| Tool                  | Description                                  |
|-----------------------|----------------------------------------------|
| AWS Management Console | Required for provisioning AWS resources.     |


***
# Cloud Infra Design Details

To create the infrastructure, I used the following services on AWS and implemented them in Production, Development, and Quality Assurance.

| Service         | Item                  | Description                                         |
|-----------------|-----------------------|-----------------------------------------------------|
| **Region**      | **Europe**            |           Frankfurt (eu-central-1)                  |
| **Availability Zone**          | **eu-central-1a**         | Primary availability zone for the region. |
| **VPC**         | **OT-Micro-Dev-Vpc**      | VPC for Development Infrastructure              |
| **Subnets**     | **Public Subnet-1**   | Hosts the Bastion Host for secure access.           |
|                 | **Private Subnet-1**  | Hosts the Frontend application components.         |
|                 | **Private Subnet-2**  | Hosts the Attendance, Employee, and Salary APIs.    |
|                 | **Private Subnet-3**  | Hosts PostgreSQL, Scylla, and Redis databases.      |
| **Route Table**  | **Public-rt**        | Associates with Public Subnet-1 for internet access.|
|                 | **Private-rt**       | Associates with Private Subnet-1, Subnet-2, and Subnet-3.|
| **Internet Gateway** | **Igw**              | Internet Gateway for OT-Micro-Dev-Vpc.           |
| **NACL**        | **Nacl-1**           | Associates with Private Subnet-1.                  |
|                 | **Nacl-2**           | Associates with Private Subnet-2.                  |
|                 | **Nacl-3**           | Associates with Private Subnet-3.                  |
| **Security Groups** | **Bastion-sg**    | Security Group for Bastion.                       |
|                 | **Frontend-sg**      | Security Group for Frontend.                       |
|                 | **ATT-sg**           | Security Group for Attendance API.                 |
|                 | **EMP-sg**           | Security Group for Employee API.                   |
|                 | **Sal-sg**           | Security Group for Salary API.                     |
|                 | **PSql-sg**          | Security Group for PostgreSQL.                     |
|                 | **Scylla-sg**        | Security Group for Scylla database.                |
|                 | **Redis-sg**         | Security Group for Redis database.                 |
| **NAT Gateway** | **ALB**              | NAT Gateway for private subnet internet access.|
| **Application Load Balancer** | **ALB** |ALB for Frontend Traffic Distribution| 
| **Auto Scaling Group**         | **ASG**           | Auto Scaling Group responsible for dynamically adjusting the number of instances for the frontend and API services based on demand. | 

***

# Infrastructure Diagram

![Cloud-Infra-30k feet - Page 1 (1)](https://github.com/avengers-p7/Documentation/assets/156056709/cb77bbe7-3aab-4b12-81db-a107e11f16ab)



**Description**

* Users connect to the environment through the internet.
* Traffic is directed through public subnets and security groups.
* Private components have internet access via the NAT gateway.
* Secure access to private resources is facilitated by bastion instances.
* Architecture includes central, AWS cloud, network, security, and application components.
* Components are deployed within Virtual Private Clouds (VPCs).
* Overview offers insights into connectivity and interactions within the development environment.


***

# Contact Information

| Name               | Email Address                               |
| ------------------ | ------------------------------------------- |
| Parasharam Desai   | parasharam.desai.snaatak@mygurukulam.co     |

***
# Resources and References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|     Documentation Template       | https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template |
