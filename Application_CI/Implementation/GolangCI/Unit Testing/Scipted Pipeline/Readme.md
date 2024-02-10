# Scripted Pipeline-Go Lang Unit Testing

|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Vishal Kumar Kesarwani |  09-02-2024  |  Version 1 | Vishal  | 09-02-2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Scripted Pipeline](#Why-Scripted-Pipeline)
+ [Flow Daigram](#Flow-Daigram)
+ [Pre-requisites](#Pre-requisites)
+ [Setup](#Setup)
+ [Jenkinsfile](#Jenkinsfile)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)
  
***
## Introduction

Scripted Pipeline in Jenkins allows users to define CI/CD pipelines using Groovy scripting language, offering flexibility and customization for defining complex workflows. It provides an imperative, programmatic approach where users write scripts executed sequentially by Jenkins, with direct access to Jenkins APIs for advanced automation and integration. Scripted Pipelines are suitable for environments requiring fine-grained control over pipeline execution and the ability to define pipelines as code.

***
## Why Scripted Pipeline
| Aspect                    | Description                                                                                                                                                       |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Imperative Syntax**        | Write pipelines as Groovy scripts, providing full control over execution flow for complex logic and dynamic behavior.                                           |
| **Programmatic Constructs**  | Access to programming features like loops, conditions, variables, and functions for building highly customizable pipelines.                                       |
| **Direct Access to APIs**    | Scripts directly interact with Jenkins APIs, enabling fine-grained automation and integration with plugins and external systems.                                 |
| **Extensibility**            | Allows for defining custom functions and importing external libraries to enhance pipeline functionality and reusability.                                          |
| **Legacy Support**           | Widely used in environments with existing pipelines, providing familiarity and compatibility with legacy systems.                                               |
| **Learning Curve**           | Requires understanding of Groovy syntax and Jenkins pipeline concepts, posing a steeper learning curve, especially for newcomers.                                |
| **Debugging and Maintenance** | Imperative nature can make debugging and maintenance challenging, necessitating proper organization, documentation, and testing practices.                     |

***
## Flow Daigram
![Screenshot from 2024-02-10 12-24-04](https://github.com/avengers-p7/Documentation/assets/156056413/a5324c1b-68c8-447c-9299-dcf28c6870d2)
***

## Pre-requisites
| **Pre-requisites** | **Version** |
| ------------------ | ----------- |
| Jenkins | 2.426.3 | 
| golang | 1.21.6 |


***
## Setup
 * Follow this document for Setup [**Cilck here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Declarative%20Pipeline/Readme.md#Setup)

   <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/b33aa757-de4f-485b-b885-430062e093da">  
   
* Console Output:

   <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/6896e404-62a6-4b4e-9221-44561cb8a4a6">
  

> [!NOTE]
> **Changes**
> *  **Pipeline name**       **-**  `Unit _Testing_(golang_CI_Checks)_(Scripted)`
> *  **Jenkinsfile Path**    **-**  `Scripted Pipeline/golang/Unit Testing/Jenkinsfile`  

   
## HTML Report
 * Cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Unit%20Testing/Scipted%20Pipeline/Report.html)

***
## Jenkinsfile
  * [**Jenkinsfie**](https://github.com/avengers-p7/Jenkinsfile/blob/main/Scripted%20Pipeline/golang/Unit%20Testing/Jenkinsfile)
  ```shell
  
node {
    stage('Installation Go') {
        try {
            // Update apt packages
            sh 'sudo apt update'
            // Install Go using snap
            sh 'sudo snap install go --classic'
        } catch (Exception e) {
            echo "Failed to install Go: ${e.message}"
            currentBuild.result = 'FAILURE'
            error("Failed to install Go")
        }
    }
    
    stage('Clone Repository') {
        try {
            // Clone the Git repository
            git branch: 'main', credentialsId: 'vishal-cred', url: 'https://github.com/OT-MICROSERVICES/employee-api.git'
        } catch (Exception e) {
            echo "Failed to clone repository: ${e.message}"
            currentBuild.result = 'FAILURE'
            error("Failed to clone repository")
        }
    }
    
    stage('Testing') {
        try {
            // Run go test and ignore errors
            sh 'go test ./... || true'
        } catch (Exception e) {
            echo "Failed to run tests: ${e.message}"
            currentBuild.result = 'FAILURE'
            error("Failed to run tests")
        }
    }
    
    stage('Generate HTML Report') {
        try {
            // Run gotest with specify the output format and generate HTML Report
            sh 'go test ./... -coverprofile=coverage.out || true'
            sh 'go tool cover -html=coverage.out -o coverage.html || true'
        } catch (Exception e) {
            echo "Failed to generate HTML report: ${e.message}"
            currentBuild.result = 'FAILURE'
            error("Failed to generate HTML report")
        }
    }
}
```
***
## Conclusion

Scripted Pipeline is a powerful and flexible way to define Jenkins pipelines using Groovy scripting language. It's suitable for environments and use cases that require fine-grained control, advanced automation, and integration capabilities. However, it also requires a deeper understanding of programming concepts and may entail additional complexity in debugging and maintenance compared to Declarative Pipeline.

***
## Contact Information
| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |
***
## Resources and References
|  **Description** |   **Source** |
| ---------------- | ------------ |
| About Jenkins Pipeline (Generic Document) | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md  ) |
| Flow Step for create pipeline | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Unit%20Testing%20(GoLang%20CI%20Checks).md) |
| Setup Jenkins | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Declarative%20Pipeline/Readme.md#Setup) |
| Jenkinsfile | [Link](https://github.com/avengers-p7/Jenkinsfile/blob/main/Scripted%20Pipeline/golang/Unit%20Testing/Jenkinsfile) |
| Scripted vs Declarative Pipelines | [Link](https://www.baeldung.com/ops/jenkins-scripted-vs-declarative-pipelines) |
| Unit Testing | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Intro-of-Unit-Testing.md) |

***
