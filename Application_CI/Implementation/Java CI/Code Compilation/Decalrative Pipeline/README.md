# Java Code Compilation Pipeline

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

## Prerequisites

| Tool | Description |
| ---- | ----------- |
| Jenkins(2.426.3) | To build our pipeline |
***

## Runtime Prerequisites

|Language / Dependency|Description|
|-------|-------|
| Java 17 | For springboot project compilation | 
| Maven Compiler Plugin | For springboot project compilation |

> [!Important]
> I have installed the plugin bundle provided by Jenkins during setup. If you have not done the same, you may encounter plugin errors.
## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| HA  reference doc | https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/DevOps%20Practices/High%20Availability/README.md |
| What is HA?                                   | https://avinetworks.com/glossary/high-availability/ |
| Clustering in Data Center Edition             | https://docs.sonarsource.com/sonarqube/latest/setup-and-upgrade/configure-and-operate-a-cluster/ |
| Installation Sonarqube                        | https://docs.sonarsource.com/sonarqube/latest/setup-and-upgrade/install-the-server/introduction/ |
| High Availability and Scalability - ELB & ASG | https://zhenye-na.github.io/aws-certs-cheatsheet/posts/ha-elb-asg/#:~:text=Auto%20Scaling%20Group%20(ASG),instances%20to%20a%20load%20balancer |
| ”Don’t let the fact that SonarQube bundles-in the H2 database tempt you to skip this step. H2 is included as a courtesy for initial testing only and is not for long-term, production use. If you try to use H2 as your production database, we guarantee you’ll be disappointed—not least because you cannot upgrade a SonarQube database that’s stored in H2.”<| https://livebook.manning.com/book/sonarqube-in-action/appendix-a/ |
