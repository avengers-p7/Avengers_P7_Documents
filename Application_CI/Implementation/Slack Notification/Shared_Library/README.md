# Documentation For POC Of Slack Notification

![image](https://github.com/avengers-p7/Documentation/assets/156057205/dda1dea8-7775-4e90-b1b6-b8a9616a32d2)

***

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Shreya Jaiswal** | **12-02-2024** | **12-02-2024** | **v1** |

***

# Table Of Contents

1. [Introduction](#introduction)
2. [What is Shared Library?](#what-is-shared-library)
3. [Why Shared Library](#why-shared-library)
4. [Pre-requisites](#pre-requisites)
5. [Flow Diagram](#flow-diagram)
6. [Slack Notification Setup](#slack-notification-setup)
7. [Pipeline](#Pipeline)
8. [Conclusion](#conclusion)
9. [Contact Information](#contact-information)
10. [Reference](#reference)

***

# Introduction

This documentation presents the development and usage of a shared library for Slack notification. The shared library includes common functions for sending notifications to Slack channels. The purpose of this library is to streamline the process of integrating Slack notifications into various applications, reducing duplication of code and ensuring consistency in notification functionality across different projects.

***

# What is Shared Library?

A shared library in Jenkins is a reusable collection of Groovy scripts that can be used by multiple Jenkins jobs.Shared libraries provide a way to efficiently share code and resources among multiple programs, promoting code reuse, efficient memory usage, and easier maintenance and updates.Each shared library requires users to define a name and a method of retrieving source code. These methods include local files, Git repositories, and Jenkins SCM plugins. Optionally, users can also set a default library version.

***

# Why Shared Library

| **Reason** | **Description** |
| ---------- | --------------- |
| **Reusability** | Shared libraries allow developers to write code once and reuse it in multiple programs, reducing duplication of effort and making maintenance easier. |
| **Dynamic Linking** |  When a program uses a shared library, the code from the library is not directly included in the program's executable file. Instead, references to the library are included, and the actual library code is loaded into memory at runtime when the program is executed. |
| **Efficient Memory Usage** | Since shared libraries are loaded into memory only once, even if multiple programs are using them simultaneously, they can help conserve system resources and reduce memory usage. |
| **Updates and Maintenance** |  If a shared library is updated or patched to fix bugs or add features, all programs that use that library can benefit from the changes without needing to be recompiled. |

***

# Pre-requisites

**1.Jenkins Installed**

**2.Slack Notification Plugin**

**3.Job DSL Plugin**

***

# Flow Diagram

<img width="652" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/ceece0cc-394a-4809-9607-63e91cb0c01b">

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

<img width="644" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/3b91bb9d-bb3c-4f5e-b600-08b11bf3f009">

***

**Job Dsl Plugin**

<img width="596" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/e5bc6f6f-5ddd-414a-81a9-1f1f6a1a69e7">

***

**Jenkinsfile Path in Configuration**

<img width="647" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/e84727c9-84e7-4b99-847c-3a1955ab83da">

***

**Console Output**

![image](https://github.com/avengers-p7/Documentation/assets/156057205/c00b8ea1-4282-4519-9ab6-40e2be285181)

![image](https://github.com/avengers-p7/Documentation/assets/156057205/4bbf42c0-1d39-4c90-9e6e-db9ed35dce4c)

![image](https://github.com/avengers-p7/Documentation/assets/156057205/f0131f03-0e8e-47f5-a95e-e15cc6bc9588)

***

**Freestyle Job Created of name "My-Freestyle-Job"**

<img width="673" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/c44f2127-32fe-483b-afc3-3e694fb925e6">

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

In conclusion, the shared library for Slack notification simplifies the process of integrating Slack notifications into applications by providing common functions for sending messages to Slack channels. By using this library, developers can save time and effort by avoiding the need to write notification code from scratch for each project. The library promotes code reuse, enhances consistency, and improves the overall development workflow when incorporating Slack notifications into various applications.

***

# Contact Information

| **Name** | **Email Address** |
| -------- | ----------------- |
| **Shreya Jaiswal** | shreya.jaiswal.snaatak@mygurukulam.co |

***

# Reference
| **Source** | **Description** |
| ---------- | --------------- |
| [Link](https://keentolearn.medium.com/how-to-improve-your-jenkins-builds-with-shared-libraries-5e225b7435fb#:~:text=A%20shared%20library%20in%20Jenkins,efficient%20and%20easier%20to%20maintain.) | Link For Shared Library |
| [Link](https://phoenixnap.com/kb/jenkins-shared-library) | Reference Link For Understanding the concept of Shared Library |
| [Link](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbHluUi1nZVZJcmRLai1COXZxMVRjcERlLXhXZ3xBQ3Jtc0trT05uZ3dWaG1sZmZHYXVQeWluVnl2ZHF6c3BYdGlyUE1OREh3NkRFb0dFMG5VQWxyMXhNRHRnWkxBY2hKTnB5UkJySW9BOVJkczJzRlZiZm92NVdWNHg1ZEJLeU5tRmFlS2sxWDZJUmE0YThuQ1JPQQ&q=https%3A%2F%2Fwww.jenkins.io%2Fdoc%2Fbook%2Fpipeline%2Fshared-libraries%2F&v=Wj-weFEsTb0) | Reference Link |
