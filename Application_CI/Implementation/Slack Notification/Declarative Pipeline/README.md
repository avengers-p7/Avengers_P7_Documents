# Documentation of Declarative Pipeline for Slack Notification

***

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Shreya Jaiswal** | **08-02-2024** | **08-02-2024** | **v1** |

***

# Table Of Contents

1. [Introduction](#introduction)
2. [Pre-requisites](#pre-requisites)
3. [Slack Notification Setup](#slack-notification-setup)
4. [Pipeline](#Pipeline)
5. [Conclusion](#conclusion)
6. [Contact Information](#contact-information)
7. [Reference](#reference)

***

# Introduction

This document provides a detailed guide on implementing Slack notifications, including an introduction to Slack incoming webhooks, step-by-step instructions, and a Proof of Concept (POC) to demonstrate the integration.**Slack notification** integration is a valuable feature that allows you to keep your team informed and engaged by sending notifications directly to your Slack channels. This can be achieved using Slack's incoming webhooks, a simple and effective way to push messages from external sources into Slack.

***

# Pre-requisites

**1.Jenkins Installed**

**2.Slack Notification Plugin**

***

# Slack Notification Setup

Setting up Slack notifications in Jenkins involves integrating Jenkins with Slack using a Jenkins plugin and configuring the necessary settings in both Jenkins and Slack.

**Step-1 Workspace Creation**

Different projects or teams may have different Jenkins jobs with unique notification requirements. Using separate workspaces in Slack allows for the isolation and organization of notifications related to specific projects or teams.

Go to the Slack website.Click on "Get started for free" or "Create a new workspace."Follow the prompts to set up your Slack workspace, providing details such as your email address and password.

<img width="865" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/5abb2e1b-f5d1-47a0-ba8b-26a6c7bf7287">

***

**Step-2 Channel Creation**

Creating a dedicated channel for Jenkins notifications helps isolate and organize build-related messages.

Log in to your Slack workspace.In the left sidebar, click on the "+" button next to "Channels."Choose "Create a channel."

<img width="846" alt="Screenshot 2024-01-23 181612" src="https://github.com/avengers-p7/Documentation/assets/156057205/ce1ccb76-4a59-4a4c-89d9-4a0d418238d7">


***

**Step-3 Jenkins CI Setup**

This step includes the steps for "Password" or "Secret Text" creation,which is an important part for Slack Notification.With this,will get the "Team Subdomain" & "Password" which is needed for jenkins slack notification configuration.

<img width="945" alt="Screenshot 2024-01-23 181736" src="https://github.com/avengers-p7/Documentation/assets/156057205/ac515c7a-4501-48b6-b84d-2724d1084572">

***

<img width="940" alt="Screenshot 2024-01-23 181811" src="https://github.com/avengers-p7/Documentation/assets/156057205/a531d89d-8ee9-4c2c-b230-b3f66726201e">

***

**Step-4 Jenkins Configuration** 

Setting up Jenkins Global Configuration for Slack notifications allows you to centralize and manage Slack-related settings at a global level. This global configuration provides a convenient way to store and share common information, such as Slack team domain and integration tokens, across multiple Jenkins jobs.

Go to "Manage Jenkins" > "Configure System."Scroll down to the "Slack" section.In the "Team Domain" field, enter the Slack team domain.In the "Integration Token Credential" section, click on "Add" to add your Slack integration token as a Jenkins credential.Enter the necessary information, such as the token itself and an ID to identify the credential.In the "Test Connection" section, enter a Slack channel name and click on "Test Connection" to verify that Jenkins can communicate with Slack.

<img width="862" alt="Screenshot 2024-01-23 181534" src="https://github.com/avengers-p7/Documentation/assets/156057205/ff96bc8e-440e-4b72-946a-9f3757499eea">

***

**Slack Notification Plugin**

***

**Jenkinsfile Path in Configuration**

<img width="647" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/e84727c9-84e7-4b99-847c-3a1955ab83da">

***

**Console Output**

![image](https://github.com/avengers-p7/Documentation/assets/156057205/c00b8ea1-4282-4519-9ab6-40e2be285181)

![image](https://github.com/avengers-p7/Documentation/assets/156057205/4bbf42c0-1d39-4c90-9e6e-db9ed35dce4c)

![image](https://github.com/avengers-p7/Documentation/assets/156057205/f0131f03-0e8e-47f5-a95e-e15cc6bc9588)

***

**Slack Notification Result**

![image](https://github.com/avengers-p7/Documentation/assets/156057205/2cb31288-be30-47e1-b4fe-6f7c1a9f1491)

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

***

# Contact Information

| **Name** | **Email Address** |
| -------- | ----------------- |
| **Shreya Jaiswal** | shreya.jaiswal.snaatak@mygurukulam.co |

***

# Reference

| **Source** | **Description** |
| ---------- | --------------- |
| https://plugins.jenkins.io/slack | Link for Jenkins Configuration |
| https://medium.com/appgambit/integrating-jenkins-with-slack-notifications-4f14d1ce9c7a |  Integration Jenkins with slack |
| https://slack.com/apps/A0F7VRFKN-jenkins-ci | Link for Jenkins CI |



