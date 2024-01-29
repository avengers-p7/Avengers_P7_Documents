# Cloud Infra Design Dev

## Table of Contents

1. [Introduction](#introduction)
2. [AWS Platform Details](#aws-platform-details)
   - [Region](#region)
   - [Availability Zone](#availability-zone)
   - [VPC](#vpc)
   - [Subnets](#subnets)
   - [Internet Gateway](#internet-gateway)
   - [Route Table](#route-table)
   - [NACL](#nacl)
   - [Security Groups](#security-groups)
   - [Nat Gateway](#nat-gateway)
   - [Application Load Balancer](#application-load-balancer)
3. [Diagram](#diagram)
4. [Contact Information](#contact-information)
5. [Resources and References](#resources-and-references)

## Introduction

The OT-Microservices project follows a modern and modular architecture with a focus on scalability and efficiency. The infrastructure is designed to utilize AWS services to ensure a reliable, scalable, and high-performance foundation.

## AWS Platform Details

### Region

- Europe (Frankfurt)
- Region Code: eu-central-1

### Availability Zone

- 1.eu-central-1a

### VPC

- Name: OT-Micro-Dev-Vpc

### Subnets

1. **Public Subnet-1**
   - Purpose: Bastion Host

2. **Private Subnet-1**
   - Purpose: Frontend (React-based)

3. **Private Subnet-2**
   - Instances:
      1. Attendance API
      2. Employee-API
      3. Salary API

4. **Private Subnet-3**
   - Instances:
      1. PostgreSQL
      2. Scylla
      3. Redis

### Internet Gateway

- Name: igw - for Dev-vpc

### Route Table

1. **Public-rt**
   - Associated with Public Subnet-1

2. **Private-rt**
   - Associated with Private Subnet-1, Subnet-2, and Subnet-3

### NACL

1. **Nacl-1**
   - Associated with Private Subnet-1

2. **Nacl-2**
   - Associated with Private Subnet-2

3. **Nacl-3**
   - Associated with Private Subnet-3

### Security Groups

#### For Private Subnet-2 (APIs)

1. **ATT-sg** - Attendance API
2. **EMP-sg** - Employee-API
3. **Sal-sg** - Salary-API

#### For Private Subnet-3 (Databases)

1. **PSql-sg** - PostgreSQL
2. **Scylla-sg** - Scylla
3. **Redis-sg** - Redis

### Nat Gateway

- Name: Nat-gateway

### Application Load Balancer

- Name: ALB

## Diagram

![Main-Dev](https://github.com/avengers-p7/Documentation/assets/156056709/1ebe5354-fec2-47de-9e60-8f6701f6d33c)


## Contact Information

| Name               | Email Address                               |
| ------------------ | ------------------------------------------- |
| Parasharam Desai   | parasharam.desai.snaatak@mygurukulam.co     |

## Resources and References

- [Reference 1]
- [Reference 2]
