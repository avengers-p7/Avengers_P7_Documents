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
> [!NOTE]
> If you want to run SonarQube as a Cluster, it is only possible with a Data Center Edition.

## Architecture
![image](https://github.com/avengers-p7/Documentation/assets/156056444/4b1a5038-1fa6-42ae-a5e8-daa5d4d5b996)
- Two application nodes responsible for handling web requests from users (WebServer process) and handling analysis reports (ComputeEngine process). You can add application nodes to increase computing capabilities.
- Three search nodes that host the Elasticsearch process that will store data indices. SSDs perform significantly better than HDDs for these nodes.
- A reverse proxy / load balancer to load balance traffic between the two application nodes. The installing organization must supply this hardware or software component.
- PostgreSQL, Oracle, or Microsoft SQL Server database server. This software must be supplied by the installing organization.
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
