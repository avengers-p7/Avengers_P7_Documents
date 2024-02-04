# High Availability (HA) in Jenkins

<img width="597" alt="Screenshot 2024-02-04 at 12 32 27 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/fbfe577a-164e-4994-b062-74bd54817d39">

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 3 feb 2024   |     v1     | Vidhi Yadav     | 3 feb 2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Description](#jenkins-infrastructure-components)
+ [Contact Information](#contact-information)
+ [References](#references)


***
## Introduction 
High Availability is a strategic approach aimed at minimizing downtime and guaranteeing consistent performance without any downtime. The fundamental goal of HA is to mitigate the impact of potential failures, whether they be hardware failures, software issues, or unforeseen events. For a more detailed understanding of high availability and its components, please refer to the following link: [Detailed Description of High Availability](https://github.com/avengers-p7/Documentation/tree/main/Application_CI/Design/DevOps%20Practices/High%20Availability).

This documentation outlines the HA design, emphasizing the design considerations and components in place to achieve highly available Jenkins.

***
## Jenkins Infrastrucutre Components

* This diagram comprehensively illustrates the essential concepts of achieving high availability. Below is a detailed explanation of the key components employed in the AWS Jenkins High Availability infrastructure

1. **EFS** - This component is utilized to store essential elements such as the Jenkins home directory, configurations, and other relevant data. This component is designed for persistent data storage and can be seamlessly mounted across multiple instances within a single AWS region. Moreover, its capabilities extend to replication across multiple Availability Zones (AZs), enhancing accessibility.
   
2. **ASG** - The Auto Scaling Group (ASG) continuously monitors the availability of the Jenkins master. In the event of a failure, it initiates the replication of a new Jenkins master. This replication is based on a predefined launch configuration template, created from an AMI. This ensures the new instance has the necessary configurations and settings, maintaining consistency with the original Jenkins master.
   
3. **ALB** - Used for distribution incoming traffic and to enhance fault tolerance so If one instance becomes unavailable or experiences issues, the ALB automatically redirects traffic to healthy instances.

***
## AWS Infrastructure

![jenkins-HA drawio](https://github.com/avengers-p7/Documentation/assets/156056349/47885a75-38a6-410b-86c2-cb049a3358d4)

***
## Contact Information

|Vidhi Yadav                     | vidhi.yadhav.snaatak@mygurukulam.co                                                                                      
|---------------------------------|------------------------------------------------------------|

***
## References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| AWS doc for HA           | https://docs.aws.amazon.com/whitepapers/latest/real-time-communication-on-aws/high-availability-and-scalability-on-aws.html    |
| HA in jenkins    | https://devopscube.com/setup-highly-available-jenkins/  |
