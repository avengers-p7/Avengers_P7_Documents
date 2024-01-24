# Documentation of AMI

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Shreya Jaiswal** | **24-01-2024** | **24-01-2024** | **v1** |

***

# Table of Contents

1. [Introduction](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#introduction)
2. [What is AMI](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#whatisAMI)
3. [Why AMI](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#whyAMI)
4. [Different Tools for AMI Management](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#DifferentTools)
5. [Reason for choosing jenkins](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#Jenkins)
6. [Pre-requisites](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#pre-requisites)
7. [AMI Setup](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#AMIsetup)
8. [Advantages of AMI](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#Advantages)
9. [Best Practices](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#BestPractices)
10. [Conclusion](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#conclusion)
11. [Contact Information](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#contactinformation)
12. [Reference](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#reference)

***

# Introduction

This documentation serves as a comprehensive guide, offering insights into the creation, maintenance, security considerations, and compliance governance surrounding AMIs within the AWS ecosystem.Whether embarking on new cloud projects or optimizing existing infrastructures, the insights provided herein will serve as a valuable resource for making informed decisions and ensuring the robustness of AWS deployments.

***

# What is AMI

An Amazon Machine Image is a special type of virtual appliance that is used to instantiate (create) a virtual machine within EC2. It serves as the basic unit of deployment for services delivered using EC2. Whenever you want to launch an instance, you need to specify AMI.It serves as a template for virtual servers, encapsulating the operating system, application software, configurations, and associated data. AMIs enable users to replicate computing environments efficiently and deploy applications consistently.

***

# Why AMI

| **Reason** | **Description** |
| ---------- | --------------- |
| **Rapid Deployment** | AMIs enable quick and consistent instance provisioning, reducing deployment time. |
| **Version Control** | Facilitates versioning of configurations, supporting easy rollback and updates. |
| **Scalability** | Supports auto-scaling and dynamic provisioning for varying workloads. |
| **Pay-as-You-Go Model** | AMIs align with AWS's pay-as-you-go pricing model, optimizing costs. |


***

# Different Tools for AMI Management

***

# Reasons for selecting "Jenkins" as a tool for AMI

| **Feature** | **Description** |
| ----------- | --------------- |
| **Versatility and Extensibility** | Jenkins is highly versatile and extensible, offering a wide range of plugins for integrating with different tools and services. |
| **Integration Capabilities** | Jenkins has a robust ecosystem of plugins that can seamlessly integrate with AWS services, including EC2 for AMI creation. |
| **Continuous Integration and Deployment** | Jenkins is purpose-built for continuous integration and deployment. It is well-suited for managing end-to-end CI/CD pipelines. |
| **Scripting and Automation** | Jenkins supports scripting in various languages, and you can use these scripts to automate AMI creation tasks. |

***

# Pre-requisites

1. AWS Account
2. Ensure that your AWS account has the necessary IAM permissions to create, manage, and launch instances from AMIs.

***

# AMI Setup

***

# Advantages of AMI

- AMIs allow users to quickly launch instances with pre-configured environments, reducing the time needed for provisioning and deployment.
- AMIs seamlessly support the scaling of resources up or down based on demand.
- AMIs facilitate the creation of snapshots, allowing users to back up and restore instances.
- AMIs support versioning, allowing users to manage and track changes to configurations over time.

***

# Best Practices

- Include only necessary software and configurations in the AMI to keep it lightweight.
- Restrict access to AMIs based on the principle of least privilege.
- Implement tagging for AMIs to categorize and manage them efficiently.
- Regularly review and clean up unused or outdated AMIs to reduce security risks.

***

# Conclusion

In conclusion, Amazon Machine Images (AMIs) play a pivotal role in the realm of cloud computing, offering unparalleled advantages in terms of efficiency, scalability, and resource optimization within the AWS ecosystem. This documentation has provided a comprehensive exploration of AMIs, covering their definition, components, and purpose. 

***

# Contact Information

| **Name** | **Email Address** |
| -------- | ----------------- |
| **Shreya Jaiswal** | shreya.jaiswal.snaatak@mygurukulam.co |

***

# Reference

| **Source** | **Description** |
| ---------- | --------------- |
| https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html | Documentation Link |                 
| https://www.techtarget.com/searchaws/definition/Amazon-Machine-Image-AMI | Concept of AMI |

