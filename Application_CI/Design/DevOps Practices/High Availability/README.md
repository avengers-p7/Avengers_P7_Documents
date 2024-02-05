# High Availability (HR)

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 4 feb 2024   |     v1     | Vidhi Yadav     | 4 feb 2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [How HA Works?](#how-high-availability-works)
+ [Key Concepts](#key-concepts)
+ [HA vs DR difference](#high-availability-vs-disaster-recovery)
+ [Contact Information](#contact-information)
+ [References](#references)

*** 
## Introduction
High Availability is a strategic approach aimed at minimizing downtime and guaranteeing consistent performance without any downtime. The fundamental goal of HA is to mitigate the impact of potential failures, whether they be hardware failures, software issues, or unforeseen events. By distributing workloads across multiple instances, regions, or Availability Zones, HA architectures can withstand disruptions, providing constant access to applications and services. 

***
## How High Availability Works ? 
### Identifying and Eliminating Single Points of Failure:

Single points of failure are components or elements within a system that, if they fail, can bring down the entire system or a significant part of it.
To achieve high availability, it is crucial to identify and eliminate these single points of failure. This can involve critical components so that if one fails, there is a backup ready to take over.
For example, if a server is a single point of failure, having a second server that can immediately take over in case the first one fails ensures continuity.

### Detecting Data Loss or System Failures:

High availability systems often incorporate mechanisms to detect failures or data loss promptly. This can include monitoring tools, automated alerts, and health checks.
Continuous monitoring helps identify issues in real-time and at an early stage, allowing for quick responses. This minimizes the impact of failures on the overall system.

### Adapting Quickly to Failures:

High availability systems are designed to adapt quickly to failures without significant impact on the user experience.
This adaptability often involves automatic failover mechanisms, load balancing, and quick re-routing of traffic to healthy components.
The goal is to maintain continuous service availability, even in the face of unexpected failures or disruptions.

***
## Key Concepts 

* Key characteristics of high availability systems include:

| Feature           | Description                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------------------|
| Redundancy        | HA systems often incorporate redundant components, such as servers, network connections, and storage, to eliminate single points of failure. If one component fails, another can seamlessly take over, maintaining continuous operation.|
| Failover          | Failover mechanisms are implemented to automatically switch to a backup or standby system when the primary system encounters a failure. This helps in maintaining service continuity without manual intervention.|
| Load Balancing    | Distributing the workload across multiple servers helps prevent overload on any single server and improves overall system performance. Load balancing can be dynamic, adjusting in real-time based on the current system conditions.|
| Fault Tolerance   | HA systems are designed to gracefully handle faults and errors without causing a complete system failure. This often involves implementing error-checking mechanisms and recovery procedures.|
| Data Replication  | Critical data is often replicated across multiple locations or servers to ensure data integrity and availability. This can involve synchronous or asynchronous replication depending on the specific requirements of the system.|
| Scalability       | High availability architectures are often designed to scale horizontally, allowing for the addition of more resources or nodes to accommodate increased demand.|

***
## High Availability Vs Disaster Recovery 
Distinguishing between high availability and disaster recovery is crucial. Disaster recovery (DR) involves a detailed strategy aimed for recovery of critical operations and systems after catastrophic events.

In contrast, when you have a system that is both highly available and fault-tolerant, the question arises: *why invest effort in disaster recovery planning*.

Disaster recovery typically focus on restoration of normal functionalities after a major disaster, whereas high availability addresses typical failures, such as a malfunctioning component or server. While both concepts are interconnected, a disaster recovery plan is designed to handle scenarios like the loss of an entire region.

***
## Contact Information

|Vidhi Yadav                     | vidhi.yadhav.snaatak@mygurukulam.co                                                                                      
|---------------------------------|------------------------------------------------------------|

***
## References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| HA conepts           | https://avinetworks.com/glossary/high-availability/    |
| aws documentation      | https://repost.aws/knowledge-center/datasync-transfer-efs-s3  |

