# High Availability in Sonarqube
![image](https://github.com/avengers-p7/Documentation/assets/156056444/62618808-0025-4518-a9fd-5102cf1383e2)

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 02-02-2024  | 1.0        | Harshit Singh   | 04-02-2024      |


## Table  of Contents

1. [Introduction](#Introduction)
2. [What](#What)
3. [Why](#Why)
4. [Infra Diagram](#Infra-Diagram)
5. [Description](#Description)
6. [Contact Information](#Contact-Information)
7. [References](#References)
***

## Introduction 

***
## What
High availability (HA) is the elimination of single points of failure to enable applications to continue to operate even if one of the IT components it depends on, such as a server, fails. IT professionals eliminate single points of failure to ensure continuous operation and uptime at least 99.99% annually.

High availability clusters are groups of servers that support business-critical applications. Applications are run on a primary server and in the event of a failure, application operation is moved to secondary server(s) where they continue to operate.
***
## Why 
To reduce interruptions and downtime, it is essential to be ready for unexpected events that can bring down servers. At times, emergencies will bring down even the most robust, reliable software and systems. Highly available systems minimize the impact of these events, and can often recover automatically from component or even server failures. 

[**Click Here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/DevOps%20Practices/High%20Availability/README.md), to know more about HA.
***
> [!IMPORTANT]
> If you want to run SonarQube as a Cluster, it is only possible with a [Data Center Edition](https://docs.sonarsource.com/sonarqube/latest/setup-and-upgrade/install-the-server-as-a-cluster/)<br>
> Below, is an alternative approach with Sonarqube+AWS to provide HA.

## Infra Diagram
<img title="HA Sonarqube" alt="HA Sonarqube AWS " src="./HA-Sonarqube.drawio (3).svg">

| Component  | Details 
| ---------- | -----------------------------
| **Region** |	N.Virginia Region (us-east-1)
| **Management VPC** |	CIDR block 10.0.0.0/22
| **Availability Zones** (us-east-1a, us-east-1b) |	Includes public and private subnets, NAT Gateway, SonarQube Server, and Postgres Cluster
| **IGW** |	Internet Gateway 
| **Public Subnets** (10.0.0.0/26, 10.0.0.1/26)	|  OpenVPN, with Security Group, NACL and NAT Gateways 
| **Public-RT** |	Routing table for the public subnet
| **Private Subnet** (10.0.0.2/26, 10.0.0.3/26, 10.0.0.4/26, 10.0.0.5/26 ) |	SonarQube Server and Postgres Cluster
| **Private-RT** |	Routing table for the private subnet
| **NAT Gateways** (NAT GW-01, NAT GW-02) |	Located in the public subnets
| **NACL** |	Network Access Control List, for subnet level security
| **ALB** |	Application Load Balancer to distribute the load b/w application servers
| **ASG** | Auto Scaling Group for application server |
|**Security Group** (SonarQube SG, Postgress SG)| To provide security on instance level
| **SonarQube Servers** |	Sonarqube sevrers in Private subnets(10.0.0.2/26, 10.0.0.3/26) 
| **Postgres Cluster** |	Private subnets (10.0.0.4/26, 10.0.0.5/26) |
> [!Note]
> CIDR blocks, security groups, NACLs, and subnets are labeled with shorthand notations for simplicity.

## Description
The configuration for the above comprises 2 Sonarqube servers, a application load balancer, and a database(Postgres) server cluster.
- **Two Sonarqube instances** responsible for handling web requests from users (WebServer process) and handling analysis reports (ComputeEngine process). You can add application nodes to increase computing capabilities.
- A **load balancer** to load balance traffic between the two Sonarqube instances.
- A **Auto Scaling Group** to matain the availability of Sonarqube server.
- **PostgreSQL cluster** to provide High Availability in database server.


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
