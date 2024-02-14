# Cloud Infra Design Dev

| **Author**           | **Created On** | **Last Updated** | **Document Version** |
| -------------------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 29-01-2024     | 29-01-2024       | V1                   |
***
# Table of Contents

1. [Introduction](#introduction)
2. [Pre-requisites](#pre-requisites)
3. [Infrastructure Diagram](#infrastructure-diagram)
4. [Description](#description) 
5. [Contact Information](#contact-information)
6. [Resources and References](#resources-and-references)

***
# Introduction

The Cloud Infra Design Dev documentation provides an in-depth overview of the development infrastructure hosted on AWS for the OT-Microservices project. This modern and modular architecture prioritizes scalability and efficiency, utilizing AWS services to establish a reliable, scalable, and high-performance foundation.

***
# Pre-requisites
| Tool                  | Description                                  |
|-----------------------|----------------------------------------------|
| AWS Management Console | Required for provisioning AWS resources.     |

***
# Infrastructure Diagram
![Dev-infra - Page 1 (1)](https://github.com/avengers-p7/Documentation/assets/156056709/fbd6ecb7-7246-40a2-b1d3-8a2edc2e1ac0)

![Dev-infra - Page 1 (2)](https://github.com/avengers-p7/Documentation/assets/156056709/6894bfd7-d422-40d2-b9ba-467eacc12387)


---
# Description
| Component                           | Details                                                                                           |
| ----------------------------------- | ------------------------------------------------------------------------------------------------- |
| **User Access**                     | Users connect to the infrastructure through the internet.                                          |
| **Route53**                         | DNS service for routing traffic to various components.                                               |
| **Public Subnets**                  | Public subnets host components requiring direct internet access. Bastion Host facilitates secure access.|
| **Private Subnets**                 | Frontend app, Attendance, Employee, and Salary APIs hosted in separate private subnets. Databases (PostgreSQL, Scylla, Redis) in another private subnet. |
| **Security Groups**                 | - To provide security on instance level |
| **NACLs (Network ACLs)**           | Control inbound and outbound traffic at subnet level for specific private subnets.                  |
| **Internet Gateway & NAT Gateway**  | - Internet Gateway (Igw) for VPC internet access.<br>- NAT Gateway for outbound traffic from private subnets to the internet.|
| **Route Tables**                    | - Public-RT for public subnet internet access.<br>- Private-RT for communication within the VPC.    |
| **ALB (Application Load Balancer)** | Configured to distribute frontend traffic across multiple targets for high availability.            |
| **Auto Scaling Group (ASG)**        | Dynamically adjusts frontend and API service instances based on demand for scalability.              |
| **Region and Availability Zone**    | Deployed in Europe region, specifically Frankfurt (eu-central-1). Utilizes availability zones (eu-central-1a) for redundancy and fault tolerance. |
| **VPC (Virtual Private Cloud)**     | Created for Development environments, organizes components for scalability and availability.        |



# Security Groups and Inbound Rules

| Layer    | Security Group Name | Inbound Rule Port | Inbound Rule Source |
|----------|---------------------|-------------------|---------------------|
| Frontend | Frontend-lb-sg      | 80                | 0.0.0.0/0           | 
| Frontend | Frontend-sg         | 22,80                | frontend-lb-sg      |               
| Backend  | Backend-sg          | 8080              | Backend-sg         |               
| Database | Postgresql-sg      | 5432              | Backend-sg          |               
| Database | Redis-sg         | 6379              | Backend-sg          |            
| Database | Scylla-sg      | 9042              | Backend-sg          |               



# NACL Rules

## Public NACL Inbound Rules

| Rule number | Type      | Protocol | Port range | Source       | Allow/Deny |
|-------------|-----------|----------|------------|--------------|------------|
| 100         | SSH       | TCP      | 22         | 0.0.0.0/0    | Allow      |
| *           | All traffic | All     | All        | 0.0.0.0/0    | Deny       |

## Public NACL Outbound Rules

| Rule number | Type      | Protocol | Port range | Destination  | Allow/Deny |
|-------------|-----------|----------|------------|--------------|------------|
| 100         | SSH       | TCP      | 22         | 10.0.1.0/28  | Allow      |
| 110         | Custom TCP| TCP      | 1024-65535 | 10.0.0.0/28  | Allow      |
| *           | All traffic | All     | All        | 0.0.0.0/0    | Deny       |

## Frontend NACL Inbound Rules

| Rule number | Type      | Protocol | Port range | Source       | Allow/Deny |
|-------------|-----------|----------|------------|--------------|------------|
| 100         | SSH       | TCP      | 22         | 10.0.1.0/28  | Allow      |
| 110         | Custom TCP| TCP      | 3000       | 10.0.1.0/28  | Allow      |
| *           | All traffic | All     | All        | 0.0.0.0/0    | Deny       |

## Frontend NACL Outbound Rules

| Rule number | Type      | Protocol | Port range | Destination  | Allow/Deny |
|-------------|-----------|----------|------------|--------------|------------|
| 100         | SSH       | TCP      | 22         | 10.0.1.0/28  | Allow      |
| 110         | Custom TCP| TCP      | 3000       | 10.0.1.0/28  | Allow      |
| *           | All traffic | All     | All        | 0.0.0.0/0    | Deny       |

## Backend NACL Inbound Rules

| Rule number | Type      | Protocol | Port range | Source       | Allow/Deny |
|-------------|-----------|----------|------------|--------------|------------|
| 100         | SSH       | TCP      | 22         | 10.0.1.0/28  | Allow      |
| 110         | Custom TCP| TCP      | 8080       | 10.0.1.16/28 | Allow      |
| *           | All traffic | All     | All        | 0.0.0.0/0    | Deny       |

## Backend NACL Outbound Rules

| Rule number | Type      | Protocol | Port range | Source       | Allow/Deny |
|-------------|-----------|----------|------------|--------------|------------|
| 100         | SSH       | TCP      | 22         | 10.0.1.0/28  | Allow      |
| 110         | Custom TCP| TCP      | 8080       | 10.0.1.16/28 | Allow      |
| *           | All traffic | All     | All        | 0.0.0.0/0    | Deny       |

## Database NACL Inbound Rules

| Rule number | Type      | Protocol | Port range | Source       | Allow/Deny |
|-------------|-----------|----------|------------|--------------|------------|
| 100         | SSH       | TCP      | 22         | 10.0.1.0/28  | Allow      |
| 120         | Custom TCP(Redis)| TCP      | 6379       | 10.0.1.32/28 | Allow      |
| 130         | Custom TCP(Scylla)| TCP      | 9042       | 10.0.1.32/28 | Allow      |
| 140         | Custom TCP (PostgreSQL) | TCP| 5432    | 10.0.1.32/28 | Allow      |
| *           | All traffic | All     | All        | 0.0.0.0/0    | Deny       |

## Database NACL Outbound Rules

| Rule number | Type      | Protocol | Port range | Source       | Allow/Deny |
|-------------|-----------|----------|------------|--------------|------------|
| 100         | SSH       | TCP      | 22         | 10.0.1.0/28  | Allow      |
| 120         | Custom TCP(Redis)| TCP      | 6379       | 10.0.1.32/28 | Allow      |
| 130         | Custom TCP(Scylla)| TCP      | 9042       | 10.0.1.32/28 | Allow      |
| 140         | Custom TCP (PostgreSQL) | TCP| 5432    | 10.0.1.32/28 | Allow      |
| *           | All traffic | All     | All        | 0.0.0.0/0    | Deny       |




***
# Contact Information

| Name               | Email Address                               |
| ------------------ | ------------------------------------------- |
| Parasharam Desai   | parasharam.desai.snaatak@mygurukulam.co     |

***
# Resources and References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| Documentation Template           | [Link](https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template) |
| Autoscaling with NGINX on AWS Blog| [Link](https://www.nginx.com/blog/announcing-new-autoscaling-support-with-nginx-plus-on-aws-cloud-quick-start/) |
| Route53           | [Link](https://alwinmathewabraham.wordpress.com/2017/08/20/lab-10-configuring-dns-with-route-53-url/) |
| Cloud Infra 30k feet          | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/09-%20Cloud%20Infra%20Design/Cloud-Infra-Design-30K-Feet.md) |


