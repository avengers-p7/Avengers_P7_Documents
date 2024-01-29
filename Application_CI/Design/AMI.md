# Documentation of AMI Introduction

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Shreya Jaiswal** | **24-01-2024** | **29-01-2024** | **v1** |

***

# Table of Contents

1. [Introduction](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#introduction)
2. [What is AMI](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#whatisAMI)
3. [Types of AMI](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#typesofAMI)
4. [Pros and Cons of AMI's Types ](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#AMIspros,cons)
5. [Why AMI](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#whyAMI)
6. [Advantages of AMI](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#Advantages)
7. [Limitations of AMI](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#limitationofAMI)
8. [Best Practices](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#BestPractices)
9. [Different Tools for AMI Management](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#DifferentTools)
10. [Reason for choosing jenkins](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#Jenkins)
11. [Conclusion](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#conclusion)
12. [Contact Information](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#contactinformation)
13. [Reference](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#reference)

***

# Introduction

This documentation serves as a comprehensive guide, offering insights into the creation, maintenance, security considerations, and compliance governance surrounding AMIs within the AWS ecosystem.Whether embarking on new cloud projects or optimizing existing infrastructures, the insights provided herein will serve as a valuable resource for making informed decisions and ensuring the robustness of AWS deployments.

***

# What is AMI?

An Amazon Machine Image is a special type of virtual appliance that is used to instantiate (create) a virtual machine within EC2. It serves as the basic unit of deployment for services delivered using EC2. Whenever you want to launch an instance, you need to specify AMI.It serves as a template for virtual servers, encapsulating the operating system, application software, configurations, and associated data. AMIs enable users to replicate computing environments efficiently and deploy applications consistently.

***

# Types Of AMI

| **Types** | **Description** |
| --------- | --------------- |
| **EBS-Backed AMI** | EBS is a block storage service provided by AWS that allows you to create resizable block-level storage volumes and attach them to EC2 instances.EBS volumes are highly available and reliable, and they can be used as the root device for instances.EBS-backed instances are more flexible in terms of storage management and can be easily snapshot for backup purposes.|
| **Instance-store (S3-backed) AMI** | An instance-store AMI uses instance-store volumes for the root device.The root file system is on an instance-store volume, and it is ephemeral, meaning it is tied to the life of the instance.|

***

# Pros,Cons and Limitations of AMI's Types

 | **AMIs** | **Pros** | **Cons** | 
 | ------------------ | -------- | -------- | 
 | **EBS-Backed AMI** | EBS-backed AMIs use Amazon Elastic Block Store (EBS) volumes for the root device, providing persistent storage even if the instance is stopped.| EBS-backed instances might incur additional costs due to the EBS volumes used for storage.|
 | **Instance-store (S3-backed) AMI** | Instance-store AMIs often have faster boot times as they rely on ephemeral (temporary) storage that is part of the instance itself.|  Instance-store instances lose all data when stopped or terminated since the root device is ephemeral.| 
 
 ***

# Why AMI?

| **Reason** | **Description** |
| ---------- | --------------- |
| **Rapid Deployment** | AMIs enable quick and consistent instance provisioning, reducing deployment time. |
| **Version Control** | Facilitates versioning of configurations, supporting easy rollback and updates. |
| **Scalability** | Supports auto-scaling and dynamic provisioning for varying workloads. |
| **Pay-as-You-Go Model** | AMIs align with AWS's pay-as-you-go pricing model, optimizing costs. |


***

# Advantages of AMI

| **Advantages** | **Description** |
| -------------- | --------------- |
| **Fast and Repeatable Deployments** | Enables rapid and consistent deployments, reducing the time and effort needed to set up new instances. |
| **Scaling and Elasticity** | AMIs play a crucial role in auto-scaling and load balancing strategies. |
| **Backup and Disaster Recovery** | AMIs serve as a basis for creating backups and implementing disaster recovery strategies. |
| **Versioning and Rollback** | AMIs can be versioned, allowing for easy rollbacks to previous configurations. |

***

# Limitations Of AMI

| **Limitation** | **Description** |
| -------------- | --------------- |
| **Region Specific** | AMIs are region-specific, and you need to create or copy them for use in different AWS regions. |
| **Instance Type Compatibility** | AMIs are often specific to certain instance types, and you need to ensure compatibility when launching instances. |
| **Time Taken** | There is a limit on the size of an AMI. If your AMI is large, it might take longer to launch instances from it. |
| **Customization Challenges** | Once an AMI is created, making changes requires creating a new AMI. |

***

# Best Practices

- Include only necessary software and configurations in the AMI to keep it lightweight.
- Restrict access to AMIs based on the principle of least privilege.
- Implement tagging for AMIs to categorize and manage them efficiently.
- Regularly review and clean up unused or outdated AMIs to reduce security risks.

***

# Different Tools for AMI Management

| **Tools** | **Pros** | **Cons** |
| --------- | -------- | -------- |
| **AWS Management Console** | User-friendly, especially for those who prefer a graphical interface. |  Not ideal for large-scale or automated AMI creation workflows. |
| **Hashicrop Packer** | Supports multiple platforms, not limited to AWS. | Additional tool to manage and learn. |
| **Netflix Aminator** | Simplifies software installation and configuration tasks. | Limited community support compared to more widely adopted tools. |
| **Terraform** | Supports multiple cloud providers, not limited to AWS. | May require additional modules for specific tasks. |
| **Ansible** | Declarative language and YAML syntax for configuration. | May not be as suitable for complex orchestration tasks. |
| **Docker** | Enables consistency across development and production. | Focuses on application containers rather than full system images. | 
| **Jenkins** | Highly extensible and customizable. | Requires additional plugins for specific AWS tasks. |

***

# Reasons for selecting "Jenkins" as a medium for creating AMI with AWS CLI

| **Feature** | **Description** |
| ----------- | --------------- |
| **Versatility and Extensibility** | Jenkins is highly versatile and extensible, offering a wide range of plugins for integrating with different tools and services. |
| **Integration Capabilities** | Jenkins has a robust ecosystem of plugins that can seamlessly integrate with AWS services, including EC2 for AMI creation. |
| **Continuous Integration and Deployment** | Jenkins is purpose-built for continuous integration and deployment. It is well-suited for managing end-to-end CI/CD pipelines. |
| **Scripting and Automation** | Jenkins supports scripting in various languages, and you can use these scripts to automate AMI creation tasks. |

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
| https://medium.com/@mbbhawsar28/ami-creation-with-jenkins-for-efficient-ci-cd-workflows-54429c2f686d | Link for Setup |

