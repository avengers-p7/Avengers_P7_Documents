# Cloud Infra Design Dev


![image](https://github.com/avengers-p7/Documentation/assets/156056709/8e2c71e2-c6fe-4daa-b577-744d133497fd)




| **Author**           | **Created On** | **Last Updated** | **Document Version** |
| -------------------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 29-01-2024     | 29-01-2024       | V1                   |
***
# Table of Contents

1. [Introduction](#introduction)
2. [Pre-requisites](#pre-requisites)
3. [Infrastructure Diagram](#infrastructure-diagram)
4. [Description](#description)
5. [Cloud Architecture Best Practices](#Cloud-Architecture-Best-Practices)
6. [Contact Information](#contact-information)
7. [Resources and References](#resources-and-references)

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

**Ideal Infra**

![Ideal-Dev-Infra - Page 1 (2)](https://github.com/avengers-p7/Documentation/assets/156056709/2a6cdd8b-81ce-4906-8aab-a17ccfadd101)



**Require Infra**

![Required](https://github.com/avengers-p7/Documentation/assets/156056709/3d746742-7a40-4de4-bf6c-a938ab258bb0)






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
| Frontend | Frontend-sg         | 22, 3000                | frontend-lb-sg   |               
| Backend  | Backend-sg          | 22, 8080              | frontend-lb-sg     |               
| Database | Postgresql-sg      | 22, 5432              | Backend-sg       |               
| Database | Redis-sg         | 22, 6379              | Backend-sg       |            
| Database | Scylla-sg      | 22, 9042             | Backend-sg          |               



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
| *           | All traffic | All     | All       | 0.0.0.0/0    | Deny      |

## Frontend NACL Inbound Rules

| Rule number | Type      | Protocol | Port range | Source       | Allow/Deny |
|-------------|-----------|----------|------------|--------------|------------|
| 100         | SSH       | TCP      | 22         | 10.0.1.0/28  | Allow      |
| 110         | Custom TCP| TCP      | 3000       | 10.0.1.0/28  | Allow      |
| *           | All traffic | All     | All        | 0.0.0.0/0    | Deny       |

## Frontend NACL Outbound Rules

| Rule number | Type       | Protocol | Port range | Destination  | Allow/Deny |
|-------------|----------- |----------|------------|--------------|------------|
| 100         | SSH        | TCP      | 22         | 10.0.1.0/28  | Allow      |
| 110         | Custom TCP | TCP      | 3000       | 10.0.1.0/28  | Allow      |
| 120         | Custom TCP | TCP      | 32768-65535| 10.0.1.0/28  | Allow      |
| 130         | Custom TCP | TCP      | 1024-65535 | 10.0.1.0/28  | Allow      |
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
| 130         | Custom TCP| TCP      | 32768-65535| 10.0.1.16/28 | Allow      |
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
| 150         | Custom TCP| TCP      | 1024-65535 | 10.0.1.32/28 | Allow      |
| *           | All traffic | All     | All        | 0.0.0.0/0    | Deny       |

# Cloud Architecture Best Practices

| Aspect                 | Description                                                                                                                                                                                                                                                              |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Operational Excellence | Involves monitoring systems and continuously improving the cloud architecture and internal processes. Implement incremental changes, document procedures, and focus on troubleshooting.                                                                                   |
| Cost Optimization      | A major concern for businesses moving to the cloud. Incorporate cloud cost optimization strategies to reduce overall spending. Analyze expenses, drop components with high operational costs, and use automation for cost-efficient alternatives.                     |
| Performance Efficiency | Design cloud architecture with the right service provider to improve performance. Focus on structuring resources, selecting appropriate sizes/types, and utilizing automation and AI for optimization.                                                                     |
| Reliability            | Ensure workloads perform as expected and recover quickly from outages. Build automated recovery processes, use autoscaling to avoid under/overprovisioning, and establish change management processes for better resource monitoring and demand management. |
| Security               | Maintain data integrity, detect security breaches, and manage user permissions. Establish secure procedures and continuously monitor for unauthorized access through automated notifications.                                                                                |
| Sustainability         | Take proactive measures to minimize environmental impact. Maximize resource utilization, decrease costs, and establish responsible models for sustainability. Harden security for all applications and instances while continuously monitoring for breaches.            |




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
|Cloud Architecture Best Practices| [Link](https://www.nops.io/blog/cloud-architecture-best-practices/)|
|Ephemeral Ports|[Link](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html#nacl-ephemeral-ports)|
