
# Jenkins AWS Infra




## Table of Contents

+ [Introduction](#introduction)
+ [Description](#description)
+ [Infrastructure Diagram](#infrastructure-diagram)
+ [Contact Information](#contact-information)  R
+ [References](#References)

***
## Introduction
This document shows an overview of our AWS Infra for Jenkins. This document presents a detailed AWS infrastructure diagram outlining the setup of Jenkins within the AWS ecosystem. 

***
## Description

* Users connect to the environment through the internet.
* Traffic is directed through public subnets and security groups.
* Private components have internet access via the NAT gateway.
* Secure access to private resources is facilitated by bastion instances.
* Components are deployed within Virtual Private Clouds.
* Load balancer is configured for SonarQube UI via Internet and can also be used for HA capabilaties if required. 


## Infrastructure Diagram

![SQ](https://github.com/avengers-p7/Documentation/assets/156056344/432eb19b-389d-42f3-bcba-b050ea3832d9)


# Contact Information

|  Name                     |        	Email Address           |
| ------------              | --------------------------------|
| Aakash Tripathi              |  aakash.tripathi.snaatak@mygurukulam.co       |  

# References

|  Source                                                                                 |        Description                 |
| ------------                                                                            | -----------------------            |
| SonarQube Docs                                                                          | https://docs.sonarsource.com/sonarqube/latest/setup-and-upgrade/overview/       |  
