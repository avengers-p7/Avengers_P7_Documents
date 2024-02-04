# Disaster Recovery in Sonarqube
![image](https://github.com/avengers-p7/Documentation/assets/156056444/c0cf39b5-29d9-4af2-9752-c40fe09c8c5f)

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 02-02-2024  | 1.0        | Harshit Singh   | 03-02-2024      |


## Table  of Contents
Backup, recovery , MTTR...
1. [Introduction](#Introduction)
2. [Conclusion](#Conclusion)
3. [Contact Information](#Contact-Information)
4. [References](#References)
***

## Introduction 

### What is Disaster Recovery?
What is disaster recovery (DR)?
Disaster recovery (DR) is an organization's ability to respond to and recover from an event that negatively affects business operations. The goal of DR is to reduce downtime, data loss and operational disruptions while maintaining business continuity. To prepare for this, organizations often perform an in-depth analysis of their systems and IT infrastructure and create a formal document to follow in times of crisis. 

### Why Disater Recovery?
Disaster recovery is essential for organizations to ensure `business continuity, protect valuable data from loss or corruption, mitigate risks, comply with regulations, maintain customer trust and reputation, avoid financial losses, gain a competitive edge, sustain employee productivity, and stabilize supply chains`. It is a crucial strategy to swiftly recover from unexpected events or disasters and minimize the impact on operations.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/67e8720b-e9e6-43c2-aa13-193300927e5a)
> [!NOTE]
> To know more about disaster recovery and  disaster recovery plan, [**click here**](https://www.techtarget.com/searchdisasterrecovery/definition/disaster-recovery).

## How


## Steps to Take a Full Backup of SonarQube Server
### Step 1 – Stop the production server
Windows
```shell
%SONARQUBE_HOME%/bin/windows-x86-32/StopNTService.bat
```
Linux
```shell
$SONAR_HOME/bin/linux-x86-64/sonar.sh stop
```
### Step 2 – Backup the production database e.g mysql db
```shell
mysqldump –opt -Q -h localhost -u username–password=’password’ databasename | gzip -9 > databasename.gz
```
Also, there is one tool which has been available to take the backup of database.
[**Refrence Doc**](https://docs.sonarqube.org/display/SONAR/Sonar+DB+Copy+Tool)
### Step 3 – Backup the $SONAR_HOME directory
```shell
zip -r Sonar_home.zip $SONAR_HOME
```
### Step 4 – List of plugins installed
Be mindful that $SONAR_HOME/extensions/plugins directory where you can get the list of plugins installed.
### Step 5 – List of custom coding rules installed
Be mindful that $SONAR_HOME/extensions/rules directory where you can get the list of custom coding rules.
### Step 6 – List of configurations used
Be mindful that $SONAR_HOME/config directory where you can get sonar.properties and wrapper.conf file which has all the current configurations and setup.
### Step 7 – Re-start the production server
Linux
```shell
$SONAR_HOME/bin/linux-x86-64/sonar.sh start
```
### Step 8: Keep the Sonar_home.zip and databasename.gz to the safe location.

I recommend making a copy of both the configuration files located in $SONARQUBE_HOME/conf and the list of plugins found in $SONARQUBE_HOME/extensions/plugins.

Backing up the elastic search data is unnecessary since sonarqube generates all the required information during startup. However, keep in mind that the initial startup time may vary depending on the volume of stored data.

## Backup and Restore

## DB Copy Tool
Sonarqube provides this tool to help you migrate your SonarQube database from one database vendor to another. For example, if you've been using your SonarQube instance with Oracle and want to migrate to PostgreSQL, the SonarQube DB Copy Tool will help. DB Copy is preferred for database migration because it does SonarQube-specific checks, ensures data consistency, and outputs meaningful logs.
For steps,[click here](https://docs.sonarsource.com/sonarqube/latest/instance-administration/sonarqube-db-copy-tool/)

## Conclusion
***

## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
***

## References

| Description                  | References  
| ------------------------ | ------------------------------------------------------------------- |
| Authorization in Jenkins | https://www.jenkins.io/doc/book/security/managing-security/ |
| Role Based Strategy      | https://plugins.jenkins.io/role-strategy/ |
| Common Mistakes | https://www.jenkins.io/doc/book/security/access-control/ |
