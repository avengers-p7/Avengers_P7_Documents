# Documentation of AMI

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Shreya Jaiswal** | **24-01-2024** | **25-01-2024** | **v1** |

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

# What is AMI?

An Amazon Machine Image is a special type of virtual appliance that is used to instantiate (create) a virtual machine within EC2. It serves as the basic unit of deployment for services delivered using EC2. Whenever you want to launch an instance, you need to specify AMI.It serves as a template for virtual servers, encapsulating the operating system, application software, configurations, and associated data. AMIs enable users to replicate computing environments efficiently and deploy applications consistently.

***

# Why AMI?

| **Reason** | **Description** |
| ---------- | --------------- |
| **Rapid Deployment** | AMIs enable quick and consistent instance provisioning, reducing deployment time. |
| **Version Control** | Facilitates versioning of configurations, supporting easy rollback and updates. |
| **Scalability** | Supports auto-scaling and dynamic provisioning for varying workloads. |
| **Pay-as-You-Go Model** | AMIs align with AWS's pay-as-you-go pricing model, optimizing costs. |


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
2. EC2 Instance
3. Ensure that your AWS account has the necessary IAM permissions to create, manage, and launch instances from AMIs.
4. Jenkins setup

***

# AMI Setup

**Step-1 Launch EC2 Instance**

Launching an instance before creating an AMI provides the opportunity to customize, configure, and test the environment, ensuring that the resulting AMI accurately represents the desired system state.

<img width="958" alt="Screenshot 2024-01-25 143104" src="https://github.com/avengers-p7/Documentation/assets/156057205/72d9cc22-11df-48ca-a2c0-80113ec4c586">

***

**Step-2 Jenkins Setup**

Setting up Jenkins for creating Amazon Machine Images (AMIs) with a Jenkins pipeline is a common practice for automating infrastructure processes.For AMI creation,we need plugins **"AWS Steps" "Amazon EC2"** and also,we need to configure **Clouds** section under **Manage Jenkins**
to add the necessary **AWS Credentials"** and **"Private key"**.

<img width="920" alt="Screenshot 2024-01-25 143300" src="https://github.com/avengers-p7/Documentation/assets/156057205/c3af0e46-e02e-4599-9e23-864fc65f489b">

***

**Step-3 Pipeline Creation**

Creating a Jenkins pipeline job for AMI creation brings automation, consistency, and integration benefits to the infrastructure provisioning process. It aligns with modern DevOps practices and facilitates the efficient management of infrastructure as code.
**Created a AMICreation Pipeline and configured it depending on the use case**.

<img width="949" alt="Screenshot 2024-01-25 134732" src="https://github.com/avengers-p7/Documentation/assets/156057205/db928af7-b8bb-4af9-85df-522a4abfac82">

***

<img width="925" alt="Screenshot 2024-01-25 134754" src="https://github.com/avengers-p7/Documentation/assets/156057205/25002fa9-6718-46cc-9a0d-5bd31dda7ed9">

 ***

 <img width="945" alt="Screenshot 2024-01-25 134820" src="https://github.com/avengers-p7/Documentation/assets/156057205/527be10f-a54a-4264-99c3-5e0b2f4189ae">

 ***

**Step-4 Build Step**

In this step,i have configured the pipeline with **Parameterized Job** in which,i have used **String Parameter**, **"Creator_Name"** and **"instance_id"** as a parameter,below is the result of this step.

<img width="950" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/d998c878-f251-4dce-b16a-f9d6a4a20469">

***

**Step-5 Console Output**

Output of the generated pipeline which shows the creation of AMI with **Success** status.

<img width="940" alt="Screenshot 2024-01-25 143124" src="https://github.com/avengers-p7/Documentation/assets/156057205/13fc046f-30a3-420b-afba-6467a433f8c5">

***

**Step-6 Confirmation of AMI Creation**

Here is the result of the AMI creation with pipeline with the help of jenkins.

<img width="939" alt="Screenshot 2024-01-25 143054" src="https://github.com/avengers-p7/Documentation/assets/156057205/56f1ed0c-40c3-4f0e-9836-b5800a17981a">

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
| https://medium.com/@mbbhawsar28/ami-creation-with-jenkins-for-efficient-ci-cd-workflows-54429c2f686d | Link for Setup |

