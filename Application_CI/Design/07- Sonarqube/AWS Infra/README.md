
# SonarQube AWS Infra
![1_tvWYZwZGRnXJPtt-X7lOoA](https://github.com/avengers-p7/Documentation/assets/156056344/95180069-054e-4980-8d90-dc7e3e856d8c)

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Aakash Tripathi | 30 Jan 2024   |     v1     | Aakash Tripathi | 03 Feb 2024    |


## Table of Contents

+ [Introduction](#introduction)
+ [Description](#description)
+ [Infrastructure Diagram](#infrastructure-diagram)
+ [Contact Information](#contact-information)
+ [References](#References)

***
## Introduction
This document shows an overview of our AWS Infra for SonarQube. This document presents a detailed AWS infrastructure diagram outlining the setup of SonarQube within the AWS ecosystem. 

***
## Description

* Users connect to the environment through the internet.
* Traffic is directed through public subnets and security groups.
* Private components have internet access via the NAT gateway.
* Secure access to private resources is facilitated by bastion instances.
* Components are deployed within Virtual Private Clouds.
* Load balancer is configured for SonarQube UI via Internet and can also be used for HA capabilaties if required. 


## Infrastructure Diagram

![SOnarQFinal](https://github.com/avengers-p7/Documentation/assets/156056344/6538c871-15cd-420f-9376-a90568ded922)



## Contact Information

|  Name                     |        	Email Address           |
| ------------              | --------------------------------|
| Aakash Tripathi              |  aakash.tripathi.snaatak@mygurukulam.co       |  

## References

|  Source                                                                                 |        Description                 |
| ------------                                                                            | -----------------------            |
| SonarQube Docs                                                                          | https://docs.sonarsource.com/sonarqube/latest/setup-and-upgrade/overview/       |  
