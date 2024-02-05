# High Availability (HR)

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 4 feb 2024   |     v1     | Vidhi Yadav     | 4 feb 2024    |

*** 
## Introduction
High Availability is a strategic approach aimed at minimizing downtime and guaranteeing consistent performance without any downtime. The fundamental goal of HA is to mitigate the impact of potential failures, whether they be hardware failures, software issues, or unforeseen events. By distributing workloads across multiple instances, regions, or Availability Zones, HA architectures can withstand disruptions, providing constant access to applications and services. 

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
## Contact Information

|Vidhi Yadav                     | vidhi.yadhav.snaatak@mygurukulam.co                                                                                      
|---------------------------------|------------------------------------------------------------|

***
## References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| HA conepts           | https://medium.com/clarusway/disaster-recovery-guide-for-jenkins-2-6463e255964d    |
| aws documentation      | https://repost.aws/knowledge-center/datasync-transfer-efs-s3  |

