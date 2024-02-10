# Scripted Pipeline-Go Lang Bug Analysis

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
![Screenshot from 2024-02-09 17-47-50](https://github.com/avengers-p7/Documentation/assets/156056413/9e3c328a-92c1-41fe-a436-8b44175e5244)  
***

## Pre-requisites

* Jenkins Installed
* golang
* golangCI-lint

***
## Setup
 * Follow this document for Setup [**Cilck here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Declarative%20Pipeline/Readme.md#Setup)

   <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/a28f984f-f633-4acb-991e-f030fed8e0fd">  
   
* Console Output:
  
   <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/991ba6a2-f089-4742-a94a-7dfcbfe32492">
   <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/1813ded0-e8a2-43cf-a06e-9301decd5a6a">
  

> [!NOTE]
> **Changes**
> *  **Pipeline name**       **-**  "Bug Analysis (GoLang CI Checks)_(Scripted)"
> *  **Jenkinsfile Path**    **-**  "Scripted Pipeline/golang/Bug Analysis/Jenkinsfile"  

   
## HTML Report
 * Cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Scripted%20Pipeline/Report.html)

***
## Jenkinsfile
  * [**Jenkinsfie**](https://github.com/avengers-p7/Jenkinsfile/blob/main/Scripted%20Pipeline/golang/Bug%20Analysis/Jenkinsfile)
  ```shell
  node {
    stage('Installation Pre-Requisites') {
        try {
            // Update apt packages
            sh 'sudo apt update'
            // Install Go using snap
            sh 'sudo snap install go --classic'
            // Remove golangci-lint using snap
            sh 'sudo snap remove golangci-lint || true'
            // Install GolangCI-lint
            sh 'go install github.com/golangci/golangci-lint/cmd/golangci-lint@latest'
            // Add $HOME/go/bin to PATH
            env.PATH += ":$HOME/go/bin"
        } catch (Exception e) {
            echo "Error occurred during installation pre-requisites: ${e.getMessage()}"
        }
    }

    stage('Clone Repository') {
        try {
            // Clone the Git repository
            git branch: 'main', credentialsId: 'vishal-cred', url: 'https://github.com/OT-MICROSERVICES/employee-api.git'
        } catch (Exception e) {
            echo "Error occurred during repository cloning: ${e.getMessage()}"
        }
    }

    stage('Linting') {
        try {
            // Run golangci-lint and ignore errors
            sh 'golangci-lint run ./... || true'
        } catch (Exception e) {
            echo "Error occurred during linting: ${e.getMessage()}"
        }
    }

    stage('Generate HTML Report') {
        try {
            // Run golangci-lint with the --out-format option to specify the output format
            sh 'golangci-lint run ./... --out-format html > report.html || true'
        } catch (Exception e) {
            echo "Error occurred during HTML report generation: ${e.getMessage()}"
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
| Flow Step for create pipeline | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/POC%20of%20Bug%20Analysis%20(Golang%20CI%20Checks).md) |
| Jenkinsfile | [Link](https://github.com/avengers-p7/Jenkinsfile/blob/main/Scripted%20Pipeline/golang/Bug%20Analysis/Jenkinsfile) |
| Scripted vs Declarative Pipelines | [Link](https://www.baeldung.com/ops/jenkins-scripted-vs-declarative-pipelines) |
| Bug Analysis Introduction | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/Introduction%20of%20Bugs%20analysis%20(GoLang%20CI%20Checks).md#resources-and-references) |


***
