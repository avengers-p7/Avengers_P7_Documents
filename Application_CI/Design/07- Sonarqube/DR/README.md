# Disaster Recovery in Sonarqube
![image](https://github.com/avengers-p7/Documentation/assets/156056444/c0cf39b5-29d9-4af2-9752-c40fe09c8c5f)

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 02-02-2024  | 1.0        | Harshit Singh   | 04-02-2024      |


## Table  of Contents

1. [Introduction](#Introduction)
2. [What is Disaster Recovery?](#What-is-Disaster-Recovery)
3. [Why Disater Recovery?](#Why-Disater-Recovery)
4. [Steps to Take a Full Backup of SonarQube Server](#Steps-to-Take-a-Full-Backup-of-SonarQube-Server)
5. [Conclusion](#Conclusion)
6. [Contact Information](#Contact-Information)
7. [References](#References)
***

## Introduction 
Disaster Recovery (DR) is crucial for organizations to swiftly respond to and recover from events impacting business operations, aiming to minimize downtime and data loss. This process involves a comprehensive analysis of IT infrastructure and the creation of a formal document for crisis management. 

This document covers backing up the database and server directory, and listing installed plugins and configurations. This proactive approach ensures business continuity, data protection, regulatory compliance, and overall resilience in the face of unforeseen events, emphasizing the importance of a robust disaster recovery plan for organizational stability.
***
## What is Disaster Recovery?
Disaster recovery (DR) is an organization's ability to respond to and recover from an event that negatively affects business operations. The goal of DR is to reduce downtime, data loss and operational disruptions while maintaining business continuity. To prepare for this, organizations often perform an in-depth analysis of their systems and IT infrastructure and create a formal document to follow in times of crisis. 
***
## Why Disater Recovery?
Disaster recovery is essential for organizations to ensure `business continuity, protect valuable data from loss or corruption, mitigate risks, comply with regulations, maintain customer trust and reputation, avoid financial losses, gain a competitive edge, sustain employee productivity, and stabilize supply chains`. It is a crucial strategy to swiftly recover from unexpected events or disasters and minimize the impact on operations. To know more about disaster recovery and  disaster recovery plan, [**click here**](https://www.techtarget.com/searchdisasterrecovery/definition/disaster-recovery).


![image](https://github.com/avengers-p7/Documentation/assets/156056444/67e8720b-e9e6-43c2-aa13-193300927e5a)
***
## Infra Diagram
<img title="HA Sonarqube" alt="HA Sonarqube AWS " src="./HA+DR-Sonarqube.drawio (2).svg">

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
|**Mngt-VPC-Endpoint**| VPC Endpoint to access S3 bucket 
|**Sonarqube Back-Up S3 Bucket**| to store Sonarqube DB back-up |
> [!Note]
> CIDR blocks, security groups, NACLs, and subnets are labeled with shorthand notations for simplicity.
***
## Description
The configuration for the above comprises 2 Sonarqube servers, a application load balancer, and a database(Postgres) server cluster.
- **Two Sonarqube instances** responsible for handling web requests from users (WebServer process) and handling analysis reports (ComputeEngine process). You can add application nodes to increase computing capabilities.
- A **load balancer** to load balance traffic between the two Sonarqube instances.
- A **Auto Scaling Group** to matain the availability of Sonarqube server.
- A **S3**  Bucket to store Sonarqube Backup. 
- **PostgreSQL cluster** to provide High Availability in database server.
***

> [!NOTE]
> Sonarqube provides [**DB Copy Tool**](https://docs.sonarsource.com/sonarqube/latest/instance-administration/sonarqube-db-copy-tool/) to help you backup or migrate your SonarQube database from one database vendor to another. For example, if you've been using your SonarQube instance with
> Oracle and want to migrate to PostgreSQL, the SonarQube DB Copy Tool will help. DB Copy is preferred for database migration because it does SonarQube-specific checks, ensures data consistency,
> and outputs meaningful logs.
## Steps to Take a Full Backup of SonarQube Server

### Step 1 – Stop the Sonarqube server

```shell
sudo systemctl stop sonarqube.service
```

### Step 2 – Backup the production database e.g postgres db

```shell
su - postgres
pg_dump -U postgress -F t  sonarqube > sonar_db_backup.tar
```
## 


### Step 3 – Backup the $SONAR_HOME directory
```shell
zip -r Sonar_home.zip $SONAR_HOME
```
#### Directory Structure
| Directory                        | Description |
| -------------------------------- | ------------ |
| `$SONAR_HOME/extensions/plugins` | directory where you can get the list of plugins installed
| `$SONAR_HOME/extensions/rules`   | directory where you can get the list of custom coding rules.
| `$SONAR_HOME/config`             | directory where you can get sonar.properties and wrapper.conf file which has all the current configurations and setup.


### Step 4 – Re-start the production server
```shell
sudo systemctl start sonarqube.service
```
### Step 5 – Keep the Sonar_home.zip and sonar_db_backup.tar to the safe location.

## Restore Sonarqube


### Step 1 - Install Sonarqube 

### Step 2 – Stop the Sonarqube server
```shell
sudo systemctl start sonarqube.service
```
### Step 3 - Restore DB
```shell
su - postgress
pg_restore -U postgress --dbname=sonarqube --verbose sonar_db_backup.tar
```
### Step 4 - Now, go to the sonarqube installation dir  `/opt/sonarqube/data` delete  the elastic indexes`es6` directory. 


### Step 5 – Re-start the Sonarqube server
```shell
sudo systemctl start sonarqube.service
```
I recommend making a copy of both the configuration files located in $SONARQUBE_HOME/conf and the list of plugins found in $SONARQUBE_HOME/extensions/plugins.

Backing up the elastic search data is unnecessary since sonarqube generates all the required information during startup. However, keep in mind that the initial startup time may vary depending on the volume of stored data.
***
## Conclusion
This comprehensive approach safeguards valuable data, complies with regulations, maintains trust, and ensures operational stability, emphasizing the significance of disaster recovery in mitigating risks and sustaining organizational resilience. Now, you can restore your Sonarqube by using these backup files created by the above steps.
***

## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
***

## References

| Description                   | References  
| ----------------------------- | ------------------------------------------------------------------- |
| Backup and Restore            | https://docs.sonarsource.com/sonarqube/latest/instance-administration/backup-and-restore/|
| Take full backup of Sonarqube | https://www.scmgalaxy.com/tutorials/sonarqube-upgrade-backup-and-restore-process/|
| DB Copy Tool                  | https://docs.sonarsource.com/sonarqube/latest/instance-administration/sonarqube-db-copy-tool/ |
| S3                            | https://www.whizlabs.com/labs/access-s3-from-private-ec2-instance-using-vpc-endpoint |
