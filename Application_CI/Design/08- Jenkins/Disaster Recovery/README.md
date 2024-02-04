# Disaster Recovery (DR) in Jenkins


|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      |  31 Jan 2024   |     v1     | Vidhi Yadav     | 31 Jan 2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [DR Diagram](#disaster-recovery-infrastructure)
+ [Key Components](#architecture-components)
+ [Flow Explanation](#flow-explanation)
+ [MTTR](#mttr)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***
## Introduction
Disaster Recovery (DR) is a strategic and systematic approach to safeguarding an organization's critical systems, applications, and data from the impact of unforeseen events or disasters. These events can range from natural disasters like earthquakes and floods to human-induced incidents such as cyber-attacks or hardware failures. 

The primary goal of a DR plan is to minimize downtime, data loss, and operational disruptions, ensuring business continuity in the face of adversity. The overall aim is to enable organizations to resume normal operations as quickly and efficiently as possible following a disruptive event.

For a more detailed understanding of Disaster recovery and its components, please refer to the following link: [Detailed Description of High Availability](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/DevOps%20Practices/DisasterRecovery/README.md).


*** 
## Disaster Recovery Infrastructure

* Presented below is an illustrative diagram showcasing the approach to Jenkins disaster recovery. This visual guide provides a clear depiction of the steps and components involved in ensuring the recovery of Jenkins data in the event of unexpected disruptions or disasters

![jenkins_DA_final drawio](https://github.com/avengers-p7/Documentation/assets/156056349/86e078c5-038c-4608-b914-8121573d83d4)

*** 
## Architecture Components

| Service           | Description                                                                                                                                                           |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Amazon EFS        | Amazon EFS is a scalable and fully managed file storage service that can be easily mounted on Amazon EC2 instances. It provides shared file storage across multiple instances, allowing them to access the same file system concurrently. |
| EFS Mount Target  | EFS mount targets work like an entrypoint that allows Amazon EC2 instances to connect to EFS File system.                                                              |
| Amazon S3         | Amazon S3 is a scalable, durable, and secure object storage service. It allows storage and retrieval of large amounts of data from anywhere on the web.                    |
| AWS DataSync       | AWS DataSync is a managed data transfer service that simplifies and accelerates moving large volumes of data between on-premises storage, Amazon S3, and Amazon EFS.     |

***
## Flow Explaination

1. **EFS Mount Targets:** EFS mount targets allow Jenkins instances in different Availability Zones to access and share the same EFS file system.
   
2. **Jenkins Data Accumulation (EFS):** Jenkins data is accumulated and stored in the shared Amazon EFS file system, ensuring high availability and fault tolerance.
   
3. **AWS DataSync:** Scheduled AWS DataSync tasks transfer data from the EFS file system to an Amazon S3 bucket, creating regular and automated backups. Scheduled DataSync tasks are configured based on specific requirements, allowing flexibility in the frequency and timing of data transfers.

>[!Note]
>
>If you are interested in connecting Amazon EFS to Amazon S3 using AWS DataSync, you can find detailed instructions and step-by-step guidance in the [official AWS documentation on EFS to S3 DataSync integration](https://repost.aws/knowledge-center/datasync-transfer-efs-s3).

4. **Amazon S3 (Backup):** The final backup is stored in Amazon S3, providing a durable and scalable storage solution. Cross-Region Replication may be configured for additional to create duplicate copies or backups of data in different locations to ensure resilience and availability. You can also prefer to enable versioning so that you can retrieve you old data at a specific point of time. 

***
## MTTR
MTTR is the average time it takes to recover from a failure, incident, or data loss. It is a key metric in assessing the efficiency of your recovery processes.

MTTR Components: 
1. `Detection Time`: Time taken to identify the failure or data loss. With monitoring tools, you can quickly detect issues affecting Jenkins data. For early detection of issues affecting Jenkins data, employ a comprehensive monitoring strategy utilizing diverse solutions such as CloudWatch Alarms, CloudWatch Logs, and other monitoring tools.

2. `Resolution Time`: Time taken to resolve the issue. In this architecture, the resolution involves restoring from the latest backup in S3, minimizing the time needed to recover.

3. `Restoration Time`: Time taken to restore services to normal operation. AWS DataSync and S3 allow for efficient restoration from backups, contributing to a low MTTR.

***
## Contact Information

|Vidhi Yadav                     | vidhi.yadhav.snaatak@mygurukulam.co                                                                                      
|---------------------------------|------------------------------------------------------------|

***
## References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| DR approach           | https://medium.com/clarusway/disaster-recovery-guide-for-jenkins-2-6463e255964d    |
| DataSync + S3     | https://repost.aws/knowledge-center/datasync-transfer-efs-s3  |


