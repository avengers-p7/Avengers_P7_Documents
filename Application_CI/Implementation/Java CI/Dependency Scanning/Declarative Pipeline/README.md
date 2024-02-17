# Java Code Compilation(Declarative Pipeline)

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| Vidhi Yadav  | 17th Feb 2024  | 1.0        | Vidhi Yadav   | 17th Feb 2024      |


## Table  of Contents

1. [Introduction](#Introduction)
2. [What is Declarative Pipeline](#What-is-Declarative-Pipeline)
3. [Prerequisites](#Prerequisites)
4. [Flow Diagram](#Flow-Diagram)
5. [Runtime Prerequisites](#Runtime-Prerequisites)
6. [Pipeline Setup](#Pipeline-Setup)
7. [Contact Information](#Contact-Information)
8. [References](#References)
***

## Introduction 
Dependency scanning is a security practice that involves analyzing the dependencies of a software application for known vulnerabilities and security issues. It's particularly crucial in modern software development, where applications often rely on numerous third-party libraries and components that can cause security risk in your application.

**For more information visit the below document link:**

[\[ Reference Doc \]](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Dependency%20Scanning/%20README.md)

In this task, we are using Declarative Pipeline.
***
## What is Declarative Pipeline

Declarative Pipeline in Jenkins offers a simplified and structured approach for defining CI/CD pipelines, using a human-readable syntax with predefined sections like pipeline, stages, and agent. It's designed to be easy to read and maintain, making it suitable for users without strong scripting skills. While it may be less flexible in terms of allowing complex scripting logic, it is a newer and more concise way to define Jenkins pipeline.

**For more information visit the below document link:**

[\[ Reference Doc \]](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md )

## Prerequisites

| Tool | Description |
| ---- | ----------- |
| **Jenkins(2.414.3)** | To build our pipeline |

***
## Runtime Prerequisites

|Language / Dependency|Description|
|-------|-------|
| **Maven Plugin** | to enable jenkins to build maven projects |
| **OWASP Dependency-Check Plugin** | for dependency-check configuration on your jenkins server |

***
## Flow Diagram
![image](https://github.com/avengers-p7/Documentation/assets/156056444/094ce1da-2714-4a57-86f0-97152fb2f8b6)
***
## Pipeline Setup
1. **Fork the Github Repo**
```shell
https://github.com/avengers-p7/Salary-API/tree/main
```
[**Repo Link**](https://github.com/OT-MICROSERVICES/salary-api)

2. **Configure Maven tool in Jenkins**
Go to `Dashboard--> Manage Jenkins--> Tools` and configure maven tool.

<img width="975" alt="Screenshot 2024-02-17 at 5 19 24 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/8ffb33b3-b11f-4ec8-a6b4-9764d5aca18c">


4. **Create and Configure your Jenkins Pipeline job**

	Follow below document to integrate Github with Jenkins:

	[Reference Document](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md)

<img width="944" alt="Screenshot 2024-02-17 at 5 16 48 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/95c45d64-1789-4460-947a-b5328825e98c">


5. **Now Build your Pipeline**
![image](https://github.com/avengers-p7/Documentation/assets/156056444/53deb6b1-a9a1-4e5b-83da-c64a93becfb0)
***
## Console Output
![image](https://github.com/avengers-p7/Documentation/assets/156056444/cbd74086-602f-45af-8cb8-61e2ec2ba2ae)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/33b3f5e3-cc47-4035-b25f-1016eea09c97)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/61720194-d89e-4f09-a257-14a696bbec31)

***
## [Pipeline](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/Java/CodeCompilation/Jenkinsfile)

```shell
pipeline {
    agent any
    tools {
      maven 'mvn'
    }
    stages {
        stage('Checkout GIT') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Panu-S-Harshit-Ninja-07/OT-Salary-API.git']])
                sh 'ls $WORKSPACE/'
            }
        }
        stage('Starting Code Compilation ') {
            steps {
                sh 'echo "Starting Java Code Compilation.........."'
                sh 'mvn clean compile'
            }
        }
    }
post { 
        success { 
            sh 'ls $WORKSPACE/'
            echo 'Compiled Successfully !'
            sh 'tree $WORKSPACE/target/'
        }
        failure { 
            echo 'Compilation Failed !'
        }
    }
}
```

***

## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Clean Workspace | https://www.jenkins.io/doc/pipeline/tour/running-multiple-steps/#finishing-up |
| Pipeline (Generic Doc) | https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md |
| Create Pipeline (Generic Doc)| https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md |
| Pipeine Syntax | https://www.jenkins.io/doc/book/pipeline/#pipeline-syntax-overview |
| Pipeline Concepts | https://www.jenkins.io/doc/book/pipeline/#pipeline-concepts |
