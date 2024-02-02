# Cloud Infra Design 30k Feet

| **Author**           | **Created On** | **Last Updated** | **Document Version** |
| -------------------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 29-01-2024     | 29-01-2024       | V1                   |

# Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Top-Down Approach](#top-down-approach)
4. [Cloud Infra Design 30k Feet Details](#cloud-infra-design-30k-feet-details)
5. [Infrastructure Diagram](#infrastructure-diagram)
6. [Contact Information](#contact-information)
7. [Resources and References](#resources-and-references)

# Introduction

The Cloud Infra Design 30k Feet documentation provides an in-depth overview of the Production, Development, Quality Assurance infrastructure hosted on AWS for the OT-Microservices project. This modern and modular architecture prioritizes scalability and efficiency, utilizing AWS services to establish a reliable, scalable, and high-performance foundation.

# Prerequisites
| Tool                  | Description                                  |
|-----------------------|----------------------------------------------|
| AWS Management Console | Required for provisioning AWS resources.     |

# Top-Down Approach

**Top-Down Approach Overview:**

Think of the top-down approach like looking at a big picture first. It's like standing on a hill and taking in the view of the entire landscape. In our Cloud Infra Design, this means starting with the overall plan, considering things like the main structure (VPCs), big locations (regions), and major elements like load balancers and databases. As we zoom in, we get into specifics like subnets, security groups, and individual services. This method helps us see the whole system strategically.

# Cloud Infra Design 30k Feet Details

Here's a flow summary of the infrastructure:

| Aspect                  | Details                                                                                          |
|-------------------------|--------------------------------------------------------------------------------------------------|
| **User Access**         | Users connect to the infrastructure through the internet.                                          |
| **Public Subnets**      | Public subnets host components that need direct internet access. The Bastion Host is in the public subnet for secure access.                                   |
| **Private Subnets**     | Frontend application components are hosted in one private subnet. Attendance, Employee, and Salary APIs are in separate private subnets. PostgreSQL, Scylla, and Redis databases are in another private subnet.                             |
| **Security Groups**     | Different security groups are defined for various components: Bastion-sg for the Bastion Host, Frontend-sg for Frontend components, ATT-sg, EMP-sg, and Sal-sg for respective APIs, PSql-sg, Scylla-sg, and Redis-sg for database components.                         |
| **Internet Gateway & NAT Gateway** | Internet Gateway (Igw) facilitates internet access for the VPC. NAT Gateway allows instances in private subnets to initiate outbound traffic to the internet.                                 |
| **ALB (Application Load Balancer)** | ALB is configured for distributing frontend traffic across multiple targets, ensuring high availability.                                                  |
| **Region and Availability Zone** | The infrastructure is deployed in the Europe region, specifically in the Frankfurt (eu-central-1) region. Availability zones (eu-central-1a & eu-central-1b) are utilized for redundancy and fault tolerance.          |
| **VPC (Virtual Private Cloud)** | Separate VPCs are created for Development, Production, and Quality Assurance environments. The flow summary outlines the path of user access, the organization of components in public and private subnets, the role of security groups, NACLs, internet and NAT gateways, routing, and the use of load balancing and auto-scaling for ensuring scalability and availability of services. |



# Infrastructure Diagram

**Production Environment**

![Cloud-Infra-30k feet - Page 1 (4)](https://github.com/avengers-p7/Documentation/assets/156056709/8b78fee4-997d-4e7e-ad64-7643ec554c7d)

**Development Environment**

![Cloud-Infra-30k feet - Page 1 (5)](https://github.com/avengers-p7/Documentation/assets/156056709/2c6234b5-863e-4fc2-a357-c918815dbb1f)

**Quality Assurance**

![Cloud-Infra-30k feet - Page 1 (7)](https://github.com/avengers-p7/Documentation/assets/156056709/0d2c245c-fbcd-4978-b1a7-b88a2fa96a99)







# Contact Information

| Name               | Email Address                               |
| ------------------ | ------------------------------------------- |
| Parasharam Desai   | parasharam.desai.snaatak@mygurukulam.co     |

# Resources and References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| Documentation Template           | [Documentation Template](https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template) |
| Autoscaling with NGINX on AWS Blog| [NGINX Autoscaling on AWS](https://www.nginx.com/blog/announcing-new-autoscaling-support-with-nginx-plus-on-aws-cloud-quick-start/) |

