# POC for Manual Setup of Auto Scaling for Employee API
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Shantanu | 12-01-2024 | 13-01-2024   |         v1     |     Shantanu    |
***

# Table of Content
[1. Introduction<br>](#introduction)
[2. Overview<br>](#overview)
[3. Setting Up Auto Scaling in AWS<br>](#setting-up-auto-scaling-in-aws)  [4. Testing Auto Scaling<br>](#testing-auto-scaling)
[5. Best Practices<br>](#best-practices)
[6. Conclusion<br>](#conclusion)
[7. Contact Information<br>](#contact-information)
[8. References](#references)
***

# Introduction
This documentation aims to guide users in setting up Auto Scaling in AWS for better resource utilization and application availability. This POC covers the basic setup of Auto Scaling using the AWS Management Console.

### Pre-requisites

***

# Overview
Auto Scaling automatically adjusts the number of EC2 instances in a group based on defined policies. It helps maintain application availability and allows for efficient use of resources.

### Benefits
| Benefit                       | Explanation                                                                                                           |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| **Improved Availability**     | Auto Scaling enhances application availability by automatically adjusting the number of instances based on demand, ensuring consistent performance. |
| **Cost Optimization**         | Auto Scaling optimizes costs by dynamically adjusting the number of instances, allowing you to pay for only the resources you need at any given time. |
| **Efficient Resource Utilization** | Auto Scaling efficiently utilizes resources by scaling in during low demand and scaling out during peak periods, maximizing utilization without manual intervention. |


### Components
| Component                  | Explanation                                                                                                      |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| **Launch Configuration**   | - Defines the configuration settings for instances launched in the Auto Scaling group, including the AMI, instance type, storage, and security groups. |
| **Auto Scaling Group**      | - Represents a logical grouping of instances, defining the desired capacity, minimum and maximum number of instances, and enabling automatic scaling based on policies. |
| **Scaling Policies**        | - Specify rules for automatically adjusting the number of instances in response to changes in demand, such as scaling out during high load and scaling in during low load. |

***

# Setting Up Auto Scaling in AWS

***

# Testing Auto Scaling

| Step                               | Description                                                                                           |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------- |
| **Triggering Scale-Out Events** | - Simulate increased load on the application.<br>- Observe Auto Scaling's response.                   |
| **Monitoring Auto Scaling Activities** | - Use CloudWatch to monitor Auto Scaling activities.<br>- Check for scaling events and alarms.        |
| **Verifying New Instances**    | - Confirm new instances are launched successfully.<br>- Validate application performance.           |
***

# Best Practices

| Best Practice                    | Description                                                                                           |
| --------------------------------- | ----------------------------------------------------------------------------------------------------- |
| **Right-sizing Instances**    | - Choose appropriate instance types to match application requirements and optimize costs.              |
| **Health Checks**             | - Implement health checks for instances to ensure they are in a healthy state before and after scaling.|
| **Cool-down Periods**         | - Set appropriate cool-down periods to avoid unnecessary scaling actions during fluctuating workloads.|
| **Termination Policies**      | - Define termination policies to determine which instances are selected for termination during scale-in.|
***

# Conclusion
This POC documentation provides a basic guide for setting up and testing Auto Scaling in AWS. Adapt the steps and details according to your specific use case and organizational requirements.
***

# Contact Information
| Name | Email Address |
| ---- | ------------- |
| Shantanu  | shantanu.chauhan.snaatak@mygurukulam.co |
***

# References
| Source | Description  | 
| -------- | ------- | 
