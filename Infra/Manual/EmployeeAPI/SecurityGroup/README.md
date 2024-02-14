# POC for Manual Setup of Security Group for Employee API
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Shantanu | 12-01-2024 | 13-01-2024   |         v1     |     Shantanu    |
***

# Table of Content
[1. Introduction](#introduction)
[2. Overview](#overview)
[3. Setting Up the Environment](#setting-up-the-environment)
[4. Best practices](#best-practices)
[5. Conclusion](#conclusion)
[6. Contact Information](#contact-information)
[7. Refrences](#references)
***

# Introduction
This document outlines the steps and considerations for conducting a Proof of Concept (POC) on AWS Security Group for Employee API, a fundamental component for securing resources in the Amazon Web Services (AWS) environment. The POC focuses on understanding and implementing AWS Security Group for a hypothetical application deployment in AWS.
***

# Overview
AWS Security Groups act as virtual firewalls for EC2 instances, controlling inbound and outbound traffic by defining rules based on ports, protocols, and source/destination IP addresses, enhancing the security posture within the Amazon Web Services environment.

### Features
| Key Features             | Description                                              |
|--------------------------|----------------------------------------------------------|
| Dynamic rule updates     | Security Groups allow real-time adjustments to rules, enabling immediate changes to access controls without instance restarts. |
| Stateful filtering        | Security Groups maintain state information, automatically allowing return traffic for established connections, simplifying rule management. |
| Granular control over traffic flow | Security Groups provide fine-grained control by specifying allowed ports, protocols, and source/destination IP addresses, enhancing security customization. |

### Use Cases
| Use Cases            | Description                                              |
|----------------------|----------------------------------------------------------|
| Web applications     | Security Groups can be tailored to permit web traffic on specific ports (e.g., 80 for HTTP, 443 for HTTPS), ensuring a secure and controlled environment for hosting web applications. |
| Database servers      | For database servers, Security Groups allow restriction to only necessary ports (e.g., 3306 for MySQL, 5432 for PostgreSQL), limiting access to databases and enhancing data security. |
| Multi-tier architectures | Security Groups support the creation of layered security in multi-tier architectures by defining rules for communication between different tiers, facilitating a secure flow of traffic within the infrastructure. |

### Benefits
| Benefits                        | Explanation                                              |
|---------------------------------|----------------------------------------------------------|
| Enhanced security posture       | Security Groups contribute to an enhanced security posture by allowing precise control over network traffic, minimizing attack surfaces, and enforcing the principle of least privilege. |
| Easy scalability               | Security Groups seamlessly scale with the infrastructure, facilitating the addition or removal of instances without the need for manual adjustments, ensuring security scales in tandem with workloads. |
| Flexible configuration options  | Security Groups offer flexibility in defining rules based on ports, protocols, and IP addresses, providing adaptability to diverse application requirements and network architectures. |
***

# Setting Up the Environment

### Navigate to the EC2 Dashboard
* In the AWS Management Console, go to the "Services" menu and select "EC2" under the "Compute" section.
* In the EC2 Dashboard, locate the "Network & Security" section in the left navigation pane and click on "Security Groups."
* Select the VPC (Virtual Private Cloud) for which you want to create the security group.
* Under the "Inbound rules" section, click "Add Rule" to add the rules for incoming traffic. (8080,9042,6379,22)
* Click the "Create" button to create the security group.
  
![Screenshot 2024-02-14 at 11 15 25 PM](https://github.com/avengers-p7/Documentation/assets/156056364/3ff679ae-90c5-4da8-8668-4d53f3839a39)

### Associating the Security Group with Instances
* After creating the security group, you need to associate it with your instances.
* In the EC2 Dashboard, go to the "Instances" section.
* Select the instance you want to associate with the security group.
* Under the "Description" tab, find the "Security groups" section and click "Edit security groups."
* Choose the newly created security group and click "Save."
***

# Best Practices
| Best Practices                               | Explanation                                              |
|----------------------------------------------|----------------------------------------------------------|
| Principle of Least Privilege                 | Adhering to the principle of least privilege involves granting only the minimum access necessary for users or systems to perform their tasks, reducing the risk of unauthorized access and potential security breaches. |
| Regularly Reviewing and Updating Rules        | Establishing a routine process for reviewing and updating Security Group rules ensures that access controls align with changing application requirements and evolving security postures, maintaining an effective defense. |
| Combining Security Groups and Network ACLs    | Leveraging both Security Groups and Network Access Control Lists (ACLs) provides a layered security approach, enhancing control and protection by filtering traffic at both the instance and subnet levels within the AWS infrastructure. |
| Integrating with AWS Identity and Access Management (IAM) | Integrating Security Groups with AWS Identity and Access Management (IAM) allows for fine-grained access control, enabling the association of specific rules with IAM identities and roles, contributing to a more robust security architecture. |
***

# Conclusion
This POC demonstrates the process of creating a Security Group in AWS for hosting Employee API. Adjustment of parameters and settings based on specific requirements and preferences could be made.
***

# Contact Information
| Name | Email Address |
| ---- | ------------- |
| Shantanu  | shantanu.chauhan.snaatak@mygurukulam.co |
***

# References
| Source | Description  | 
| -------- | ------- | 
| https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Employee_API/README.md | Employee API |
