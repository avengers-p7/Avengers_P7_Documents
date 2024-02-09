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

***

# Why Declarative Pipeline

***

# What is "Packer"

***



***

# Pre-requisites

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
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Define the DSL for creating a Freestyle job
                    def jobDSL = '''
                        job('My-Freestyle-Job') {
                            description('This is a sample Freestyle job created using a Declarative Pipeline')
                            steps {
                                shell('echo "Hello, world!"')
                            }
                        }
                    '''
                    // Execute the job DSL to create the Freestyle job
                    jobDsl scriptText: jobDSL
                }
            }
        }
    }
    
    post {
        success {
            slackSend(color: '#36a64f', message: "Declarative Job completed successfully!", channel: "#jenkins", teamDomain: "demoworkspace-6868926", tokenCredentialId: "e96c6c7f-1fdf-4c4a-80fd-5ad178092678")
        }
        failure {
            slackSend(color: '#ff0000', message: "Declarative Job failed!", channel: "#jenkins", teamDomain: "demoworkspace-6868926", tokenCredentialId: "e96c6c7f-1fdf-4c4a-80fd-5ad178092678")
        }
    }
}
```

***

# Conclusion

In summary, integrating Slack notifications with Jenkins through Declarative Pipelines simplifies communication in software teams. With our pipeline configuration stored on GitHub, we streamline the process and ensure everyone receives timely updates on build outcomes. This straightforward approach promotes collaboration and keeps the team aligned, ultimately leading to smoother development cycles and faster problem-solving.

***

# Contact Information

| **Name** | **Email Address** |
| -------- | ----------------- |
| **Shreya Jaiswal** | shreya.jaiswal.snaatak@mygurukulam.co |

***

# Reference

| **Source** | **Description** |
| ---------- | --------------- |
| https://eavnitech.com/blog/send-notification-to-slack-from-the-Jenkins-CI-job-and-jenkinsfile/ |  Integration Jenkins with slack |
| https://naiveskill.com/jenkins-pipeline-slack-notification/ | Link for Jenkins CI |




