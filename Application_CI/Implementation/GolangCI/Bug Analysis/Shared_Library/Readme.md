# Shared Library Go Lang Bug  Analysis

  <img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/8f646df3-4ed6-434e-9a69-b8fd8ccfb6b9">

|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Vishal Kumar Kesarwani |  13-02-2024  |  Version 1 | Vishal  | 13-02-2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Shared Library](#Why-Shared-Library)
+ [Flow Diagram](#Flow-Diagram)
+ [Pre-requisites](#Pre-requisites)
+ [Setup of Bug Analysis](#Setup-of-Bug-Analysis-Via-Shared-Library)
+ [HTML Report](#HTML-Report)
+ [Jenkinsfile](#Jenkinsfile)
+ [Shared Library](#Shared-Library)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)
  
***
## Introduction

 <img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/f94f127a-d207-4c76-bc32-d25e4fe48280"> 

A Jenkins Shared Library is a collection of reusable code that facilitates the sharing of common pipeline logic among teams in Jenkins. It simplifies CI/CD processes by abstracting complex tasks into functions, speeding up pipeline development. By keeping shared code separate from individual pipelines, teams ensure consistency and minimize duplication. This fosters collaboration, encourages best practices, and streamlines Jenkins pipeline creation, leading to better software delivery and development workflows.  
About more information [**Click Here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/sharedLibrary/README.md)

***
## Why Shared Library
| Advantage          | Description                                                                                                                                                          |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Reusability**        | Shared Libraries allow teams to write code once and reuse it across multiple pipelines. This reduces duplication of effort and promotes consistency in the CI/CD process. |
| **Centralization**     | By centralizing common pipeline logic, updates and improvements can be made in one place, benefiting all pipelines that use the library.                             |
| **Abstraction**        | Complex tasks can be abstracted into simple functions in the Jenkins Shared Library, making pipeline scripts cleaner and more maintainable.                            |
| **Standardization**    | Jenkins Shared Library allows organizations to define standardized practices, coding conventions, and security measures across all pipelines.                         |
| **Collaboration**      | Jenkins Shared Libraries encourage collaboration among teams, as they can share and contribute to a common set of pipeline tools and utilities.                         |
| **Versioning Control** | Jenkins Shared Library can be version-controlled, enabling teams to manage changes and rollbacks effectively.                                                        |
| **Ease of Maintenance** | As the Jenkins Shared Library is maintained separately from individual pipelines, updates and bug fixes can be implemented without impacting the pipelines directly. |

***
## Flow Diagram  
![Screenshot from 2024-02-09 17-47-50](https://github.com/avengers-p7/Documentation/assets/156056413/9e3c328a-92c1-41fe-a436-8b44175e5244)  

***
## Pre-requisites
| **Pre-requsisites** | **Version** |
| ------------------- | ----------- |
| Jenkins | 2.426.3 |
| golang | 1.21.6 |
| golangCI-lint | 1.55.2 |  

***
## Setup of Bug Analysis Via Shared Library
* Follow this document for Setup [**Cilck here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/sharedLibrary/setup.md)

  <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/95ae3196-eebd-43f3-b399-6db1443f1a29"> 

* Console Output:

   <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/cc4e4cb5-1749-4848-a105-eaf71ff8546a"> 


> [!NOTE]
> **Changes**
> *  **Pipeline name**       **-**  `Bug_Analysis_(GoLang_CI_Checks)`
> *  **Jenkinsfile Path**    **-**  `SharedLibrary/Golang/BugAnalysis/Jenkinsfile`  

***

## HTML Report
 * Cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Shared_Library/Report.html)

***
## Jenkinsfile
  * [**Jenkinsfie**](https://github.com/avengers-p7/Jenkinsfile/blob/main/SharedLibrary/Golang/BugAnalysis/Jenkinsfile)
  ```shell

@Library('snaatak-p7') _

pipeline {
    agent any
    
    stages {
        stage('Installation Pre-Requisites') {
            steps {
                script{
                    golangBugAnalysis.installprerequisites()
                }
            }
        }
        stage('Checkout') {
            steps {
                gitCheckoutPrivate(branch: 'main', url: 'https://github.com/OT-MICROSERVICES/employee-api.git', credentialsId: 'vishal-cred')
            }
        }
        stage('Linting') {
            steps {
                script{
                    golangBugAnalysis.linting()
                }
            }
        }
        stage('Generate HTML Report') {
            steps {
                script{
                    golangBugAnalysis.html()
                }
            }
        }
    }
}
    
        
```
## Shared Library
  * [**gitCheckoutPrivate.groovy**](https://github.com/avengers-p7/SharedLibrary/blob/main/vars/gitCheckoutPrivate.groovy)
  ```shell
// Checkout Github Private Repository
// vars/gitCheckoutPrivate.grovvy
def call(Map config = [:]) {
    checkout scm: [
        $class: 'GitSCM',
        branches: [[name: config.branch]],
        userRemoteConfigs: [[url: config.url, credentialsId: config.credentialsId]]
    ]
}
```
  * [**golangBugAnalysis.groovy**](https://github.com/avengers-p7/SharedLibrary/blob/main/vars/golangBugAnalysis.groovy)
  ```shell
// vars/golangBugAnalysis.groovy
def installprerequisites(){
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
}

def linting(){
  // Run golangci-lint and ignore errors
  sh 'golangci-lint run ./... || true'
}

def html(){
  // Run golangci-lint with the --out-format option to specify the output format
  sh 'golangci-lint run ./... --out-format html > report.html || true'
}
```
***
## Conclusion
The Jenkins Shared Library streamlines CI/CD processes by allowing teams to share reusable code and logic across various pipelines. It standardizes workflows, minimizes duplication, and ensures consistency. With abstracted complex tasks into reusable functions, it simplifies maintenance and fosters collaboration among teams. By promoting best practices and enabling version control, it enhances the efficiency and reliability of the CI/CD process, accessible even without Jenkins admin access.

***
## Contact Information
| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |
***
## Resources and References
|  **Description** |   **Source** |
| ---------------- | ------------ |
| About Jenkins Shared Library (Generic Document) | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/sharedLibrary/README.md) |
| POC Generic Document | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/sharedLibrary/setup.md) |
| Jenkinsfile | [Link](https://github.com/avengers-p7/Jenkinsfile/blob/main/SharedLibrary/Golang/BugAnalysis/Jenkinsfile) |
| Manual Setup | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/POC%20of%20Bug%20Analysis%20(Golang%20CI%20Checks).md) |
| Manual Pipeline | [Declarative](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Declarative%20Pipeline/Readme.md) & [Scripted](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Scripted%20Pipeline/Readme.md) |
| Bug Analysis | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/Introduction%20of%20Bugs%20analysis%20(GoLang%20CI%20Checks).md#resources-and-references) |

***

