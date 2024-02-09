# Documentation of Declarative Pipeline for AMI Creation

![image](https://github.com/avengers-p7/Documentation/assets/156057205/7ab97e86-1928-454d-8770-4b5e13487e95)

***

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Shreya Jaiswal** | **08-02-2024** | **08-02-2024** | **v1** |

***

# Table Of Contents

1. [Introduction](#introduction)
2. [Pre-requisites](#pre-requisites)
3. [Flow Diagram](#flow-diagram)
4. [AMI Setup](#ami-setup)
5. [Pipeline](#Pipeline)
6. [Conclusion](#conclusion)
7. [Contact Information](#contact-information)
8. [Reference](#reference)

***

# Introduction

Creating Amazon Machine Images (AMIs) using Packer with Jenkins pipelines allows for efficient and automated infrastructure provisioning in AWS environments. Packer is a tool that automates the creation of machine images for multiple platforms, including AWS EC2 instances. When integrated with Jenkins pipelines, the process becomes streamlined and reproducible.

***

# What is Declarative Pipeline

Declarative Pipeline in Jenkins offers a simplified and structured approach for defining CI/CD pipelines, using a human-readable syntax with predefined sections like pipeline, stages, and agent. It's designed to be easy to read and maintain, making it suitable for users without strong scripting skills.It enforces a stricter syntax and allows for less flexibility compared to the scripted pipeline, which can be seen as an advantage for ensuring consistency and readability.

***

# Why Declarative Pipeline

| Aspect          | Description                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------|
| **Organization**    | Markdown tables organize pipeline stages, descriptions, and commands into neat columns for easier readability and understanding. |
| **Readability**     | Condenses verbose Declarative Pipeline syntax, particularly beneficial for complex pipelines, enhancing readability and comprehension. |
| **Documentation**   | Integrates pipeline configuration seamlessly into project documentation using Markdown, providing a comprehensive overview of CI/CD processes. |
| **Version Control** | Markdown files are version-controlled with tools like Git, enabling tracking of pipeline changes, revision history, and collaboration. |
| **Accessibility**   | Markdown files are viewable and editable with basic text editors or online Markdown editors, facilitating review and contribution by team members, including non-technical stakeholders. |
| **Presentation**    | Markdown files can be rendered into multiple formats, including HTML, PDF, and slideshows, enabling formatted documents or presentations for sharing and presentation purposes. |

***

# What is "Packer"

Packer, a powerful open-source tool developed by HashiCorp, has emerged as a preferred choice for creating AMIs. Offering multi-platform support, an infrastructure-as-code paradigm, and extensibility through various builders and provisioners, Packer streamlines the AMI creation process.

***

# Note

> [!NOTE]
> POC for Manually AMI Creation is prepared in different doc,if you want to see the AMI Creation Process use this link [AMI POC](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/02-%20Generic%20CI%20operation/AMI/AMI%20via%20Packer.md) 

***

# Pre-requisites

| **Pre-requisites** | **Description** |
| ------------------ | --------------- |
| **Jenkins** | Latest version of Jenkins (2.426.2) |
| **Packer** | Latest version of Packer (Packer v1.10.1) |
| **Pipeline Plugin** | This is a must-have as it provides the infrastructure for defining and running your pipeline as code. |
| **AWS Credentials Plugin** | This plugin allows you to securely store your AWS credentials in Jenkins. |
| **Credentials Binding Plugin** | This plugin is useful for binding credentials to environment variables in your Jenkins pipeline. |
| **Pipeline AWS Plugin** | This plugin provides a set of reusable functions for working with AWS services in Jenkins pipelines. It's particularly helpful when interacting with AWS services like EC2 for building AMIs. |
| **Amazon EC2 Plugin** | While not directly related to Packer, this plugin is useful if you plan to use Jenkins to provision temporary build agents on EC2 instances. |

**1.Jenkins Installed**

**2.Slack Notification Plugin**

**3.Job DSL Plugin**

***

# Flow Diagram

<img width="652" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/ceece0cc-394a-4809-9607-63e91cb0c01b">

***

# AMI Setup

***

# Pipeline

```shell
pipeline {
    agent any
    
    environment {
        AWS_ACCESS_KEY_ID = credentials('aws-credentials')
        AWS_SECRET_ACCESS_KEY = credentials('aws-credentials')
        PACKER_LOG = '1' // Set PACKER_LOG environment variable
    }
    
    stages {
        stage('Initialize Packer') {
            steps {
                dir('/home/shreya') {
                    sh '/usr/bin/packer init .'
                }
            }
        }
        stage('Build AMI') {
            steps {
                script {
                    try {
                        sh "/usr/bin/packer build -var AWS_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID} -var AWS_SECRET_ACCESS_KEY=${AWS_SECRET_ACCESS_KEY} /home/shreya/ami.pkr.hcl"
                        currentBuild.result = 'SUCCESS'
                    } catch (Exception e) {
                        currentBuild.result = 'FAILURE'
                        echo "AMI creation failed: ${e.message}"
                        error("AMI creation failed: ${e.message}")
                    }
                }
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed.'
        }
        success {
            echo 'AMI creation completed successfully.'
        }
        failure {
            echo 'AMI creation failed.'
        }
    }
}
```

***

# Conclusion

In conclusion, integrating Packer with Jenkins pipelines offers a powerful solution for automating AMI creation in AWS environments. By defining infrastructure as code and leveraging the automation capabilities of Jenkins, teams can ensure consistency, reliability, and scalability in their infrastructure provisioning workflows. With Packer handling the image creation process and Jenkins orchestrating the pipeline execution, teams can streamline their development and deployment processes, ultimately leading to faster delivery of applications and services. 

***

# Contact Information

| **Name** | **Email Address** |
| -------- | ----------------- |
| **Shreya Jaiswal** | shreya.jaiswal.snaatak@mygurukulam.co |

***

# Reference

| **Source** | **Description** |
| ---------- | --------------- |
| https://devopscube.com/packer-tutorial-for-beginners/ | Reference Link For AMI Creation |
| https://flugel-it.medium.com/building-and-running-custom-amis-on-aws-using-packer-and-terraform-3db28c968b30 | Reference Link |




