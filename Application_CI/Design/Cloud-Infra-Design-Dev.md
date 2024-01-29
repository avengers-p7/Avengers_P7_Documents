# Cloud Infra Design Dev

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Cloud Infra Design Dev Details](#cloud-infra-design-dev-details)
   - [Region](#region)
   - [Availability Zone](#availability-zone)
   - [Virtual Private Cloud (VPC)](#vpc)
   - [Subnets](#subnets)
   - [Internet Gateway](#internet-gateway)
   - [Route Table](#route-table)
   - [Network Access Control List (NACL)](#network-access-control-list)
   - [Security Groups](#security-groups)
   - [NAT Gateway](#nat-gateway)
   - [Application Load Balancer](#application-load-balancer)
4. [Infrastructure Diagram](#infrastructure-diagram)
5. [Contact Information](#contact-information)
6. [Resources and References](#resources-and-references)

## Introduction

The Cloud Infra Design Dev documentation provides an in-depth overview of the development infrastructure hosted on AWS for the OT-Microservices project. This modern and modular architecture prioritizes scalability and efficiency, utilizing AWS services to establish a reliable, scalable, and high-performance foundation.


## Prerequisites
| Tool                  | Description                                  |
|-----------------------|----------------------------------------------|
| AWS Management Console | Required for provisioning AWS resources.     |

## AWS Platform Details

### Region

| Item                  | Description            |
|-----------------------|------------------------|
| Europe                | Frankfurt              |
| Region Code           | eu-central-1           |

### Availability Zone

| Item                  | Description            |
|-----------------------|------------------------|
| 1.eu-central-1a       | Primary availability zone for the region. |

### Virtual Private Cloud (VPC)

| Item                  | Description            |
|-----------------------|------------------------|
| Name                  | OT-Micro-Dev-Vpc       |

### Subnets

1. **Public Subnet-1**

| Item                  | Description                              |
|-----------------------|------------------------------------------|
| Purpose               | Hosts the Bastion Host for secure access.|

2. **Private Subnet-1**

| Item                  | Description                              |
|-----------------------|------------------------------------------|
| Purpose               | Hosts the Frontend application components.|

3. **Private Subnet-2**

| Item                  | Description                              |
|-----------------------|------------------------------------------|
| Instances             | Hosts the Attendance, Employee, and Salary APIs.|

4. **Private Subnet-3**

| Item                  | Description                              |
|-----------------------|------------------------------------------|
| Instances             | Hosts PostgreSQL, Scylla, and Redis databases.|

## Internet Gateway

| Item                  | Description                              |
|-----------------------|------------------------------------------|
| Name                  | Internet Gateway for OT-Micro-Dev-Vpc.   |

## Route Table

1. **Public-rt**

| Item                  | Description                                  |
|-----------------------|----------------------------------------------|
| Associated Subnet     | Associates with Public Subnet-1 for internet access.|

2. **Private-rt**

| Item                  | Description                                  |
|-----------------------|----------------------------------------------|
| Associated Subnets    | Associates with Private Subnet-1, Subnet-2, and Subnet-3.|

## Network Access Control List (NACL)

1. **Nacl-1**

| Item                  | Description                              |
|-----------------------|------------------------------------------|
| Associated Subnet     | Associates with Private Subnet-1.        |

2. **Nacl-2**

| Item                  | Description                              |
|-----------------------|------------------------------------------|
| Associated Subnet     | Associates with Private Subnet-2.        |

3. **Nacl-3**

| Item                  | Description                              |
|-----------------------|------------------------------------------|
| Associated Subnet     | Associates with Private Subnet-3.        |

## Security Groups

### For Private Subnet-2 (APIs)

| Item                  | Description                                  |
|-----------------------|----------------------------------------------|
| **ATT-sg**            | Security Group for Attendance API.          |
| **EMP-sg**            | Security Group for Employee API.            |
| **Sal-sg**            | Security Group for Salary API.              |

### For Private Subnet-3 (Databases)

| Item                  | Description                                  |
|-----------------------|----------------------------------------------|
| **PSql-sg**           | Security Group for PostgreSQL.              |
| **Scylla-sg**         | Security Group for Scylla database.         |
| **Redis-sg**          | Security Group for Redis database.          |

## NAT Gateway

| Item                  | Description                              |
|-----------------------|------------------------------------------|
| ALB                  | NAT Gateway for private subnet internet access.|

## Application Load Balancer

| Item                  | Description                              |
|-----------------------|------------------------------------------|
| Nat gateway                | Application Load Balancer for distributing traffic.|

## Infrastructure Diagram

The diagram illustrates the flow of AWS-hosted development infrastructure. Users connect to the environment through the internet, and traffic is directed through public subnets and security groups to reach specific resources. Private components have internet access through the NAT gateway, and secure access to private resources is managed by bastion instances. The architecture encompasses central, AWS cloud, network, security, and application components, all deployed within Virtual Private Clouds (VPCs). This high-level overview provides insights into connectivity and interactions within the development environment.

![Main-Dev](https://github.com/avengers-p7/Documentation/assets/156056709/1ebe5354-fec2-47de-9e60-8f6701f6d33c)


## Contact Information

| Name               | Email Address                               |
| ------------------ | ------------------------------------------- |
| Parasharam Desai   | parasharam.desai.snaatak@mygurukulam.co     |

## Resources and References

- [Reference 1]
- [Reference 2]
