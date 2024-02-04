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
## Steps to Take a Full Backup of SonarQube Server

### Step 1 – Stop the Sonarqube server
```shell
$SONAR_HOME/bin/linux-x86-64/sonar.sh stop
```

### Step 2 – Backup the production database e.g mysql db
```shell
mysqldump –opt -Q -h localhost -u username–password=’password’ databasename | gzip -9 > databasename.gz
```
## 

> [!NOTE]
> Sonarqube provides [**DB Copy Tool**](https://docs.sonarsource.com/sonarqube/latest/instance-administration/sonarqube-db-copy-tool/) to help you backup or migrate your SonarQube database from one database vendor to another. For example, if you've been using your SonarQube instance with
> Oracle and want to migrate to PostgreSQL, the SonarQube DB Copy Tool will help. DB Copy is preferred for database migration because it does SonarQube-specific checks, ensures data consistency,
> and outputs meaningful logs.


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

### Step 4 – List of plugins installed
Be mindful that $SONAR_HOME/extensions/plugins directory where you can get the list of plugins installed.

### Step 5 – List of custom coding rules installed
Be mindful that $SONAR_HOME/extensions/rules directory where you can get the list of custom coding rules.

### Step 6 – List of configurations used
Be mindful that $SONAR_HOME/config directory where you can get sonar.properties and wrapper.conf file which has all the current configurations and setup.

### Step 7 – Re-start the production server
```shell
$SONAR_HOME/bin/linux-x86-64/sonar.sh start
```
### Step 8 – Keep the Sonar_home.zip and databasename.gz to the safe location.

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
