# High Availability in Sonarqube
![image](https://github.com/avengers-p7/Documentation/assets/156056444/62618808-0025-4518-a9fd-5102cf1383e2)

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 02-02-2024  | 1.0        | Harshit Singh   | 03-02-2024      |


## Table  of Contents

1. [Introduction](#Introduction)
2. [Conclusion](#Conclusion)
3. [Contact Information](#Contact-Information)
4. [References](#References)
***

## Introduction 

***
## What
High availability (HA) is the elimination of single points of failure to enable applications to continue to operate even if one of the IT components it depends on, such as a server, fails. IT professionals eliminate single points of failure to ensure continuous operation and uptime at least 99.99% annually.

High availability clusters are groups of servers that support business-critical applications. Applications are run on a primary server and in the event of a failure, application operation is moved to secondary server(s) where they continue to operate.
***
## Why 
To reduce interruptions and downtime, it is essential to be ready for unexpected events that can bring down servers. At times, emergencies will bring down even the most robust, reliable software and systems. Highly available systems minimize the impact of these events, and can often recover automatically from component or even server failures. [Click Here](https://avinetworks.com/glossary/high-availability/), to know more about HA.
***
> [!IMPORTANT]
> If you want to run SonarQube as a Cluster, it is only possible with a [Data Center Edition](https://docs.sonarsource.com/sonarqube/latest/instance-administration/sonarqube-db-copy-tool/).<br>
> Below, is an alternative approach with Sonarqube+AWS to provide HA.

## Diagram
<img title="HA Sonarqube" alt="HA Sonarqube AWS " src="./HA-Sonarqube.drawio.svg">

| Component  | Details 
| ---------- | -----------------------------
| **Region** |	AWS Cloud FN.Virginia Region (us-east-1)
| **Management VPC** |	CIDR block 10.0.0.0/22
| **Availability Zones** (us-east-1a, us-east-1b) |	Includes public and private subnets, NAT Gateway, SonarQube Server, and Postgres Cluster
| **IGW** |	Internet Gateway 
| **Public Subnets** (10.0.0.0/26, 10.0.0.1/26)	| Security Group: Open, VPN, and SonarQube Security Group 000
| **Public-RT** |	Routing table for the public subnet
| **Private Subnet** (10.0.0.3/26, 10.0.0.4/26, 10.0.0.5/26, 10.0.0.6/26) |	SonarQube Server and Postgres Cluster
| **Private-RT** |	Routing table for the private subnet
| **NAT Gateways** (NAT GW-01, NAT GW-02) |	Located in the public subnets
| **NACL** |	Network Access Control List
| **ALB** |	Application Load Balancer
| **SonarQube Servers** |	Sonarqube sevrers in Private subnets(10.0.0.2/26, 10.0.0.3/26) SonarQube Security Group 000
| **Postgres Cluster** |	Private subnet 10.0.0.4/26, NACL Hop, NACL Hol, and NACL Users |




> [!Note]
> CIDR blocks, security groups, NACLs, and subnets are labeled with shorthand notations for simplicity.


## Conclusion
***

## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| What is HA?                                   | https://avinetworks.com/glossary/high-availability/ |
| High Availability and Scalability - ELB & ASG | https://zhenye-na.github.io/aws-certs-cheatsheet/posts/ha-elb-asg/#:~:text=Auto%20Scaling%20Group%20(ASG),instances%20to%20a%20load%20balancer |
