# Jenkins AWS Infra

| **Author**           | **Created On** | **Last Updated** | **Document Version** |
| -------------------- | -------------- | ---------------- | -------------------- |
| **Vikram Bisht**     | 31-01-2024     | 01-02-2024       | V1                   |


# Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Description](#Description)
4. [Infrastructure Diagram](#infrastructure-diagram)
5. [Contact Information](#contact-information)
6. [References](#References)

***
# Introduction
This document shows an overview of our AWS Infra for Jenkins. 

***
# Prerequisites
| Tool                  | Description                                  |
|-----------------------|----------------------------------------------|
| AWS Management Console | Required for provisioning AWS resources.    |


# Description

* Users connect to the environment through the internet.
* Traffic is directed through public subnets and security groups.
* Private components have internet access via the NAT gateway.
* Secure access to private resources is facilitated by bastion instances.
* Components are deployed within Virtual Private Clouds.
* Load balancer is configured for HA. 


# Infrastructure Diagram

![image](https://github.com/avengers-p7/Documentation/assets/79625874/61ab2369-21e0-4ac5-b044-ddf02a9a1804)

# Contact Information

|  Name                     |        	Email Address           |
| ------------              | --------------------------------|
| Vikram Bisht              |  Vikram.Bisht@opstree.com       |  

# References

|  Source                                                                                 |        Description                 |
| ------------                                                                            | -----------------------            |
| https://medium.com/@sebolabs/jenkins-ha-aws-cd55d82057c8                                | Infra Refrence                     |  
